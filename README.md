# wvessel - a vessel wrapper

**wvessel** is a script that wraps [vessel](https://github.com/dfinity/vessel), a [motoko](https://sdk.dfinity.org/docs/language-guide/motoko.html) package management tool, to ease the use of different versions per project or just to portably download and use the one that work with your sources.

## How to use

1. Download a copy of the `wvessel` script [from the release page](https://github.com/metavercity/wvessel/releases)
2. Copy `wvessel` to the root of your vessel-dependent project
3. Just use `./wvessel` instead of `vessel`
4. Change the default or decide and configure the vessel release your project will be depending:

List the available vessel release tags:

```bash
./wvessel --list
```

Set the tag of the vessel release to use:

```bash
./wvessel --use v0.6.2
```

Or just edit `.vessel.release` to manually specify the tag.

When the file is missing, the script connects to github to lookup the latest vessel release tag and if that fails 
it falls back to the latest already downloaded and cached binary.

A cache of tag-binaries is kept in your home directory.

## Advanced usage:

If you will be using this tool in different local projects, you may prefer to include a `vessel` executable script 
in your `PATH`, that will in turn execute the `wvessel` script from your current working directory, or the first that appears
in a parent folder.

To achieve that, you could put these lines in `~/bin/vessel`:

```bash
#!/bin/bash
wv="wvessel"; while ! test -e "$wv" && test "$PWD" != "/"; do cd ..; done; if test -x "$wv"; then echo ./$wv $*; fi
```
Notice that if `wvessel` is not found in the current folder or any of the parent folders, the above script does nothing.

Do not forget to set execute permissions with:

```bash
chmod +x ~/bin/vessel
```

## Todo

* The script has only being tested and know to work on linux.
* The scripts assumes that `bash` and `curl` are available.

## Find out more

**Vessel** is a package management tool for Motoko. See https://github.com/dfinity/vessel 

**Motoko** is a simple language for writing Internet Computer (IC) actors. See https://github.com/dfinity/motoko

To find out more about **DFINITY Internet Computer** see https://dfinity.org/

**Metavercity** is a project still being cooked, more information will be available when the time comes.

