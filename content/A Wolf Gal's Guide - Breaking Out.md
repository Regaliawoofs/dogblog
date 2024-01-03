---
title: "AWGG - Breaking Out"
date: 2024-01-3T09:03:20-08:00
---



**AWGG - Breaking Out Of Jail**

So, you end up in a shell, and you realize you're stuck in jail. What do you do now?
*You break out of course!*

**Step 1: Enumeration**

The first thing you'll want to do is basic enumeration. Start finding what binaries you have access to while "locked up". At the very LEAST you'll have access to shell one-liners, but any compilers,  interpreters, or packages for other languages (gcc, python, lua, node, etc.) are a massive bonus.

---

**Step 2: Permissions Within the chroot Environment** 

The ability to read (and more importantly) write files in the chroot will give you a good idea of what you'll be able to get away with as you're trying to escape. Test the waters with `touch` or `vi` or if you've got them, `vim` or `nano`. 

---

**Step 3:Theory**

![Diagram of a basic chroot](https://securityqueens.co.uk/wp-content/uploads/2020/04/Chroot-1.png)

Breaking out of the sandbox and onto the root filesystem of the box is our goal, and to achieve this, we simply need to spawn a shell outside of our sandbox. 

---

**Step 4: Practice**

Here are several methods of chroot escapes, using very common binaries found enabled in chroot environments. These will work regardless of having write permissions in the chroot.

- **awk**  
```
awk 'BEGIN {system("/bin/sh")}'
```

- **vi** 
```
vi -c ':!/bin/sh' /dev/null
```

- **more** 
```
TERM= more /etc/profile
!/bin/sh
```

- **find**
```
find . -exec /bin/sh \; -quit
```
---

**Part 4a: Sudo is your best friend**

Many, many binaries that require elevated permissions will ask users to utilize `sudo` to elevate permissions. If you have access to use `sudo` (rare, but still extremely effective). We can utilize the privileges gained by `sudo`, and use common binary flags to gain privileged shells, and by proxy, execution as root in the sandbox, allowing us to jump out easily into the main filesystem, and start enumeration from there. 

**Extra Resources**

GTFOBins - Emilio Pinna and Andrea Cardaci's collaborative project that lists many privilege escalation opportunities presented by often standard binaries in linux images. (https://gtfobins.github.io/)

---

**DISCLAIMER: I am not responsible for any damage that may come to systems these techniques may be used on. I am also not responsible for making sure your target machines are owned by you, or are allowed to be tested by the machine's owner. You should follow proper due diligence in assuring your targets are within scope.**

*With that said, Happy Hacking!*

-RW