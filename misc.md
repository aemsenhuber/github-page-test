---
title: miscellaneous
date: 2023-03-28
---

This document contains information primarily on the computing systems hosted at USM. For information on the computing services provided by LMU Physik or by LRZ see their respective web pages:

- [https://www.it.physik.uni-muenchen.de](https://www.it.physik.uni-muenchen.de)

- [https://www.lrz.de](https://www.lrz.de)

# USM computer systems organization

## 1.  Computer systems

### Servers

There are lots of these. They are not available for users.

dorc1–4 and cast1–2

CAST group machines and associated disks.

seitz1–2, werc1–2

Stella’s group machines and disks (werc also Jochen).

weller1–2

Jochen’s group and disks.

gustl, birnst1

Til’s group and disks.

errc1, ercol1

Barbara’s group and disks.

ltsp01–03, mpusm01–11

Open to everyone (mpusm02 reserved for Jo, Keith, Thomas, etc.).

ltsp04–19

Thin client machines to replace PCs (reserved for practicals at the moment).

## 2. Users

- Any of the machines can be used by anyone with a valid USM account with an up-to-date password.

- BUT machines are reserved for the intended groups. You can use other group machines if and only if given permission by the various group leaders. Do not use the thin client machines unless you’re using a thin client.

  (This is not enforced at the moment but can be if necessary.)

- You can log in to `ltsp01` from anywhere using ssh:

  ```ssh -Y -l username ltsp01.usm.uni-muenchen.de```

  or:

  ```ssh -Y username@ltsp01.usm.uni-muenchen.de```

- You can log in to group machines (seitz1 etc.) and mpusm machines from within the MWN.

- You need to set up a VPN connection to access the MWN from outside: see [https://www.lrz.de/services/netz/mobil/vpn](https://www.lrz.de/services/netz/mobil/vpn).

- The other machines can only be reached from our local network, but this is changing. All PCs on the ground floor and some on the first floor can also be logged in to directly (with a VPN).

- If you mistype your password three times in a row then you will be blocked for 10 minutes, so just wait and then try again. This is a security measure and will change for the machines behind the LRZ firewall (those you can reach using VPN).

- Problems with the servers can mean either your username is not known or, more often, your home directory isn’t available. The latter is normally not a problem with the home directories themselves but with the system. When you try to log in to a machine, the machine asks our servers if your username is known and checks your password (using kerberos, look it up). If the answer to both is yes then you can log in BUT ssh and window manager (e.g., KDE, XFCE) try to store/read data on your home directory (look at .ssh, .config, .cache, .local) and if your home directory is not there or is full then you still won’t be able to log in.

- A serious DNS attack for instance can mean that ltsp01 and so on are not able to look up your information and you will be blocked. (It’s a bit more complicated as ltsp01 etc. cache much of the information to speed things up so you may possibly be lucky and be able to log in anyway.)

## 3. Module command

The module command works by modifying your environment (mostly the PATH and LDLIBRARYPATH variables). 

There’s a description at [https://doku.lrz.de/display/PUBLIC/Environment+Modules](https://doku.lrz.de/display/PUBLIC/Environment+Modules).

`module avail` tells you what modules are available.

`module list` tells you which modules you are currently using.

`module load intel` loads the default version of the Intel module.

`module load intel/17.0` loads version 17.0 of the Intel compiler suite.

`module unload intel` unloads the Intel version in use.

## 4. x2go

- X is slow remotely (and if your internet connection is interrupted, your session will be killed).

- Use x2go instead. It will work on any machine with ssh access.

- You can find x2go clients at [https://wiki.x2go.org/doku.php/download:start](https://wiki.x2go.org/doku.php/download:start).

- The clients need to know the machine you want to connect to, your username, and the desktop session type you want to use. Choose XFCE rather than KDE as it uses fewer resources.

- Disable sound as well.

- If you choose “Desktop Sharing” or “Connection to local desktop” you can connect to an existing X session and work with others (this is buggy and can give font and other problems).

- The session remains active until you log out on the remote machine. Just capping the connection doesn’t stop the session. (This allows you to resume a session if your internet connection suddenly dies but can be restarted.)

- Tadziu or Keith need to install/start an x2go server on the target machine. If you can ssh to a machine but not use x2go the server probably isn’t running. Please contact us in this case.

## 5. Queuing, scratch, and backup

- In general there is no queuing. On the whole people behave reasonably and a “gentle” hint has usually sufficed.

- The CAST group machines do have queueing. It is a system called torque which is based on the older PBS system. You submit (qsub) a script including comments specifying your requirements. For more information ask your supervisor or a friend.

- All machines have some scratch space which is limited to the machine in question. There are also project disks belonging to the various groups.

- If you need scratch space or access to the project disks then ask Keith or Tadziu to create a directory for you. You need to tell us which machines you are using as scratch is normally local to a single machine.

- Backups are made of system relevant disks. In particular, /home/moon (your home directories) are backed up incrementally every night.

- Scratch disks are not backed up.

- Desktop machines are only backed up if a user’s home directory is on the machine, incrementally every night.

- Your home directories are backed up, so any important software, programs, thesis, etc. should be placed there. And for really important stuff you should have your own backups.

- Your home directories are accessed by the machines you’re using through a (relatively) slow network connection. In addition, any changes made to files in your home directories will need to be transferred via the network to the LRZ for backup every night. Therefore, your home directory is not the place to do calculations creating large amounts of scratch data or large numbers of files. Use scratch space local to the machine or the project disks for this. You are probably not aware of it, but some of the software some of you are using creates tens of thousands of small files.

- `/tmp` is available and local but has limited space, shared with the system. When the disk is full the machine will not work properly, if at all. (Another reason why you may not be able to log in on occasion.)

## 6. System support

- Generally, contact Tadziu or Keith if you have system requests or there are problems with the system. If it’s something that Rudi needs to deal with it will be passed on.

- Software/system upgrades: we are obliged to keep the systems up to date as regards security updates. Unfortunately these mostly require a restart so we try to keep these to a minimum.

- All the user machines use the openSUSE distribution and should have the same software installed as far as possible. Anything else would be impossible to maintain.

- Use zypper se "package" to find out if SUSE supplies a package of interest. If they do just ask Keith or Tadziu to install it.

## 7. E-mail and file sharing

- Your e-mail and login accounts are completely separate even though the username is the same for both.

- This is for security reasons. Your e-mail password may be passed in clear over the network and read by an intruder.

- Email and login passwords should never be the same.

- For the same reason, your web presence (if you have set one up) has no access to your home directories, which is why you need to transfer data to the web directories. These are only available via ltsp01.

- E-mail is not meant to transfer large amounts of data. Use a cloud solution instead (e.g., [https://doku.lrz.de/display/PUBLIC/Cloud+Storage](https://doku.lrz.de/display/PUBLIC/Cloud+Storage)).

### FYI: e-mail addresses

- Every employee/student of the LMU has a lmu.de e-mail address. These are administered by the LMU IT department.

- Physics students and employees have a physik.uni-muenchen.de e-mail address. These are administered by the Physics faculty IT department.

- If you are working at the USM then you will usually have a usm.lmu.de / usm.uni-muenchen.de e-mail account. These are administered by us.

- These different mail addresses have absolutely nothing to do with each other.

- You can forward mail from one to the other. Do this by logging in to horde ([https://www.usm.uni-muenchen.de/horde/login.php](https://www.usm.uni-muenchen.de/horde/login.php)) and choosing “Mail”, “Filters”.

## 8. Outdated software

- Installing software or updating outdated software is easy if SUSE provides an update. If not then it will depend.

- For things like the Intel compilers etc., we try to keep them compatible with the situation at the LRZ.

- Other packages of general interest (things on /opt or /usr/local) are maintained by us, e.g., IDL, IRAF, . . .

- For programs which interest only 1 person he/she should do it themselves. Note that this isn’t generally hard but distributions like SUSE have chosen to separate out header files into packages which aren’t installed by default. This is actually idiotic as it stops you from compiling your programs without our help. Get in touch with Tadziu or Keith if you can’t compile your program due to missing files.

- Otherwise you can ask. It will help your case if other people are interested.

- Note that things like Python and Ruby are used by the system itself. They can’t be changed system-wide without there being a system upgrade. The same goes for glibc.

- We have tried to install more up-to-date versions of software in the past but this has caused more problems than are solved. Other things had a nasty habit of not working any more and when SUSE catches up/overtakes there are inconsistencies with libraries/header files etc.

- The same is true to some extent for packages from “packman”.

- This means that it’s better for some packages to be installed by the user.

- Bear in mind: we have of order 100 registered users, of order 100 machines (including PCs) and SUSE has 30000–40000 packages in all. There’s no way that 3 people can cater for every need.

## 9. Guests

- Short-term guests who want to make light use of the Internet should just use Bayern-WLAN which only requires agreeing to the terms and conditions. It is also available throughout the City.

- Longer-term guests can have a LRZ guest WLAN account. Just get in touch with Keith. You should say who it’s for and how long their stay is (a week is the maximum but this can be extended).

- For a meeting or workshop the LRZ will create an account for all participants. You need to do this reasonably well in advance. See [https://doku.lrz.de/display/PUBLIC/Konferenz-WLAN+beantragen](https://doku.lrz.de/display/PUBLIC/Konferenz-WLAN+beantragen).

- The other alternative is that they use a cable but this should only be used if larger amounts of data are being transferred. For this we (Tadziu or Keith) need the hardware address of the Ethernet card. It can be found using the commands

  - under Windows: `ipconfig /all`

  - under Linux or MacOS: `ifconfig -a`

    (or look at the internet connection in the system settings).

- If they have an ultra-thin laptop with an external Ethernet adapter then plug it in and give us its hardware address (it’s the one that appears after the device is plugged in).

## 10. Miscellaneous

- If you need more computing power it is possible to use the Linux system at the LRZ. Get in touch with your LRZ master user (Keith).

- Rudi and Keith are also responsible for the network so that any misuse gets reported to them and they will get in touch with you.

- The physics department has licensed software which may be of interest. This includes Mathematica and various Microsoft programs including Office. See [https://www.it.physik.uni-muenchen.de/dienste/software/index.html](https://www.it.physik.uni-muenchen.de/dienste/software/index.html).

- You can subscribe to the “alle” list in your mail client. Look for “subscribe” and choose usm-bulletin-board (right at the bottom).

# Information for computer users at the USM

## Passwords

If you have an account at the USM you have two passwords, one for logging in and one for email. Do not choose the same password for email as for logging in. This is so that when you read email over the web in not-so-well-trusted locations, if your email password gets compromised, your login account (and our machines) will not be.

To change your login password:

- connect to [https://umaster.usm.uni-muenchen.de/](https://umaster.usm.uni-muenchen.de/) with a web browser, log in, click on your name at the top right, and choose “Change password”.

To change your email password:

- connect to [https://kmaster.usm.lmu.de/](https://kmaster.usm.lmu.de/) with a web browser, log in, click on your name at the top right, and choose “Change password”.

## Email

Your email address at the USM is username**@usm.uni-muenchen.de** or username**@usm.lmu.de**. Mail sent to either address will arrive in your inbox.

You can read and send email using your favorite IMAP- and SMTP-capable mail program (e.g., Mutt, Pine, Thunderbird, Outlook, Apple Mail) or using one of the email interfaces on our web server ([Horde](https://www.usm.uni-muenchen.de/horde/), [SquirrelMail](https://www.usm.uni-muenchen.de/webmail/), or [Roundcube](https://www.usm.uni-muenchen.de/roundcubemail/)). SquirrelMail and Roundcube have a simpler interface, Horde also supports calendars, to-do lists, etc. For all email interfaces you need to authenticate using your username and email password.

If you prefer using a dedicated email program, here are the required settings:

- Mailbox server (IMAP) mailget.usm.uni-muenchen.de using a secure connection (SSL) on port number 993.

- Outgoing mail server (SMTP) mailto.usm.uni-muenchen.de using a secure connection (STARTTLS) on port number 587.

Both mailbox server and outgoing mail server require authentication using your username and email password.

## Email forwarding

Email forwarding is achieved via sieve, which runs entirely within the mail server (a .forward in your home directory will not work because the mail server does not look into the users’ home directories). You can write a sieve script by hand and upload it to the mail server or you can use Horde to set everything up for you (look under Mail → Filters).

For those writing their own scripts, the sieve language is well documented on the web, and the things you can have sieve do with your mail (such as automatically sorting messages into different subfolders or replying with a vacation message) are quite numerous. See Rudi’s imap pages for an example.

To upload a sieve file to the mail server:

- On one of the Linux machines change into the directory where your sieve file is located and execute sieve-connect mailget.usm.uni-muenchen.de, which should ask you for your (email) password.

- If the connection succeeds, from within sieve-connect do:

```
  put sievefile

  activate sievefile

  quit
```

where `sievefile` is the name of your sieve file. 
If your sieve script contains errors it will not be accepted.

The sieve script remains active until you (within sieve-connect) either deactivate or delete it or activate another script. You can also list your uploaded scripts in sieve-connect.

## Wireless network

The wireless network is managed by the LRZ. The simplest way to connect to the wireless network is through eduroam.

- If your home institute participates in eduroam and you have already set it up there, then it should work here as well without further changes.

- If not: here are the required settings (the LRZ has more detailed instructions, see [https://www.lrz.de/services/netz/wlan/eduroam/](https://www.lrz.de/services/netz/wlan/eduroam/)):

```
  Network name (SSID): eduroam.

  Security protocol: WPA2 Enterprise.

  Authentication protocol: TTLS, configured with:

  Outer identity (anonymous identity): anonymous@mwn.de.

  Phase 2 authentication (TTLS inner authentication): PAP.

  Identity (user name): username**@usm** (this is not an email address but a user name with an appended RADIUS authentication realm).

  Password: your email password.
```

- Your operating system may ask/require you to accept/install a corresponding server certificate.

- macOS and iPhone users can download a preconfigured profile that uses TTLS and PAP (the one from the LRZ is configured for PEAP and MSCHAPv2 and will not work with RADIUS).

- When installing the profile you need to enter your identity as username**@usm** and your email password.

## Wired network

To connect your laptop to the wired ethernet, set the wired network configuration to “automatic” (DHCP) and talk to one of the sysadmins to have the hardware address (MAC address) of your laptop registered with our server.

To find the hardware address:

- on Windows: type the command ipconfig /all into a cmd window and look in the output for physical address.

- on Linux and macOS: type the command ifconfig −a into a terminal window (console window) and look for HWaddr (Linux) or ether (macOS). (The builtin wired interface is often named eth0 or en0.)

In all cases the MAC address will look something like nn**-nn-nn-nn-nn-nn or nn:nn:nn:nn:nn:**nn, where the ns are digits/letters from “0” to “9” and “a” to “f”.

## Mailing lists

There are a number of institute-related mailing lists which may be of interest to you, such as alle for general USM-related topics or students for subjects of interest to Master’s and PhD students and post-docs. Publicly visible mailing lists, for example those created for the participants of a particular teaching course, are advertised on our mailman page ([https://www.usm.uni-muenchen.de/mailman/](https://www.usm.uni-muenchen.de/mailman/)). Consult your supervisor and/or colleagues regarding further mailing lists relevant to your work.

- To subscribe to a list, send a mail to listname**-join@usm.uni-muenchen.de**, where listname is the name of the list. (The subject and body of the message will be ignored, so you may leave them empty.)

- To unsubscribe from a list, send a mail to listname**-leave@usm.uni-muenchen.de**. Send this mail using the same email account with which you are subscribed to the list.

## Journal access

Journals for which the LMU has a subscription can be accessed from your laptop, if you have a VPN connection to the MWN (see [https://www.lrz.de/services/netz/mobil/vpn/](https://www.lrz.de/services/netz/mobil/vpn/)) and the correct proxy settings for your browser. The LRZ has an automatic proxy configuration script at [http://pac.lrz.de/](http://pac.lrz.de/). To set this in Pale Moon,for example, go to Preferences → Advanced → Network → Connection Settings, and then choose Automatic proxy configuration URL and enter the above address.

## Using X remotely

You can use VNC or X2go to connect to a remote desktop session. You will need a VPN connection to the Munich university network and the VNC viewer or X2go client software.

You can also use X directly if you have a local X server running (check that your DISPLAY environment variable is correctly set and that you can open local clients) and connect to our machines using ssh −X or ssh −Y.

## Printing

The recommended way to print on the USM printers from your laptop is via the USM CUPS server. (See the instructions on adding a printer for → Linux, → macOS, and → Windows.) To get a list of available printers, go to [http://cups.usm.uni-muenchen.de:631/printers/](http://cups.usm.uni-muenchen.de:631/printers/). On the USM Linux machines, you can also use the command lpstat −a to list all printers and their current status. Most of the printers also have an adhesive label indicating the printer’s name.

On the Linux machines, you can print from the shell command line using the command

lpr −o fit-to-page −Pprintername filename

where printername is the name of the printer on which you want to print. See man lpr for a list of available options.

## Poster printer

Poster size: The printer’s paper is 36 inches (91.4 cm) wide, which is slightly wider than A0 (84.1 cm). If you absolutely require an A0-size poster, you must manually cut off a strip of approximately 7 cm from the side of your printout. (The printer itself can cut the paper perpendicular to the feed direction, but not parallel.) If you prefer not to cut by hand, you can either use the full width of the paper, giving you a poster somewhat larger than A0, or print your poster rotated by 90 degrees (so that the width of the paper becomes the height of the poster), giving you a poster between A1 and A0 in size.

Margins: The printer will leave an unprinted margin of 17 mm at the top and bottom (in feed direction) and 5 mm at the left and right, inside of your requested paper size. Take this into consideration when designing your poster (→ Example). If you want color all the way to the edges, you have no choice but to manually trim the margin from all four sides.

Images: The printer understands baseline JPEG images (encapsulated in a Postscript wrapper), but it has trouble with progressive JPEGs. Avoid progressive JPEG encoding for images, otherwise your poster may not print. If you’re unsure, use a different form of encoding (e.g., in OpenOffice, choose “lossless compression” when exporting to PDF). As a general rule, avoid the use of images (in particular JPEG images) for line graphs and plots, and use scalable (vector) graphics instead.

Transparency: The printer understands Postscript, but not PDF. Posters in PDF must be converted to Postscript for printing, for example using Adobe Reader (acroread). While PDF supports transparency in its imaging model, Postscript does not, so transparency effects must be faked when converting to Postscript. Avoid the excessive use of transparency gimmicks in your poster design to reduce the probability that glitches will be introduced by this process.

