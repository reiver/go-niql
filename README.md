# go-niql

Package **niql** (pronounced "*nickel*") provides parsing for a SQL-like query language (also) called "NiQL",
for the Go programming language.


## Documention

Online documentation, which includes examples, can be found at: http://godoc.org/github.com/reiver/go-niql

[![GoDoc](https://godoc.org/github.com/reiver/go-niql?status.svg)](https://godoc.org/github.com/reiver/go-niql)


## Example Go code
```
code := `SELECT first_name, last_name FROM LOAD('table10.csv') WHERE city = 'Vancouver'`
reader := strings.NewReader(code)

parser := NewParser(reader)

stmt, err := parser.Parse()
```


## Example NiQL
```
SELECT first_name, last_name FROM LOAD('table10.csv') WHERE city = 'Vancouver'
```


# Alternative NiQL Syntax
NiQL also has a shell-like piping syntax that can be used as an alternative to the
SQL style syntax.

For example:
```
from load('table10.csv') | where city = 'Vancouver' | select first_name, last_name
```
