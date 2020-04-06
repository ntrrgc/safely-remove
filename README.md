This is a simple tool to eject external media from command line in Linux operating systems, in a similar fashion to what happens when you click the eject button in a file explorer such Nautilus.

The command will find the drive associated with the path provided as argument (resolving mount endpoints if necessary), explore the tree of block devices contained within the drive, unmount all filesystems within them, lock all contained crypto backing devices, eject the media, and if the media is not removable, turn off the drive.

This is all done with the same UDisks2 DBus interface that file managers use, so it doesn't require any more priviledges than those.

This has been tested with:

* USB thumb drives.
* External hard drives with luks encryption.
* SD cards with multiple partitions.
* CD/DVD drives.

## Requirements

 * Python 3.6+
 * pydbus

## Usage

```
usage: safely-remove [-h] [--raw-device] [-d] path

Safely ejects a device, just like Nautilus does. Doesn't require root.

positional arguments:
  path          Path of the device to unmount, be it raw (e.g. /dev/sdc1), a
                mount point (/var/mount/...) or a path within a mount point.

optional arguments:
  -h, --help    show this help message and exit
  --raw-device  Interpret PATH as a device path, don't try to resolve a mount
                point.
  -d, --debug   Show debug info.
```

## License

MIT License.

Copyright 2020 Alicia Boya García

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
