# zchi
[![Go Reference](https://pkg.go.dev/badge/github.com/Lavalier/zchi.svg)](https://pkg.go.dev/github.com/Lavalier/zchi)

A [zerolog](https://github.com/rs/zerolog) Logger/Recoverer middleware for [chi](https://github.com/go-chi/chi).

![carbon](https://user-images.githubusercontent.com/6241454/150070893-8cc19034-7c66-4a7d-a245-59fc64125043.png)

## Install
`go get -u github.com/Lavalier/zchi`

## Usage
```go
package main

import (
	"net/http"

	"github.com/Lavalier/zchi"
	"github.com/go-chi/chi/v5"
	"github.com/rs/zerolog/log"
)

func main() {
	r := chi.NewRouter()
	r.Use(zchi.Logger(log.Logger))
	r.Get("/", func(w http.ResponseWriter, r *http.Request) {
		w.Write([]byte("test"))
	})
	http.ListenAndServe(":8080", r)
}

```
