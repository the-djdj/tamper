# Tamper
A simple system for checking for file changes on a disk. This script will create a hash of every file in a directory and compare it to a historical list, allowing you to see which files have been changed since the last time the script was run.

## Usage
To use tamper, simply type
```shell
$ tamper -d <directory>
```
In the example above, `<directory>` refers to the directory that you want to examine. The first time you run the script you will get an output looking something like this:
```
$ tamper -d ~
Searching for files
Writing tamper log to /home/<user>/.tamper/Mon_30_Feb_2020_15:07:55_
Run tamper again to detect changes.
```
Once there has been some activity in your folder, the output will start to look more like this:
```
$ tamper -d ~
Searching for files
Writing tamper log to /home/<user>/.tamper/Mon_30_Feb_2020_15:09:42_
The following files have been added/modified:
/home/danj/tamper/test/file
/home/danj/tamper/test/schedule
The following files have been deleted:
/home/danj/tamper/test/document
```

## Dependencies
Tamper makes use of [shflags](https://github.com/kward/shflags) for argument handling, but it will download this automatically. Just make sure you have an internet connection on your first run!
