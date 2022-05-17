# Linux

##

## What You Need to Know to Get Started With Linux



{% embed url="https://www.lpi.org/our-certifications/lpic-1-overview" %}

November 13, 2020

This article has been just updated: November 13, 2020

### **An Overview of the Linux OS for Newbies**

There may come a time in your computing life when you either desire or require a degree of knowledge regarding the [Linux operating system](https://en.wikipedia.org/wiki/Linux). You might decide to explore Linux as an alternative operating system for your home computer. In some cases, you may need to display some proficiency with the software in order to perform your job. That’s how I first got involved with Linux.

After being introduced to the Linux machine that I would be using as a backup and recovery server, I began searching for information to help me survive. There is a wealth of informative websites, and over time I became more comfortable maneuvering around the system.

This overview is intended to get you started with Linux. It is not meant as an exhaustive reference guide. I will be providing links which offer more depth pertaining to the various aspects of the OS that are discussed in this guide.

So without further ado, let’s plunge into the workings of the **Linux** operating system.

### **What is Linux?**

![Linux Logo](https://comptechdoc.org/wp-content/uploads/2020/07/linux\_logo1.jpg)

Linux was born in 1991 as a free and open source alternative to Unix, according to [**opensource.com**](https://opensource.com/resources/linux). Its creator was [Linus Torvalds](https://en.wikipedia.org/wiki/Linus\_Torvalds), and due to a file structure that held the distribution code in a directory called “Linux”, the name stuck. The server admin had simply appended the first letter of Linus’ name to the word Unix in an attempt to easily identify where the code was stored. Names can be derived from the strangest places.

Linux is free for anyone to use and is distributed under the GPLv2 license. It is a comprehensive operating system that has found many applications in diverse areas of the computing landscape. You can find Linux running on supercomputers as well as on small, embedded devices. Different Linux distributions are tailored to be more useful in various implementations.

![](https://comptechdoc.org/wp-content/uploads/2020/07/various\_linux\_distro\_list.jpg)

### **Components of the Linux Operating System**

There are a number of distinct pieces which comprise a distribution of the Linux OS. According to [**linux.com**](https://www.linux.com/what-is-linux), they are:

![](https://comptechdoc.org/wp-content/uploads/2020/07/linux\_os\_components-300x249-1.jpg)

**The Bootloader –** This software manages the computer’s boot process.

**The Kernel –** The kernel is the core of the system and takes care of managing the computer’s CPU, memory, and peripheral devices.

**Daemons –** Background services such as printing and scheduling are handled by daemons.

**The Shell –** Also known as the Linux command line, in the early days of the operating system this was the only way to control your computer. It required commands to be entered in a text interface. Modern, desktop implementations of Linux have made it possible to use the operating system without having to master the command line.

**Graphical Server –** This sub-system is responsible for displaying the graphics on your machine and is called the X server.

**Desktop Environment –** There are many different desktop environments such as GNOME, Cinnamon, and KDE. This is the window through which the user interacts with the operating system.

**Applications –** There are thousands of applications that can be downloaded and installed to extend to functionality of your Linux implementation. Some Linux distributions offer a centralized method for installing applications.

### **Commonly Used Linux Commands**

Before we dive deeper into the inner workings of **Linux**, let’s take a look at some of the commands which you will commonly need to execute when working with the operating system through the **command line**. These are just a few of the more than 1,000 Linux commands that are available. For further information and more commands, consult the [**linuxtrainingacademy.com**](https://www.linuxtrainingacademy.com/linux-commands-cheat-sheet/).

* **ls** – This is the list directory command and displays the contents of the current working directory. Using the variant **ls -l** gives long form information and **ls -a** also will show you any hidden files in the directory.
* **pwd** – The current working directory is displayed with this command.
* **cd** – Change to your home directory with this command. Appending a space and a name will switch you to the named directory. Appending two periods will bring you to the current directory’s parent directory.
* **mkdir** – You can create a new directory with this command as long as none already exist with the selected name.
* **mv** – Rename or move files and directories with this command.
* **uname** – This command displays information regarding the machine name and operating system. Use uname -a to obtain more detailed information.
* **history** – Using this command you can see a list of the recently executed commands entered through the command line.
* **touch** – You can create a file that does not already exist with this command. If the file exists, the timestamp is updated, but the contents remain unchanged.
* **chmod** – This command is used to change the read, write and execute file permissions.
* **more** – This is a very helpful command that displays multiple pages of information one screen at a time. Hitting enter will show you the next screen.
* **locate** – Find a file’s location by name with this command.
* **man** – Short for manual, this command displays the reference manual pages for a specified command. Entering man ls will show what the manual has on the ls command.
* **kill** – This is used to kill a process by name.
* **ip** – This displays and manages routing, devices, and can be used to assign an IP address to a specific interface.
* **grep** – You can search for a specified pattern or string in files with this command.
* **du** – This command displays disk space usage of files in a directory.
* **cp** – Use this command to copy files and directories from one location to another.
* **passwd** – This command allows you to create or update passwords for user accounts.
* **cat** – You can view and add to a text file with this command.
* **sudo** – This is a very powerful command that allows an authorized user to execute commands as the root user of the system.
* **vim/vi** – Executing this command allows you to edit text and program files.

That’s enough to get you started. As we mentioned above, there are many commands incorporated into Linux. Consult the training link supplied to further investigate the functionality built into the operating system.

### **The Linux File Structure**

The Linux operating system has an extensive default directory structure. According to [linux.com](https://www.linux.com/blog/learn/intro-to-linux/2018/4/linux-filesystem-explained), these are the directories that can be found by executing the “**tree -L 1 /**“ command. The directories we will be discussing are the top level directories located under the _**root directory**_. We will simply name the directories and state the contents that they hold.

* **/bin** – contains binaries which are some of the applications and programs that can be executed.
* **/boot** – files required for system startup are in this directory.
* **/dev** – this virtual directory contains device files associated with peripheral devices attached to your system.
* **/etc** – contains system-wide configuration files.
* **/home** – users’ personal directories are located here.
* **/lib** – as you might suspect, this directory contains libraries that contain the code required by the system’s applications.
* **/media** – external storage is automatically mounted in the directory when it is plugged into your system.
* **/mnt** – used to manually mount storage devices or partitions.
* **/opt** – this directory will often contain software that you have compiled.
* **/proc** – another virtual directory that contains information about your CPU and Linux kernel.
* **/root** – home directory of the superuser or administrator.
* **/run** – used to store temporary data from system processes.
* **/sbin** – contains binaries that only the superuser will need.
* **/usr** – this directory was used for users’ home directories but has been replaced by the /home directory for that purpose. Modern Linux distributions use the directory for various application and service-related files.
* **/srv** – contains data for servers.
* **/sys** – a virtual directory that contains device information.
* **/tmp** – used for storing temporary files from users and applications.
* **/var** – logs and task spools are found in this directory.

There may be additional directories at the root level that are part of your particular Linux distro. Linux also creates subdirectories in most of the directories we have referenced above. You can explore them by using commands such as _**pwd**_, _**ls**_, and _**cd**_.

![](https://comptechdoc.org/wp-content/uploads/2020/07/linux\_file\_structure\_tree.jpg)

### **Linux Files and File Permissions**

The ability of users and applications to access files and directories is based on their file permissions. In Linux, if you don’t have permission to use a file in a particular way, it’s not going to happen. According to [**booleanworld.com**](https://www.booleanworld.com/introduction-linux-file-permissions/), these are the **specific permissions** that a file or directory can possess.

*
* **Read** – Read permission enables the user to view the contents of a file and view the names of files contained in a directory.
* **Write** – Having write permission lets a user modify or delete a file. Combined with the execute permission, you can modify the contents of a directory.
* **Execute** – Execute permission lets you execute a file if the read permission is also enabled. It is used with the write permission for modifying directories and the files they contain.

![](https://comptechdoc.org/wp-content/uploads/2020/07/permission\_classes.jpg)

Linux further delineates the control a user can exercise over a file or directory by the use of groups. A group is a collection of zero or more users that may have common computing requirements. File and directory permissions are assigned to three entities:

**User** – these permissions impact the file’s owner.\
**Group** – these permissions affect the group that owns the file. When the owner is in the group, User permissions are enforced.\
**Other** – all other users are subject to these permissions.

Executing a **ls -l** command will return a list of files and their permissions. The file mode describes the type of entity and its permissions. It is ten characters long, with the first letter being a ‘d’ for a directory, a ‘-‘ for a file, or a ‘l’ for a link.

![](https://comptechdoc.org/wp-content/uploads/2020/07/file\_types\_linux-300x125.jpg)

The next nine characters symbolically spell out the permissions for the User, Group, and Others respectively. Triplets of letters represent the permissions. For example, this would give everyone read, write, and execute permission for a file:

```
rwxrwxrwx
```

Where this takes away execute permission for the group and others.

```
rwxrw-rw-
```

_So the letter indicates the permission is enabled and a dash shows it is not set. They are always assigned in the read, write, and execute order._

Permissions can also be represented as numeric values based on binary substitution of the characters.

### **Linux Services, Daemons, and Devices**

Linux [services](https://www.linux.com/news/introduction-services-runlevels-and-rcd-scripts) and [daemons](https://en.wikipedia.org/wiki/List\_of\_Unix\_daemons) are very similar animals. They are both essentially applications that run the background. They are not under the direct control of a user. System events may initiate action by the services or daemons.

Some examples of important daemons are:

**cron** – used to schedule command execution\
**lpd** – manage printing\
**rpc.mountd** – respond to mount requests

Linux services such as Apache and MySQL are likely to be running on your machine.

![](https://comptechdoc.org/wp-content/uploads/2020/07/linux\_services\_daemons.jpg)

Devices files are special files that interact with device drivers to access hardware attached to your system. They are found in the **/dev** directory.

### **Networking with Linux**

Linux machines are often employed as network gateways or firewalls. The reliability of the operating system, its cost-effectiveness, and its flexibility make it a prime candidate for use in servers and devices involved in networking. There are Linux distributions that are tailored to the needs of network administrators.

According to [geekflare.com](https://geekflare.com/linux-networking-commands/), here are some of the more **useful Linux networking commands**.

* **ifconfig** – used to configure the parameters of network interfaces
* **telnet** – tests connectivity between two hosts
* **netstat** – allows you to review network connections
* **scp** – used to copy files securely between hosts
* **nmap** – checks opened ports

There are several Linux serial console programs which can be used for purposes such as testing and configuring the serial ports in your network installations. Among them are **minicom, grub,** and **getty**. Based on your specific distribution, additional tools may be available for use in network administration.

### **A Sample Linux Session**

Now that you have a little background concerning Linux let’s take a look at how a typical session begins. We will use the command line for demonstration purposes, but many Linux distributions have intuitive user-interfaces that can be used to perform many of the same functions. We will see some of the concepts discussed above in action.

Here’s what we are going to do.

Log into the system, locate a file, run it, change permissions so no-one else can run it, and then log off. Let’s get started.

login username **\<enter>** – Your username should have been assigned by your system administrator. You will be prompted for your password. Provide it and hit enter again.

You should be in your home directory. To verify, execute the **pwd** command. We are going to assume that the program you are going to run is located in _/home/username/progs_. Let’s go there by entering this command:

```
cd /home/username/progs
ls -l
```

Now you are presented with all of the files that are in the _/home/username/prog_ directory. You will see the file permissions, file owner, and group owner with the file name on the far right.

You have a program titled myTestProgram which currently has permissions set at –**rwxrwxrwx**, meaning that anyone can read, modify, and execute the program.

Since you are one of everyone, you can run it by simply typing its name and hitting enter.

```
myTestProgram
```

Let’s assume that the program executed, but there is an issue you need to resolve before letting anyone else use it. You need to change the permissions with the **chmod** command as in this example:

```
chmod u=rwx,g=r,o=r myTestProgram
```

The result of this command is that only you can run the program. A look at the file permissions will show this:

```
-rwxr—r—
```

Everyone else can only read the file. Now you can take your time and fix it before modifying permissions again to let others use your creation.

You can simply logout to end your session.

```
logout
```

That’s it. You have successfully run a program in Linux and modified it so it cannot be used by others. With a little practice, you will soon be moving around the system like a pro.

### **Installing Linux**

You may be interested in trying Linux on a particular computer but not yet be ready to blow away the current operating system. Many Linux versions have what is called a “live” distribution, where you can run the OS from a CD or other external media without any changes to your hard drive.

![](https://comptechdoc.org/wp-content/uploads/2020/07/install\_ubuntu.jpg)

This lets you check it out before making any commitment.

Once you are satisfied that the operating system indeed fits your needs, simply **click on the install icon** and a software wizard will guide you during installation. The wizard will help you determine if your machine meets the minimum requirements for the OS. You will also **set up your wireless connection** if you have one, as you will need to access the network to download additional software and updates.

Further details on trying and installing Linux can be found on this page at [**linux.com**](https://www.linux.com/learn/how-install-and-try-linux-absolutely-easiest-and-safest-way).

***

This overview provides a taste of what to expect from the Linux operating system. While it was once considered the operating system of experts or computer geeks, the newer, user-friendly distributions allow just about anyone to experiment with this powerful operating system. The links that are included in this article are a good starting point if you desire more thorough Linux knowledge. You just might find that Linux fills all of your computing needs and lets you escape from the monolithic major operating system vendors.

***

Copyright by comptechdoc.org

{% embed url="https://www.youtube.com/watch?v=ROjZy1WbCIA" %}

{% embed url="https://www.youtube.com/watch?t=481s&v=ZtqBQ68cfJc" %}
