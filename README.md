# dirt

Dirt stands for **dir**ectory **t**raversal. It is a library and a binary which provides functionality to traverse directories in manys ways.

# Working

Dirt binary:

```
dirt <root_dir> [-c|--ctime] [-m|--mtime] [-a|--atime] [-r|--reverse]
```

For instance,

```
dirt $HOME -a
```

will print contents to the deepest directory sorted by access time of files.

Example:

```
$ tree
.
├── dir1
│   ├── nested_file1
│   └── nested_file2
├── file1
└── file2

1 directory, 4 files
$ dirt . -a
./dir1/nested_file2
./file2
./file1
./dir1/nested_file1
```

Above, `./dir1/nested_file2` was accessed most recently so it was on the top.


Helpful links:
- [std::fs::read_dir](https://doc.rust-lang.org/std/fs/fn.read_dir.html)
- [std::fs::MetaData](https://doc.rust-lang.org/std/fs/struct.Metadata.html#method.accessed)
- [std::os::unix::fs::MetadataExt](https://doc.rust-lang.org/std/os/unix/fs/trait.MetadataExt.html)





