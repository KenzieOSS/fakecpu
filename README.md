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
sudo fakecpu off
```

OR MANUALLY

```bash
sudo umount /proc/cpuinfo
sudo systemctl disable --now fake-cpuinfo.service 2>/dev/null || true
sudo rm -f /etc/systemd/system/fake-cpuinfo.service
sudo systemctl daemon-reload 2>/dev/null || true
sudo rm -f /etc/fake-cpuinfo /etc/real-cpu-name 2>/dev/null || true
```

## Usage
```bash
sudo fakecpu <name> [OPTIONS]

Options:
  --cores, -c <n>      Set fake core count
  --mhz, -m <n>        Set fake CPU MHz
  --cache <size>       Set fake cache size
  --persist, -p        Make changes persist across reboots
  off                  Disable fakecpu and delete made files, you might need to run this twice for it to work
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
