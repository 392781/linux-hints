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
