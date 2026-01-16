# `windows-terminal`
Some windows terminal settings, mostly keybindings.

## Setup your settings directory as a repository tracking this repo
```bash
# this may be already created if you're using my nixos-config
WINDOWS_USERNAME=<your windows username>
cd /mnt/c/Users/$WINDOWS_USERNAME/AppData/Local/Packages/Microsoft.WindowsTerminal_8wekyb3d8bbwe/LocalState

# setup repo
git init
# use ssh link if you prefer
git remote add origin https://github.com/tlovell-sxt/windows-terminal 
git branch -m main
git fetch

# backup your settings.json
cp settings.json settings.json.bak

# sync up with main
git reset --hard origin/main
```

You will also want to set up an alias to `cd` into this repo.
This will already exist if you use my nixos-config.

*In `.bashrc`*
```bash
export WINDOWS_USERNAME=<your windows username>
alias windows-terminal-config="cd /mnt/c/Users/$WINDOWS_USERNAME/AppData/Local/Packages/Microsoft.WindowsTerminal_8wekyb3d8bbwe/LocalState"
```

## Keybinding Cheatsheet
| Key | Action |
| --- | --- |
| `alt+num` | switch to tab `num` |
| `alt+` vim direction (`h`, `j`, `l`) | move pane focus |
| `alt+t` | new pane |
| `alt+shift+t` | new tab |
| `alt+shift+q` | close pane |

Also, `ctrl+c` and `ctrl+v` have been unbound.
These conflict with keyboard kill and vim visual block.
Use `ctrl+shift+` `c/v` instead.
