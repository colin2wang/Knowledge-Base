# Golang

## Development Setup

### Install golang.org/x

```shell script
mkdir -p %GOPATH%/src/golang.org/x/
cd %GOPATH%/src/golang.org/x/

git clone https://github.com/golang/net.git net
go install net

git clone https://github.com/golang/sys.git sys
go install sys

git clone https://github.com/golang/text.git text
go install text

git clone https://github.com/golang/lint.git lint
go install lint

git clone https://github.com/golang/tools.git tools
go install tools

git clone https://github.com/golang/crypto.git crypto
go install crypto
```

### Set Go Proxy for China
```shell script
go env -w GOPROXY=https://goproxy.cn,direct
```