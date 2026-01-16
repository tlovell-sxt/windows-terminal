# `windows-terminal`
Some windows terminal settings, mostly keybindings.

## Setup with symlink
We can symlink the settings file to the one that exists in this repo.

The downside of this is that changing settings requires restarting windows terminal to take effect.

1. Clone this repo into your wsl home directory
```bash
cd
git clone https://github.com/tlovell-sxt/windows-terminal
```
2. Completely close out of windows terminal, end tasks with task manager
3. Start powershell (not in windows terminal) as administrator
4. Remove the original settings.json and replace it with a symlink.
```powershell
$windowsHome = "C:\Users\TrevorLovell"
$wslHome = "\\wsl.localhost\NixOS\home\nixos"
rm "$windowsHome\AppData\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\settings.json"
New-Item -Path "$windowsHome\AppData\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\settings.json" -ItemType SymbolicLink -Target "$wslHome\windows-terminal\settings.json"
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
