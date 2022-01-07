# Commands

## Auto explainable commands
> go version
> go env
> go help

## Running a go file
> go run <file name>

eg: go run *.go

> go build
* for an executable:
** builds the file
** reports errors, if any
** if there are no errors, it puts an executable into the current folder

* for a package:
** builds the file
** reports errors, if any
** throws away binary
> go installv
for an executable:
compiles the program (builds it)
names the executable 
mac: the folder name holding the code
windows: file name
puts the executable in workspace / bin
$GOPATH / bin
for a package:
compiles the package (builds it)
puts the executable in workspace / pkg
$GOPATH / pkg
makes it an archive file
flags
 -race


## See all dependencies
> go list -m all

## Upgrade dependencies
> go list -m -versions <import>
