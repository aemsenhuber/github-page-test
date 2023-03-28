---
title: login
date: 2023-03-28
---

## 1.  Computer systems

### Servers

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

# 3. Example

To login on errc1:

```ssh -4XC user@errc1```

or

```ssh -4XC user@errc1.usm.uni-muenchen.de```

- 4 is to avoid ipv6, X for the graphics, C to compress.

- user should be your username.

- To login from outside the USM you can go through `ltsp01`:

```ltsp01.usm.uni-muenchen.de -X4C```

