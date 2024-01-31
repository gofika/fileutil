[![codecov](https://codecov.io/gh/gofika/fileutil/branch/main/graph/badge.svg)](https://codecov.io/gh/gofika/fileutil)
[![Build Status](https://github.com/gofika/fileutil/workflows/build/badge.svg)](https://github.com/gofika/fileutil)
[![go.dev](https://img.shields.io/badge/go.dev-reference-007d9c?logo=go&logoColor=white)](https://pkg.go.dev/github.com/gofika/fileutil)
[![Go Report Card](https://goreportcard.com/badge/github.com/gofika/fileutil)](https://goreportcard.com/report/github.com/gofika/fileutil)
[![Licenses](https://img.shields.io/github/license/gofika/fileutil)](LICENSE)

# fileutil

golang file utils for common use


## Basic Usage

### Installation

To get the package, execute:

```bash
go get github.com/gofika/fileutil
```

### Example

```go
package main

import (
	"fmt"
	"github.com/gofika/fileutil"
)

func main() {
	name := "foo/bar.txt"
	data := []byte("Hello")
	// write data to file. will create dir: foo
	err := fileutil.WriteFile(name, data)
	if err != nil {
		fmt.Printf("Write file failed. err: %s\n", err.Error())
		return
	}
	// check file exist
	if !fileutil.IsExist(name) {
		fmt.Printf("file %s not exist.\n", name)
		return
	}
	// clear temp file
	fileutil.DeleteAll("foo")
}
```
