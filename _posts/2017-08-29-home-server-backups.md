---
layout: post
title: Home server backups
date: 2017-08-29 20:31:08.000000000 +01:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []
meta:
  _wpcom_is_markdown: '1'
  _rest_api_published: '1'
  _rest_api_client_id: "-1"
  _publicize_job_id: '8759358030'
author:
  login: timabell
  email: tim@timwise.co.uk
  display_name: timabell
  first_name: ''
  last_name: ''
permalink: "/2017/08/29/home-server-backups/"
---
<p>The setup</p>
<ul>
<li>Ubuntu server domU xen host
<ul>
<li>Ubuntu server xen VM with LUKS full disk encryption
<ul>
<li>docker-compose
<ul>
<li>syncthing with built-in "Staggered File Versioning"</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
<p>Plan</p>
<ul>
<li>Plug in usb external hdd, with full disk encryption (i.e. a LUKS partition taking up almost all the space, plus a little fat32 with a text file in case anyone finds it and wants to return it).</li>
<li>Use LUKS key chaining to be able to unlock the disk without entering a password</li>
<li>Use autofs to automatically mount/unmount so that it's safe to unplug when a backup isn't running.</li>
<li>Use rsync to push all the files from the syncthing data directory onto the usb disk.</li>
</ul>
<p>Somehow need to make the disk accessible to the VM.</p>
<p>Finding the luks partition when plugged into the host:</p>
<pre>tim@spot:~$ sudo fdisk -l
...
Disk /dev/sdc: 931.5 GiB, 1000170586112 bytes, 1953458176 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x6380ad37

Device Boot Start End Sectors Size Id Type
/dev/sdc1 63 21579 21517 10.5M c W95 FAT32 (LBA)
<strong>/dev/sdc2 21580 1953147527 1953125948 931.3G 83 Linux</strong>


tim@spot:~$ ll /dev/disk/by-uuid/
...
lrwxrwxrwx 1 root root 10 Aug 29 21:51 <strong>6ca09b72-8c9b-4571-8943-9f1d520671ab -&gt; ../../sdc2</strong></pre>
<p>Confirm it's the luks partition:</p>
<pre>tim@spot:~$ sudo cryptsetup luksDump /dev/disk/by-uuid/6ca09b72-8c9b-4571-8943-9f1d520671ab
LUKS header information for /dev/disk/by-uuid/6ca09b72-8c9b-4571-8943-9f1d520671abVersion: 1
Cipher name: aes
Cipher mode: xts-plain64
Hash spec: sha1
...</pre>
<p>I'll update this post with any details as I progress. Don't hold your breath though!</p>
