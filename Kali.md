# Kali setup playbook
This is just my personal preference to get started, your requirements may differ so follow at your own risk.

**Hypervisor:** VirtualBox

**Install type:** the latest “point release” installer


## VirtualBox Settings

Under the VM settings: `system > assign 12Gb RAM and 6 CPU cores`, `display > set video memory to 128mb` and `audio > set audio controller to "Intel HD Audio"`


## Installing VirtualBox Guest Additions

The Kali Linux installer will automatically add Guest Additions.


## Kali HiDPI mode

If using a HiDPI monitor, text may appear too small. Run `kali-hidpi-mode` to enable a 2x scaling.


## Kali tweaks

Run `kali-tweaks` and amend repositories to use HTTPS (else the HTTP traffic may get blocked):

`Network Repositories > Use the HTTPS Protocol`

I also prefer the terminal emulator prompt to be on a single line:

`Shell & Prompt > Configure Prompt > One Line`


## Install and enable firewall

```bash
sudo apt update && sudo apt install ufw && sudo ufw enable
```


## Update all packages

```bash
sudo apt update && sudo apt full-upgrade
```


## Disable screen timeout 

Go to `Power Manager > Display` and set the parameters to never.


## Install favourite packages

```bash
sudo apt install flameshot ffmpeg ghostwriter hollywood
```


## Update Firefox settings

Personally I prefer to update safety and history settings in Firefox, limiting the history shown and default search engine.

Also certain CTF platforms may use TLDs such as thm or htb often - these can be whitelisted as valid in `about:config`:

```bash
browser.fixup.domainsuffixwhitelist.<myTLD>
browser.fixup.domainsuffixwhitelist.thm
browser.fixup.domainsuffixwhitelist.htb
```
(means Firefox will understand it is a TLD and not to send it to the search engine)


## Disable zsh autosuggestions and history (optional)

My personal preference is to not save commands into a history file and disable the autosuggestions:

```bash
# open the config file
vim .zshrc

# comment out the if statement block referring to zsh-autosuggestions.sh

# amend the history variables
export HISTFILE=/dev/null
export HISTSIZE=50
export SAVEHIST=0
```

