### Introduction ###
Sometimes you need to search the FS to find a file by name. Drop the following function into your ~/.profile or ~/.bashrc file:

```bash
# Find files faster on a large FS
export LC_ALL=C

function kgrep2() {
    find ${1} | parallel --pipe -k -j+1 grep "${2}"
}
```

### Example Usage ###
```bash
source ~/.profile
kgrep "<directory>" "<string>"
```

```bash
kgrep ~/ "foo.txt"
```



