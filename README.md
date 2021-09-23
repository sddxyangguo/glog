## 这个版本是copy的CodyGuo同学的 https://github.com/CodyGuo/glog
## 拷贝过来只是为了修改方便，请不要fork我。 直接fork CodyGuo的原版，支持原作者
## 如果你看到这些文字，请点击 https://github.com/CodyGuo/glog 看作者的。
## 这里是个人学习修改版本，一旦你fork回去自己用就可能程序出错。 


## Golang log library

[![godoc](http://img.shields.io/badge/godoc-reference-blue.svg?style=flat)](https://godoc.org/github.com/Lizhengyan/glog) [![build status](https://img.shields.io/travis/Lizhengyan/glog/master.svg?style=flat-square)](https://travis-ci.org/Lizhengyan/glog)

Package glog implements a log infrastructure for Go.

## Example

Let's have a look at an [example](examples/main.go) which demonstrates most
of the features found in this library.

```go
package main

import (
	"os"

	"github.com/Lizhengyan/glog"
)

func main() {
	glog.Debug("hello debug")
	glog.Info("hello info")

	customLog := glog.New(os.Stdout,
		glog.WithLevel(glog.TRACE),
                glog.WithLevelLength(4),
		glog.WithFlags(glog.LglogFlags),
		glog.WithPrefix("[customLog] "))

	customLog.Trace("hello trace")
	customLog.Debug("hello debug")
	customLog.Info("hello info")
	customLog.Notice("hello notice")
	customLog.Warning("hello warning")
	customLog.Error("hello error")
	customLog.Critical("hello critical")
}
```

## Installing

### Using *go get*
    $ go get github.com/Lizhengyan/glog

You can use `go get -u` to update the package.

## Go test
    $ go test -bench . -benchmem
    
![image](<doc/benchmem.png>)

## Documentation

For docs, see http://godoc.org/github.com/Lizhengyan/glog or run:

    $ godoc github.com/Lizhengyan/glog
