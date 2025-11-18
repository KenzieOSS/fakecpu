# fakecpu
fakecpu is a script that can be used to change the CPU's name in /proc/cpuinfo to anything.

## Installation
```bash
git clone https://github.com/KenzieOSS/fakecpu
cd fakecpu
sudo cp fakecpu /usr/local/bin/
sudo chmod +x /usr/local/bin/fakecpu 
```

## NOTICE:
This script MIGHT make flatpak applications unusable USE WITH CAUTION

TO FULLY DISABLE:
```bash
sudo umount /proc/cpuinfo
sudo systemctl disable --now fake-cpuinfo.service 2>/dev/null || true
```

## Usage
```bash
sudo fakecpu <name>
sudo fakecpu AMD Ryzen 6990X3D 48-Core Processor
```
Having fastfetch installed is preferrable, but not needed

(if you're using brackets or or other special characters use quotes when setting the name)

to disable
```bash
sudo fakecpu off
```

Sometimes you may get an error like
```bash
mount: /proc/cpuinfo: move_mount() failed: No such file or directory.
       dmesg(1) may have more information after failed mount system call.
```
just run the script again, it *should* just work

## PSA:
I made this script just for fun, it should be *mostly* safe as you're just doing stuff to /proc/cpuinfo (besides potentially screwing with sandboxed apps)
