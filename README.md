# Docker Exec Image: Python 2

A Dockerfile describing an container capable of executing Python 2 source files.

# Build

```sh
git clone https://github.com/docker-exec/python2.git
docker build -t dexec/python2 .
```

# Usage

In a directory containing a script e.g. foo.py, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.py:/tmp/dexec/build/foo.py \
    dexec/python2 foo.py
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.py:/tmp/dexec/build/foo.py \
    dexec/python2 foo.py \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```
