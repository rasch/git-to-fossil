# git-to-fossil

[![builds.sr.ht status](https://builds.sr.ht/~rasch/git-to-fossil.svg)](https://builds.sr.ht/~rasch/git-to-fossil?)

Import a Git repository into Fossil.

## Usage

```sh
# directory must be a Git repository
cd <directory>
git-to-fossil
```

If the current directory is the root of a Git repository (contains a
`.git` directory), then the Fossil repository is created at
`../_fossil/<directory>.fossil`. If the Fossil repository already
exists, then an incremental import is performed.

## Installation

```sh
# download script
curl -O https://git.sr.ht/~rasch/git-to-fossil/blob/main/git-to-fossil

# make it executable
chmod +x git-to-fossil

# move script to somewhere in "$PATH" such as:
mv git-to-fossil /usr/local/bin/
```

## Configuration

Fossil determines the user for the newly created repository from the
`$USER` environment variable. In this script, `$GIT_USER` is used with
a fallback to `$USER`. If neither variable is set, then the output of
the `whoami` command is used.
