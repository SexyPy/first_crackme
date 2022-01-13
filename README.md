
# First CrackMe

For my first CrackMe I decided to go on the site https://crackmes.one/ and to take one of the simplest to get in touch with the decompiling and debugging tools.

Concerning tools, in my case I would use Ghidra 10.1.1 and Python 3.9.0.


## 🚀 Let's get started
Let's get a CrackMe... [mohammadali](https://crackmes.one/crackme/5fe8258333c5d4264e590114)'s will be perfect...

**Platform:**
Windows

**Difficulty:**
1.0

**Quality:**
4.8

**Arch:**
x86


## 1) Find the main function
![main func](https://imgur.com/U0uvOxr.png)

## 2) Analyze the code
![main code](https://imgur.com/N2NMY21.png)

As we can see here we have several variables defined at program start:

    • An Integer named iVarl

    • A String of 30 characters max

    • Three undefined variables (local_28, local_24 and local_20)

    • Three Integer (local_lc, local_l8, local_l4)

When main is called local_28, local_24 and local_20 are updated in this way:

    local_20 => 0x73736170

    local_24 => 0x64726f77

    local_20 => 0x333231


With a little research on the internet we realize that it is possible to use the pwn library to transform these 3 variables into ASCII characters:

![pwn](https://imgur.com/3OfGOEs.png)

This looks very much like a password. Let's test it.  (Of course we remove \x00 which corresponds to a null character).

![congrat](https://imgur.com/fGNEgqz.png)

Here we go, we have validated our first CrackMe :)
