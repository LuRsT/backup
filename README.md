# backup

Copy file(s) with a new extension (.old) to avoid disasters

Tired of copying config files before making some changes that may break the
whole internet? Afraid you might mess up and place the backup file in /dev/null
forever?

`backup` comes to the rescue, with an intuitive interface that is as simple as:
passing the file name(s) to it and it prints out the list of the created
duplicates. That's it, it just copies files with the extension ".old" on the
same directory of the original file.

Examples:

```console
    $ ls
    file.cfg
    $ backup file.cfg
    file.cfg.old
    $ ls
    file.cfg file.cfg.old
    $ rm *
    $ touch file{1..5}.cfg
    $ ls
    file1.cfg  file2.cfg  file3.cfg  file4.cfg  file5.cfg
    $ backup file*
    file1.cfg.old
    file2.cfg.old
    file3.cfg.old
    file4.cfg.old
    file5.cfg.old
```

## Setup

#### Quick install

```console
    $ curl https://raw.githubusercontent.com/LuRsT/backup/master/backup > ~/bin/backup
    (Examine ~/bin/backup)
    $ chmod +x ~/bin/backup
```

Note: You should have `~/bin` in your `$PATH` for this to work.


## Final notes

You might say that this is an over complication of `cp file{,.old}` and you
are correct, this is an overcomplication of cp + expansions, I created this
for two reasons, to avoid mistakes like `cp file{,old}` that are easy to
overlook, and for people who don't know and don't want to know about bash
expansions.

