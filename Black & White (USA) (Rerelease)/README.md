# Game

- Black & White (USA) (Rerelease)

## How to convert cue/bin to iso ;)

```bash
bchunk bw.bin bw.cue bw
```

_You need to install[bchunk](http://he.fi/bchunk/) on your system_

## Mount cdrom

```bash
sudo mount -o loop "bw.iso" "/mnt/cdrom"
```

or

```bash
sudo mount -t iso9660 -o loop "bw.iso" "/mnt/cdrom"
```