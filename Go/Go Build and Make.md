# Go Build and Make
  - go build and go install
  - about makefile
    - pure makefile for go
    - go-makefile (w/ docker)

---

# $GOPATH
- `src` and `pkg`
  - `/src/foo/bar.go`
  - `/pkg/OS_ARCH/foo/bar.a`

---

# Build
- parameters
  - first line comment `//+build linux,386 darwin,!cgo`
  - [parameters](https://golang.org/pkg/go/build/)
- `go build -o <output>`
  - default output file is `Go`
- `go install`
  - cache the .a file and place under $GOPATH/pkg/
  - put the outpur file under $GOPATH/bin/

---
# Makefile for Go

Makefile
```
SOURCEDIR=.
SOURCES := $(shell find $(SOURCEDIR) -name '*.go')

BINARY=roll

VERSION=1.0.0
BUILD_TIME=`date +%FT%T%z`

LDFLAGS=-ldflags "-X github.com/ariejan/roll/core.Build=`git rev-parse HEAD`"

.DEFAULT_GOAL: $(BINARY)

$(BINARY): $(SOURCES)
    go build ${LDFLAGS} -o ${BINARY} main.go

.PHONY: install
install:
    go install ${LDFLAGS} ./...

.PHONY: clean
clean:
    if [ -f ${BINARY} ] ; then rm ${BINARY} ; fi
```

github/ariejan/roll/version.go
```
package core

import "fmt"

type version struct {
    Major, Minor, Patch int
    Label               string
    Name                string
}

var Version = version{1, 2, 3, "dev", "Chuck Norris"}

var Build string

func (v version) String() string {
    if v.Label != "" {
        return fmt.Sprintf("Roll version %d.%d.%d-%s \"%s\"\nGit commit hash: %s", v.Major, v.Minor, v.Patch, v.Label, v.Name, Build)
    } else {
        return fmt.Sprintf("Roll version %d.%d.%d \"%s\"\nGit commit hash: %s", v.Major, v.Minor, v.Patch, v.Name, Build)
    }
}
```
[ref1](https://ariejan.net/2015/10/03/a-makefile-for-golang-cli-tools/)
[ref2](https://ariejan.net/2015/10/12/building-golang-cli-tools-update/)


---
# Complete Makefile for golang

Author: [Jon Eisen](https://gist.github.com/dnishimura/2961173)

```
# Makefile for a go project
#
# Author: Jon Eisen
# 	site: joneisen.me
# 	
# Targets:
# 	all: Builds the code
# 	build: Builds the code
# 	fmt: Formats the source files
# 	clean: cleans the code
# 	install: Installs the code to the GOPATH
# 	iref: Installs referenced projects
#	test: Runs the tests
#
#  Blog post on it: http://joneisen.me/post/25503842796
#

# Go parameters
GOCMD=go
GOBUILD=$(GOCMD) build
GOCLEAN=$(GOCMD) clean
GOINSTALL=$(GOCMD) install
GOTEST=$(GOCMD) test
GODEP=$(GOTEST) -i
GOFMT=gofmt -w

# Package lists
TOPLEVEL_PKG := whatever
INT_LIST := myinterface another/impl	#<-- Interface directories
IMPL_LIST := myimplementation another/pkg/impl	#<-- Implementation directories
CMD_LIST := mycmd1 another/pkg/mycmd1	#<-- Command directories

# List building
ALL_LIST = $(INT_LIST) $(IMPL_LIST) $(CMD_LIST)

BUILD_LIST = $(foreach int, $(ALL_LIST), $(int)_build)
CLEAN_LIST = $(foreach int, $(ALL_LIST), $(int)_clean)
INSTALL_LIST = $(foreach int, $(ALL_LIST), $(int)_install)
IREF_LIST = $(foreach int, $(ALL_LIST), $(int)_iref)
TEST_LIST = $(foreach int, $(ALL_LIST), $(int)_test)
FMT_TEST = $(foreach int, $(ALL_LIST), $(int)_fmt)

# All are .PHONY for now because dependencyness is hard
.PHONY: $(CLEAN_LIST) $(TEST_LIST) $(FMT_LIST) $(INSTALL_LIST) $(BUILD_LIST) $(IREF_LIST)

all: build
build: $(BUILD_LIST)
clean: $(CLEAN_LIST)
install: $(INSTALL_LIST)
test: $(TEST_LIST)
iref: $(IREF_LIST)
fmt: $(FMT_TEST)

$(BUILD_LIST): %_build: %_fmt %_iref
	$(GOBUILD) $(TOPLEVEL_PKG)/$*
$(CLEAN_LIST): %_clean:
	$(GOCLEAN) $(TOPLEVEL_PKG)/$*
$(INSTALL_LIST): %_install:
	$(GOINSTALL) $(TOPLEVEL_PKG)/$*
$(IREF_LIST): %_iref:
	$(GODEP) $(TOPLEVEL_PKG)/$*
$(TEST_LIST): %_test:
	$(GOTEST) $(TOPLEVEL_PKG)/$*
$(FMT_TEST): %_fmt:
	$(GOFMT) ./$*
```
