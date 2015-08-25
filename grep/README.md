### Fast File Search ###
Sometimes you need to search the FS to find a file by name. Drop the following function into your ~/.profile or ~/.bashrc file, source it, and speed up your search. Note that you will need the [GNU Parallel](http://www.gnu.org/software/parallel/) installed.

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



