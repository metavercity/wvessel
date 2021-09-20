# wvessel - a vessel wrapper

**wvessel** is a script that wraps [vessel](https://github.com/dfinity/vessel), a [motoko](https://sdk.dfinity.org/docs/language-guide/motoko.html) package management tool, to ease the use of different versions per project or just to portably download and use the one that work with your sources.

## How to use

1. Download a copy of the `wvessel` script [from the release page](https://github.com/metavercity/wvessel/releases)
2. Remove the original `vessel` binary or move it out of your `PATH`
3. Copy the wrapper script `wvessel` as `vessel` and include in your `PATH`
4. Make sure the new `vessel` script has execute permission: `chmod +x vessel`
5. Use `vessel` from command line or the tools as you would normally do
6. Optionally, decide and configure the vessel release tag your project will be depending:

List the available vessel release tags:

```bash
vessel --list
```

Set the tag of the vessel release to use:

```bash
vessel --use v0.6.2
```

Or just edit `vessel.tag` to manually specify the version tag.

When the file is missing, the script connects to github to lookup the latest vessel release tag and if that fails 
it falls back to the latest already downloaded and cached binary.

A cache of binaries (one per tag) is kept in your home directory.

## Todo

* The script has only being tested and know to work on linux.
* The scripts assumes that `bash` and `curl` are available.

## Find out more

**Vessel** is a package management tool for Motoko. See https://github.com/dfinity/vessel 

**Motoko** is a simple language for writing Internet Computer (IC) actors. See https://github.com/dfinity/motoko

To find out more about **DFINITY Internet Computer** see https://dfinity.org/

**Metavercity** is a project still being cooked, more information will be available when the time comes.

