# Tamper
A simple system for checking for file changes on a disk. This script will create a hash of every file in a directory and compare it to a historical list, allowing you to see which files have been changed since the last time the script was run.

## Usage
To use tamper, simply type
```shell
$ tamper -d <directory>
```
In the example above, `<directory>` refers to the directory that you want to examine. If the `-d <directory` flag is ommitted, tamper will default to the current user's home directory.

The first time you run the script you will get an output looking something like this:
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

The following files have been modified:
/home/<user>/tamper/test/do_not_modify

The following files have been added:
/home/<user>/tamper/test/file
/home/<user>/tamper/test/schedule

The following files have been deleted:
/home/<user>/tamper/test/document
```

### Reset
If you want to reset the tracking for a folder, creating a clean slate, use:
```shell
$ tamper -r [-d <directory>]
```
This will remove the logs of the previous runs, forcing tamper to accept the current directory as the original. This doesn't alter any of your files, just resets the tracking

### Help
If ever you're in doubt, simply use
```shell
$ tamper -h
```
to see all of the arguments available

## Dependencies
Tamper makes use of [shflags](https://github.com/kward/shflags) for argument handling, but will download this automatically. Just make sure you have an internet connection on your first run!
