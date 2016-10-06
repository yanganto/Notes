# Ready to Go with Web
---

# Basic

## Books and Articles
- [The little Go book](http://openmymind.net/The-Little-Go-Book/)
- [GoLang Note](https://polor10101.gitbooks.io/golang_note/content/defer_panic_recover.html)
- [Array, Slice, Map, Set](https://se77en.cc/2014/06/30/array-slice-map-and-set-in-golang/)
- `godoc -http:=9000`

## Commands
- `$GOPATH`
- `go get github/someone/packages`
- `go run main.go`
- [Ref](https://github.com/astaxie/build-web-application-with-golang/blob/master/zh/01.3.md)


## Naming
- a name is exported if it begins with a **capital** letter.

---

# IDE & Tools

## Atom
- go-plus packages
  - go-degug ... etc

1. set up $GOPATH
2. ```apm install go-plus```
3. Press `F5`

## Vim
- [vim-go](https://github.com/fatih/vim-go)
- vim-golang (legacy)
- ref: [vimgo development environment](https://blog.gopheracademy.com/vimgo-development-environment/)

---

# Web Framework
- revel - **Not** follow the Go style
- beego - popular, MVC, but **heavy** with ORM, Session Cache
- [Martini](https://github.com/go-martini/martini) (2013 Oct, 8738 stars) - lightweight, but not maintain
  - [Negroni](https://github.com/urfave/negroni) (2014 May, 3966 stars)
     > If you like the idea of Martini, but you think it contains too much magic, then Negroni is a great fit.

  - ref: [My Thoughts on Martini](https://codegangsta.io/blog/2014/05/19/my-thoughts-on-martini/)
  - ref: [Three reasons you should not use Martini](https://stephensearles.com/?p=254)

---

#  Essential Middlewares w/ Negroni
- [render](https://github.com/unrolled/render)
  - support HTML, JSON(w/o Streaming), JSONP, XML, Binary, Text
  - using [html/template](https://golang.org/pkg/html/template/)

---

# Example
  - GoWithWeb.tgz
  - `go run main.go`
  - `/` is the main handler in main.go
  - `/home` is the home handler in handler/home.go use template/base.tmpl
  - `/Go.png` get the file Go.png from public folder
