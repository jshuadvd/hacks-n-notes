# Shell / Unix

Shell and Unix notes

## How to make tarballs

> Unix command `tar`
> bundles files without compression.
> see [tar documentation](https://en.wikibooks.org/wiki/Guide_to_Unix/Commands/File_Compression)

- Supported in Unix environments.
- Can also `gzip`

### Modes
- `-c`  create an archive (files to archive, archive from files)
- `-x`  extract an archive (archive to files, files from archive)

### Options

- `-f` FILE  name of archive - must specify unless using tape drive for archive
- `-v` be verbose, list all files being archived/extracted
- `-z` create/extract archive with gzip/gunzip
- `-j` create/extract archive with bzip2/bunzip2
- `-J` create/extract archive with XZ

### To compress
> Compress (gzip) and package (tar) the directory myfiles to create myfiles.tar.gz:

`tar -czvf myfiles.tar.gz myfiles/`

### To uncompress

> Uncompress (gzip) and unpack compressed package, extracting contents from myfiles:

`tar -xzvf myfiles.tar.gz`

## How to check your memory processes

### Top memory consumers

- `top`

### Check how much memory is used vs free

- `free -m`

### Check all the memory each process is consuming
- `ps aux --sort -rss | head -n 15`

### kill an unresponsive process on Unix

- `ps aux | grep <service name>`
- find its process id (PID)
- `kill -9 PID`

### Check port use

- `sudo netstat -naplt | grep 8080`

### Check Node traffic on specific port

- `sudo tcpdump -A -i lo port 2354`


### to get unix my ip address

```sh
echo `ifconfig eth0 2>/dev/null|awk '/inet addr:/ {print $2}'|sed 's/addr://'`
```

### ssh

> Secure shell
