# Installing QEMU

## Installing QEMU on MacOS

Alas, this seems to change every year. Damn you Steve Jobs!

### Get BREW

If you have `brew`, execute `brew update`. Then, pick up the install instructions at installing `qemu`.

```text
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

You will need to enter your Mac password.

This install can take a long time and make your fan spin real hard! The `xcode` `command line tools` may be installed.

### Install QEMU and yet another GCC

After `brew` is installed, you'll be able to get `qemu` and yet another C compiler. Damn you Steve Jobs!

```text
brew install qemu x86_64-elf-gcc
```

Note the `elf` - we will be talking about `elf` shortly.

This will also take a long time.

### Launching xv6

After downloading a fresh `xv6` zip file, decompress it into folder per `xv6` project.

In the `Makefile` search for `usertest` and delete the line it is on. Damn you Steve Jobs!

Then, when you want to start working on your `xv6` code, you'll need to do this:

```text
export TOOLPREFIX=x86_64-elf- 
export QEMU=qemu-system-i386
```

This can be made sticky so you don't have to do it every time you start work. Instructions for this another time.

Finally, to build and launch `xv6`:

```text
make qemu-nox
```

### Exiting xv6

```text
^ax
```

### If you already have QEMU

Check for an upgrade:

```text
brew upgrade qemu
```

`brew` may ask you to change the ownership of certain directories. Do as it suggests and rerun the `qemu` installation.

## Installing QEMU on Windows

Don't.

## Installing QEMU on WSL

1. Install WSL - I prefer you use Ubuntu 18.04 LTS.

This means you may have to enable the Windows Subsystem for Linux in the old Add Remove Programs -> Windows Features settings.

### Enable WSL

1. Completely update your Windows machine.
2. Open Settings app.
3. Click on Apps.
4. On right hand side, click on Programs and Features. Yet another settings dialog appears following a completely different standard. Microsoft is wonderful.
5. On the left of the new dialog click `Turn Windows features on or off`.
6. Scroll down to `Windows Subsystem for Linux`.
7. Ensure this is checked. If it is not, checking it will enbable WSL.
8. Hit OK and close settings related windows.
9. Restart Windows. Windows will update and restart.

There is a tiny chance your computer BIOS will need a tickle to enable Virtualization Technology. You won't find out until much later. Microsoft is Wonderful.

### Install Ubuntu on Windows

WSL is (for now) a command-line only honest-to-goodness Linux system with some small limitations (dealing with file systems). Any distro will do but I strongly suggest Ubuntu 18.04 LTS.

1. Press the windows key &#8862;
2. Microsoft Store
3. Search `Ubuntu`
4. Choose the right one: `Ubuntu 18.04 LTS`
5. Download it. It is about 221 MB.
6. Install it.
7. "Launch"
8. Wait.
9. Make a trivial user name and password. Don't make this complicated - something easy. I used user name `a` with password `a`. Entering a password on the command line does not echo. This is normal.


### Install QEMU

1. `sudo -i`
2. Enter password.
3. `apt update` If this is your first time, there may be hundreds of packages to update. Don't. Rather do it at home. See below.
4. `apt install qemu-system`
5. Enter
6. Wait
7. `exit` This will leave the super user shell.

At home, update the full system.

1. `sudo -i`
2. `apt update`
3. `apt upgrade`
4. `exit`

