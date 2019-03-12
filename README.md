### bitset
---
https://github.com/willf/bitset

```go
package main

import (
  "fmt"
  "math/rand"
  
  "github.com/willf/bitset"
)

func main() {
  fmt.Printf()
  var b bitset.BitSet
  
  for i := 0; i < 100; i++ {
    card1 := uint(rand.Intn(52))
    card2 := uint(rand.Intn(52))
    b.Set(card1)
    if b.Test(card2) {
      fmt.Println("Go Fish!")
    }
    b.Clear(card1)
  }
  
  b.Set(10).Set(11)
  
  for i, e := b.NextSet(0); e; i, e = b.NextSet(i + 1) {
    fmt.Println("The following bit is set:", i)
  }
  if b.Intersection(bitset.New(100).Set(10)).Count() == 1 {
    fmt.Println("Intersection works.")
  } else {
    fmt.Println("Intersection doesn't work???")
  }
} 
```

```sh
go get github.com/willf/bitset
make help
make qa
```

```
```


