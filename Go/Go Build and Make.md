# Go Build and Make
---
# $GOPATH
- `src` and `pkg`
  - `/src/foo/bar.go`
  - `/pkg/OS_ARCH/foo/bar.a`

---
# Build
- first line comment `//+build linux,386 darwin,!cgo`
- [parameters](https://golang.org/pkg/go/build/)

---
# Makefile for Go

https://ariejan.net/2015/10/03/a-makefile-for-golang-cli-tools/

https://ariejan.net/2015/10/12/building-golang-cli-tools-update/
