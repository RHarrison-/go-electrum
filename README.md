# go-electrum [![GoDoc](https://godoc.org/github.com/d4l3k/go-electrum?status.svg)](https://godoc.org/github.com/d4l3k/go-electrum)
A pure Go [Electrum](https://electrum.org/) bitcoin library. This makes it easy to write bitcoin based services using Go without having to run a full bitcoin node.

This is very much WIP and has a number of unimplemented methods. This will eventually be rewritten into a more Go-esque library and handle wallet generation.

## Usage
```bash
go get -u "github.com/d4l3k/go-electrum"
```

```go
package main

import (
  "log"
  "github.com/d4l3k/go-electrum"
)

func main() {
	node := electrum.NewNode()
	if err := node.ConnectTCP("electrum.dragonzone.net:50001"); err != nil {
		log.Fatal(err)
	}
	balance, err := node.BlockchainAddressGetBalance("1NS17iag9jJgTHD1VXjvLCEnZuQ3rJDE9L")
	if err != nil {
		log.Fatal(err)
	}
	log.Printf("Address balance: %+v", balance)
}
```
See [example/](https://github.com/d4l3k/go-electrum/tree/master/example) for more.

# License
go-electrum is licensed under the MIT license.

Made by [Tristan Rice](https://fn.lc).
