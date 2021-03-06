---

## Unix and Log Reading

### Khoa Tran

---

## Agenda

- Basic *nix
- Aliases + Tricks
- Processes
- ssh, scp, and permissions
- Reading and digesting logs
- Questions?

---

## Basic \*nix

- pwd, cd, ls, rm, mv
- more/less, head/tail to view files
- touch/cat/echo to create/print/write to file
- man / tldr: view the man-ual for a certain command
- Ctrl+K/Ctrl+U, Ctrl+A/Ctrl+E, etc.

+++

## History

- history | more
- `export HISTTIMEFORMAT='%F %T '` to see timestamp
- Ctrl+R to search thru history, Ctrl+G to get out
- !! or Ctrl + P to execute last command
- !X to execute commands at X position in history

+++

## Wildcard and Redirection

- `rm -rf ~/*`
- `<` redirect from stdin
- `>` redirect from stdout, replacing existing content
- `>>` redirect from stdout, appending after existing content

+++

## Pipe

- Redirect the output of one command into another
- `ls -l | grep ^d | wc -l`
- Print the number of subdirectories in the current directory
- Combining tail and grep can be very powerful for reading logs

---

## Bash Aliases and Environment Variables

- alias short = 'LONG COMMAND', e.g. .. = 'cd ..'
- For lasting effect, put in ~/.bash_aliases or ~/.bash_profile
- Similarly, export VAR = 'value'
- `echo $VAR`
- Sourcing with `source`

+++

## Git Aliases

- git alias new_cmd = 'LONG COMMAND'
- Better, put in ~/.gitconfig

```
[alias]
    st = status
    cl = log --pretty --date=relative
```

- I'm lazy, so I use Bash aliases, e.g. `alias st = git status`

+++

## (Z)umping around

- z https://github.com/rupa/z
- ag == find+grep on steroid

---

## Processes

- ps
- psaux on Update
- kill and pkill

+++

## Foreground & Background

- Ctrl+C to terminate
- Ctrl+Z to suspend
- fg, bg, jobs, disown %1 OR nohup

+++

![](https://i.imgur.com/XyPyVUp.png)

---

## SSH, SCP, and SFTP

- username/password or public-private keypair
- `scp file server:/path/on/server`

+++

## Permissions

- `ls -lah` to see details
- `chown` changes owner
- `chgrp` changes groups
- `chmod` changes permission
- 4: read, 2: write, 1: execute
- What's 660? How about 744?

---

## Reading logs and csvs

- tail -f to see running log
- Find a pattern with `grep` or `ag`
- Combine together to see only items relevant to you

+++

## sed

- `sed -n 16224,16240p filename`

+++

## csv

- Manipulating csv with `cut` and `sort`

```
1111,2222,3333,4444
aaaa,bbbb,cccc,dddd

$ cut --complement -f 3 -d, inputfile
1111,2222,4444
aaaa,bbbb,dddd

$ cut -d , -f 1-2,4-, inputfile
```

---

## What else?

- vim/tmux living in terminal
- regular expression! power up `sed` and `awk`

---

## Questions?

Thanks!