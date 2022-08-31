# Script Runner
A runner for any kind of scripts

## start
1. fork this repositary
1. modify the RAWSITE in run file
1. clone your repositary to your local

## write script
support any kind of script with Shebang
### POSIX shell
```
#!/bin/sh
...
```
### bash
```
#!/usr/bin/bash
...
```
### zsh
```
#!/usr/bin/zsh
...
```
### python
```
#!/usr/bin/env python
...
```
### nodejs
```
#!/usr/bin/env node
...
```
> DON'T write any variable according to the script path
## write sudo script
if name of script starts with "sudo-", this script will run with root privilege
## write hook
`MAIN_SCRIPT.pre` or `MAIN_SCRIPT.post`
```
SCRIPT [ARG1 ARG2 ARG3...]
SCRIPT [ARG1 ARG2 ARG3...]
# comment here
```
> SCRIPT is the script path relative to repositary. each SCRIPT in pre hook will run before the running of MAIN_SCRIPT, and each SCRIPT in post hook will run after.

## run script
### run locally
```
$ ./run SCRIPT ARG1 ARG2 ARG3
```
### run remotely
```
$ sh -c "$(curl -fsSL RAWSITE/run)" - SCRIPT ARG1 ARG2 ARG3
```
```
$ sh -c "$(wget -qO- RAWSITE/run)" - SCRIPT ARG1 ARG2 ARG3
```
