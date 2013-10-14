autotorrent
===========

Given an input torrent, it will scan your collection for the files in the torrent.
If all the files are found, a folder with links to all the files will be created.

The idea is to be able to organise your collection as you want to and still be able
to seed with the folder structure required by the torrent.

Install
-------

    virtualenv autotorrent-env
    autotorrent-env/bin/pip install git+https://github.com/JohnDoee/autotorrent.git

Configuration
-------------

All settings can be found and changed in autotorrent.conf, this file must reside in the
same folder as autotorrent is executed from.

### general

* db - Path to the database file
* store_path - Folder where the virtual folders seeded, resides
* ignore_files - A comma seperated list of files that should be ignored (does not support wildcard)
* rtorrent_url - URL to rtorrent, must be to the XMLRPC server
* label - Label added to torrents when added to rtorrent (used in rutorrent only)

### disks

A list of disks where to build the search database from.

The keys must be sequential, i.e. disk1, disk2, disk3 etc.

Instructions
------------

Start by installing and configuring.

Step 1, build the database with `autotorrent -r`, this can take some time.

Step 2, have some torrents ready and run `autotorrent -a folder/with/torrents/*.torrents`, this command will spit out how it went with adding the torrents.

And you're good to go, it is possible to verify the integrity of the currently seeded torrents with `autotorrent -v`

Limitations
-----------

* Only works with rtorrent
* Probably only works on Linux

License
-------

MIT, see LICENSE