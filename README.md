# go-talib

[![GoDoc](http://godoc.org/github.com/maurodelazeri/go-talib?status.svg)](http://godoc.org/github.com/maurodelazeri/go-talib) 

A pure [Go](http://golang.org/) port of [TA-Lib](http://ta-lib.org)

## Install

Install the package with:

```bash
go get github.com/maurodelazeri/go-talib
```

Import it with:

```go
import "github.com/maurodelazeri/go-talib"
```

and use `talib` as the package name inside the code.

## Example

```go
package main

import (
	"fmt"
	"github.com/maurodelazeri/go-talib"
)

// Standard Deviation
func main() {
	x := []float64{22.2,22.33,21.22,23.22,21.00}
        fmt.Println(talib.StdDev(x, 5, 2))
	[0 0 0 0 1.611339815184824]
}
```


```
package main

import (
	"fmt"
	"github.com/markcheno/go-quote"
	"github.com/markcheno/go-talib"
)

func main() {
	spy, _ := quote.NewQuoteFromYahoo("spy", "2016-01-01", "2016-04-01", quote.Daily, true)
	fmt.Print(spy.CSV())
	rsi2 := talib.Rsi(spy.Close, 2)
	fmt.Println(rsi2)
}
```
