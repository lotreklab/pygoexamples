# Extend Python in Go Examples

## What you need

For this experiment you need:

- Python 3.8 + Python source code
- Golang 1.13.5

Setup `LIBRARY_PATH` and `PKG_CONFIG_PATH` on your system.

For me on Mac is

```sh
export PKG_CONFIG_PATH=/Library/Frameworks/Python.framework/Versions/3.8/lib/pkgconfig/
export LIBRARY_PATH=/Library/Frameworks/Python.framework/Versions/3.8/lib
```

**You may need to change the path and the preamble in any .c file, pay attention!**

## Install dependencies

If you want to run examples please install Python dependencies in your virtualenv

```sh
pip install -r requirements.txt
```

## Chapter 1 - From C to Python

In this chapter there's a simple example on how to extend Python using C language. This is a good starting point to see CPython at work with a simple function that sums two numbers.

## Chapter 2 - From Go to Python

In this chapter there's a simple example on how to extend Python using Go and [cgo](https://golang.org/cmd/cgo/). With cgo we can use any C code using the preamble and `import C` statement

    // #include <stdio.h>
    // #include <errno.h>
    import "C"

so we can use CPython structures and objects (e.g. `C.PyObject`)

## Chapter 3 - Performances

In this chapter there are two examples:

- Hello: in this example we try to say "hello!" using Python, C extension and Golang
- Sum: in this example we try to sum numbers from 0 to 900000

At the end of each execution there's the time spent running the code.

## Chapter 4 - Parallel execution

I love Golang to run parallel code! Python GIL limits parallel execution in Python, in Golang environment there's no limitation! At the end of each execution there's the time spent running the code.
