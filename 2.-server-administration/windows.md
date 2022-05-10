---
description: >-
  Source:
  https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson1/
---

# Windows

{% embed url="https://www.youtube.com/watch?v=bvGBVaipoqk" %}



## [Understanding Windows Administration Tools](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson1/)

Windows has many different administration tools, but do you know what even half of them do? In this edition of Geek School, we are going to teach you all about how to use these tools, as well as when to use each one.

### Task Manager

![](https://www.howtogeek.com/wp-content/uploads/2014/04/img\_535dc6aaab74f.png?trim=1,1\&bg-color=000\&pad=1,1)

This tool is used internally by Windows to run many tasks that only need to be run occasionally rather than always running. One of the biggest changes under the hood of more recent versions of Windows has been the switch from housing functionality in a service that is always running and moving them to scheduled tasks instead. You can also schedule your own tasks to run in this panel.\


### Event Viewer - **eventvwr.** **msc**

![](https://www.howtogeek.com/wp-content/uploads/2014/04/img\_535dc654eec4a.png?trim=1,1\&bg-color=000\&pad=1,1)

Most people don’t know how to use Event Viewer, or haven’t even heard of it, but it’s a great troubleshooting tool that can help you figure out when a component is having a problem behind the scenes. The trick is in understanding how to use it, as well as understanding when you don’t have to worry.

### Disk Management

![](https://www.howtogeek.com/wp-content/uploads/2014/05/clip\_image002.png?trim=1,1\&bg-color=000\&pad=1,1)

When you need to create or delete partitions, initialize a new disk, or even stripe a partition across multiple disks, this is the utility that you’ll need to use. It’s also very useful for figuring out why a USB drive isn’t showing up on your computer – you’ll open up Disk Management and check to see whether the drive or partition is showing up at all.



### Dealing with Services

![](https://www.howtogeek.com/wp-content/uploads/2014/04/img\_535dc88daf6e7.png?trim=1,1\&bg-color=000\&pad=1,1)

The services panel is fairly self-explanatory, with a list of services that are running or not running, the ability to stop and start them, and a few more options. It doesn’t really require explanation for most geeks.

But what does require explanation is how all these services really work, which ones you should disable (hint: you might be wrong), and how to really administrate them. We’ll take a look at removing services from the list entirely, and how those dependency and other options work.

Did you know that you can also manage services from the command line?

### Registry Editor

You are probably already aware of the Registry Editor, and you might have even hacked a few registry keys at one time or another. There is a lot more to the registry than just tweaking a setting, though, so in this part of the series we’ll take a deeper dive to help you understand what you need to know so you can edit with confidence.

### Resource Monitor

![](https://www.howtogeek.com/wp-content/uploads/2014/04/img\_535dc39f81c72.png?trim=1,1\&bg-color=000\&pad=1,1)

This tool is a newer addition to Windows that you won’t find in XP, and it is a powerful way to see what processes are using resources on your computer. Instead of just looking at memory usage or CPU time, as you can in Task Manager already, this utility allows you to see an in-depth look at what is using your resources, whether that is hard drive, network, memory, or CPU.

### Performance Monitor

![](https://www.howtogeek.com/wp-content/uploads/2014/04/img\_535dc37fcc0b7.png?trim=1,1\&bg-color=000\&pad=1,1)

This tool is yet another way to track resource usage over time, and it is meant for much more advanced users. We’ll cover how and why you want to use it, and how to get the most out of it.

### Group Policy Editor

_Note:_ the Group Policy Editor is only available in the Professional version of Windows, which is sad because it has a lot of really useful functionality. You can use this tool to tweak settings that aren’t available normally except through registry hacks. In fact, Group Policy is how a lot of your favorite registry hacks were found in the first place.

{% embed url="https://www.youtube.com/watch?v=cKbgHaQG6BI" %}



### Device Manager

![](https://www.howtogeek.com/wp-content/uploads/2014/04/img\_535dc5c342bb7.png?trim=1,1\&bg-color=000\&pad=1,1)

Long gone are the days of geeks using Device Manager every time they touch a computer. Plug and Play, which used to be known as “Plug and Pray”, has improved dramatically to the point where you rarely have to think about drivers or device support unless you are a hard-core gamer.

There are still some important things to know about how devices work in Windows, how to remove or update drivers, or how to see hidden devices so you can remove the drivers for devices that aren’t plugged into the computer anymore.

### File History and System Restore

Under the hood, the NTFS file system that Windows uses has a really powerful feature known as Shadow Copy, which works a lot like a versioning system. Essentially, you can take a “snapshot” of a point in time, and access or save files from that exact moment in time, even if the files continue to be modified after that.\


This technology is how all backup utilities work, so they can access files that are locked by other applications, and is also how the System Restore and File History features work under the hood. In previous versions of Windows Pro there was a feature called “Previous Versions”, where you could access these snapshots to restore particular files.

The new File History feature in Windows 8 saves out versions of certain files, similar to the way Apple’s Time Machine backups work – you need to setup a secondary backup drive and Windows will save the backups of the files.

And, of course, you can still access manually or automatically created snapshots if you need to. We’ll demystify all of these things when we cover the topic later in the series.

### Advanced Firewall

![](https://www.howtogeek.com/wp-content/uploads/2014/04/img\_535dc611000c8.png?trim=1,1\&bg-color=000\&pad=1,1)

The basic firewall utility that comes with Windows is really simple and barely worth talking about, but the advanced firewall interface is quite powerful. You can customize your settings as much as you want.



### Common MSC Files names&#x20;

admgmt.msc - Active Directory Manager

azman.msc - Authorization Manager

certmgr.msc - Certificate Manager

ciadv.msc - Indexing Service

comexp.msc - Component Services

compmgmt.msc - Computer Management

devmgmt.msc - Device Manager

dfrg.msc - Disk Defragmenter

dhcpmgmt.msc - DHCP Management

diskmgmt.msc - Disk Management

eventvwr.msc - Event Viewer

fsmgmt.msc - Shared Folders

gpedit.msc - Group Policy

ipaddrmgmt.msc - IP Address Manager

**lusrmgr.msc - Local Users and Groups**

ntmsmgr.msc - Removable Storage

ntmsoprq.msc - Removable Storage Operator Requests

perfmon.msc - Performance Monitor

rsop.msc - Resultant Set of Policy

secpol.msc - Local Security Policy

services.msc - Services

tsmmc.msc - Remote Desktop

uddi.msc - UDDI Services Management

wmimgmt.msc - Windows Management Infrastructure (WMI)

winsmgmt.msc - WINS Server Management\


### Extra Topics

1. [Using Task Scheduler to Run Processes Later](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson2/)
2. [Using Event Viewer to Troubleshoot Problems](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson3/)
3. [Understanding Hard Drive Partitioning with Disk Management](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson4/)
4. [Learning to Use the Registry Editor Like a Pro](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson5/)
5. [Monitoring Your PC with Resource Monitor and Task Manager](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson6/)
6. [Understanding the Advanced System Properties Panel](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson7/)
7. [Understanding and Managing Windows Services](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson8/)
8. [Using Group Policy Editor to Tweak Your PC](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson9/)
9. [Understanding Windows Administration Tools](https://www.howtogeek.com/school/using-windows-admin-tools-like-a-pro/lesson1/)
