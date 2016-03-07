# Shell / Unix

Shell and Unix notes

## How to make tarballs

> Unix command `tar`
> bundles files without compression.

- Supported in Unix environments.
- Can also `gzip`

### Modes
- `-c`  create an archive (files to archive, archive from files)
- `-x`  extract an archive (archive to files, files from archive)

### Options

- `-f` FILE  name of archive - must specify unless using tape drive for archive
- `-v`       be verbose, list all files being archived/extracted
- `-z`       create/extract archive with gzip/gunzip
- `-j`       create/extract archive with bzip2/bunzip2
- `-J`       create/extract archive with XZ