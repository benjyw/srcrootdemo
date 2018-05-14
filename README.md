Run `./pants binary foo/bar:bin`

Which yields `dist/bin.pex`

And:

`unzip -t dist/bin.pex`

yields, as expected:

```
    testing: .bootstrap/_pex/__init__.py   OK
...
    testing: .bootstrap/pkg_resources/extern/__init__.pyc   OK
    testing: PEX-INFO                 OK
    testing: __main__.py              OK
    testing: __main__.pyc             OK
    testing: foo/__init__.py          OK
    testing: foo/bar/__init__.py      OK
    testing: foo/bar/baz.py           OK
    testing: foo/bar/baz.pyc          OK

```

And running the pex works:

```
$ ./dist/bin.pex 
Baz
```
