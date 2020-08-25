# dotfiles-and-hints
I'm fed up looking up Linux set up instructions on the internet... Time to make my own reference.

### Change screenshot default folder
```
$ gsettings set org.gnome.gnome-screenshot auto-save-directory "[complete-path-to-new-directory]"
```

### Change username, groupname, and ~$ dir
First kill everything (ideally you'd do this from a different user or superuser account)
```
$ sudo pkill -u [old-username]
$ sudo pkill -9 -u [old-username]
$ sudo usermod -l [new-username] [old-username]
```
Change the Home directory name
```
$ sudo usermode -d /home/[new-username] -m [new-username]
```
Change the groupname
```
$ sudo groupmod -n [new-username] [old-username]
```

### Change hostname
```
$ sudo hostnamectl set-hostname [new-hostname]
```
### Clear cache

```
$ echo 1 > /proc/sys/vm/drop_caches
```

## Memory adjustments

### See and adjust swappiness
```
$ cat /proc/sys/vm/swappiness
$ sysctl vm.swappiness=[0-100, most recommend 10 (default is 60)]
```

### See and adjust inode cache
```
$ cat /proc/sys/vm/vfs_cache_pressure
$ sysctl vm.vfs_cache_pressure=50 (default is 100)
```

### Do both of the above permanently
Using your favorite text editor (in my case vim)
```
$ sudo vim /etc/sysctl.conf
```
at the bottom add the following lines:
```
vm.swappiness=10
vm.vfs_cache_pressure=50
```
then run this line:
```
$ sudo sysctl -p
```


## Websites
* [Speed up Linux Mint](https://easylinuxtipsproject.blogspot.com/p/speed-mint.html#ID1.1)
