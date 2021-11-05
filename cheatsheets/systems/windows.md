# Windows

## Hyper-V

To switch the hyper-v launch type:

- `on` - allows running WSL, Docker, etc.
- `off` - allows running VirtualBox

Execute the following batch files **as administrator** on your local drive (not on a mounted or a network drive!).

`hyperv-on.bat`

```bat
@echo off

echo Trying to turn on hyper visor launch (needs to be run as administrator) . . .
echo.

bcdedit /set hypervisorlaunchtype auto

echo.
pause
```

`hyperv-off.bat`

```bat
@echo off

echo Trying to turn off hyper visor launch (needs to be run as administrator) . . .
echo.

bcdedit /set hypervisorlaunchtype off

echo.
pause
```
