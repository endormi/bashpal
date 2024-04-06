# Bashpal

Package for adding aliases and PATHs.

## Installation

> **NOTE**: The actual package resides in a private repository due to containing numerous binary files from builds. This is a mirror featuring important files.

Incorrect usage can disrupt your alias and `PATH` configurations. Use at your own risk.

```bash
sudo add-apt-repository ppa:endormi/ppapp &&
sudo apt update &&
sudo apt install bashpal
```

## Usage

Manpages:

```bash
man bashpal
```

By default, `-f` points to `~/.bash_aliases`, but it's customizable:

```bash
bashpal -a hello -c 'echo "hello"' -f hello.txt
```

Content of `hello.txt`:

```bash
alias hello='echo "hello"'
```

Adding a new `PATH`:

```bash
bashpal -p $PWD -f hello.txt
```

Updated content of `hello.txt`:

```bash
alias hello='echo "hello"'
export PATH=$PATH:/home/...
```

Using `-p`, `-a`, and `-c` simultaneously does not pose any issues:

```bash
bashpal -f test.txt -a test -c 'echo "test"' -p /test/folder
```

Content of `test.txt`:

```bash
alias test='echo "test"'
export PATH=$PATH:/test/folder
```

### Why?

I use this code in some of my projects. It's mostly for my own use, but you can give it a try if you're okay with the risks. Also, I made this package to learn how to create, build, and publish Debian packages.
