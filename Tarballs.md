# Tarballs
#wiki #cs3377 

**Tarballs** are another term for a *tape archive*, which is a group of files that are collected as one.

Tarballs separate the compression from the actual archive. This is why you will see tarballs with file extensions `.tar.gz` and `.tar.bz2`, where `gz` and `bz2` represent different types of compression.

## Creating Tarballs
1. Change directory to the parent folder of the one you wish to compress
2. Use `tar cfvz archive.tar.gz myfolder`, where `archive.tar.gz` is your output file and `myfolder` is the source folder

#### Argument Meanings
| Argument             | Meaning                            |
| -------------------- | ---------------------------------- |
| `-c, --create`       | create a new archive               |
| `-f, --file=ARCHIVE` | use archive file or device ARCHIVE |
| `-v, --verbose`      | verbosely list files processed     |
| `-z, --gzip`         | filter the archive through gzip    |

The dashes are not necessary.

For more information and options, refer to `man tar`.
