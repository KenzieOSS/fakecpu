# fakecpu
fakecpu is a script that can be used to change the CPU's name in /proc/cpuinfo to anything.

## Installation
```bash
git clone https://github.com/KenzieOSS/fakecpu
cd fakecpu
sudo cp fakecpu /usr/local/bin/
sudo chmod +x /usr/local/bin/fakecpu 
```


## Usage
```bash
sudo fakecpu <name>
sudo fakecpu AMD Ryzen 6990X3D 48-Core Processor
```
Make sure you have fastfetch installed

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
I made this script just for fun, it should be completely safe as you're just doing stuff to /proc/cpuinfo

there's also a bug where it will reset the name at times, I am too lazy to fix this
