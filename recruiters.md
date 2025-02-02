---
layout: page
title: Recruiters
permalink: /recruiters/
---

While many recruiters try and be reasonable, there are enough out there using
[underhand
tactics](http://www.brandonsavage.net/why-recruiters-are-bad-for-your-career/)
to make life difficult and potentially jeopardise a good contract.

The one tackle here is "multiple submission". This is where you end up with
your CV landing on a client's desk from **two** different recruitment companies. I
gather this can be the nail in the coffin of a contract even if the client was
keen - who wants to be stuck in the middle of two recruiters fighting over the
commission?!

# Principles

The first step is simple, which is **never agree verbally or otherwise to be
put forward without first finding out who the client is**, and make sure you
keep track of who sent your CV where. I find
[Trello](https://trello.com/timabell2/recommend) is a good tool for keeping on
top of the fast moving and often fragmented information you get when hunting
for contracts, particularly combining web view with the mobile apps for on-the
go access to the information.

Recruiters are often hesitant to pass on the client's name, and this is
understandable as if you were to go round them then they'd lose their
commission which is how they earn a living. Worse, if you let the name slip to
another less scrupulous recruiter then they may try and get your CV in first
themselves without asking and in doing so sour the deal for everyone. (They
often fish for names with phrases like "*I need to know who else you've been
submitted to in order to avoid duplication*" - this is a lie, you can manage
this fine yourself.)

To tackle this I recommend the following:

* Never share their client's name with anyone else, especially other
  recruiters; make it clear this is a point of principle.
* Prove your integrity by politely refusing to tell recruiters who ask, they
  might have liked the name, but they will be more likely to trust you in the
  future for respecting the wishes of other recruiters.

So that's the easy bit which I've been doing for some time...

<div style="text-align: center">
<a href="https://www.flickr.com/photos/tim_abell/21013910269/" target="_blank" rel="noopener"><img title="" src="https://c2.staticflickr.com/6/5769/21013910269_433c52303f.jpg" alt="Picture of an otter's head poking up in the sea." width="320" height="192" border="0" /></a>
</div>

# Technical measures

There are unfortunately a bunch of particularly unscrupulous recruiters out
there like sharks in the water who will without your permission, or possibly
without ever contacting you, send your CV to their "client" (or just some poor
manager they've found to spam with CVs). You can't tell them not to if they've
never asked you, and it can still ruin a deal. So what to do about that?

If you're looking for contract work, you really need good exposure, so having
your CV all over the place like leaves in the wind is not a bad way of getting
the word out there (bear in mind I'm looking for work for my contracting
company, which is a different ball-game to finding that perfect permanent
role). It's actually pretty hard to control at all if you're dealing with
recruiters because as soon as you include your CV in a response to posting on
[JobServe](http://www.jobserve.com/) it'll be dropped straight into that
recruiter's pool of CVs, and some recruiters even pool CVs between them using
services like [iProfileUK](http://www.iprofileuk.com/).

To prevent that free-wheeling CV being used without permission, it contains the
following text (as does [my LinkedIn
profile](https://www.linkedin.com/in/timabell)):

> Recruiters: this CV is not authorised for distribution to your clients.
> Please contact me for permission to represent me and for a separate copy
> containing an authorisation code & gpg signature. Thanks. To prospective
> clients, if you receive my CV without these then I haven't given permission
> to be represented.

Okay, so far so good, but any unscrupulous recruiter could just strip that out
and send it anyway, and how would I be able to make a client comfortable that
they can tell this scumbag to jog on?

So before I agree to be represented by a particular recruiter to a particular
client (which I have no particular objection to if they've found work I
otherwise couldn't have found), I will be needing the client's name. I will add
this to a list of who has authorization to send my CV and who they are
authorized to send it to. I will then generate a customised CV (via mail merge)
with explicit permission to represent me to this specific client included in
it, and a note that any CVs received without this are unauthorized by me.

To prevent a recruiter cottoning on and just generating this themselves I will
then be [GPG](https://gnupg.org/) signing the result, which can then be checked
against my public key, proving that it did indeed come from me (assuming my pc
hasn't been hacked of course but I haven't heard of any recruiters going that
far, if they could they'd probably be security consultants instead of
recruiters!).

## My public key

My current public key for *tim@timwise.co.uk* is available on the public
keyservers, or you can download it: [my public key on
dropbox](https://www.dropbox.com/s/2abgnkfff4gceru/Tim%20Abell%20tim%40timwise.co.uk%20%280x28CDF8EA%29%20pub.asc.txt?dl=0).
Primary key fingerprint: 74D4 2A4C 9055 07C5 4A7E  3C9C 26C6 E087 **28CD F8EA**.

## Technical details

Using libreoffice calc, codes are generated with the following:

A cell containing allowable characters in the codes as text: `0123ABCDEF` etc
for this example this is in cell `F1`.

A row for each authorized representation containing this formula to generate a
unique authorisation code: `=CONCATENATE(MID($F$1,RANDBETWEEN(1,LEN($F$1)),1)`,
[repeat the "mid" clause once for each digit of the code to be generated] )

There's then another concatenation cell to generate the message to add to the
CV. This is then copy-pasted into a file, and signed with gnupg on the
command-line of my linux box. Here you can see the signing happening, followed
by verification that the file is signed properly (as the client might do if
they suspect a recruiter is reusing my CV for without my permission).

```
$ ./sign.sh #!/bin/sh -v gpg --clearsign authorization.txt

You need a passphrase to unlock the secret key for user: "Tim Abell
<tim@timwise.co.uk>" 4096-bit RSA key, ID 28CDF8EA, created 2015-01-20
```

```
$ ./verify.sh #!/bin/sh -v gpg --verify authorization.txt.asc gpg:
Signature made Thu 29 Oct 2015 01:02:52 GMT using RSA key ID 28CDF8EA gpg: Good
signature from "Tim Abell <tim@timwise.co.uk>" gpg: WARNING: This key is not
certified with a trusted signature!  gpg:          There is no indication that
the signature belongs to the owner.  Primary key fingerprint: 74D4 2A4C 9055
07C5 4A7E  3C9C 26C6 E087 28CD F8EA
```

the contents of the signed file is then copy-pasted onto the end of a CV and
sent off to the recruiter to relay to their client.

## Examples

I've uploaded a couple of files for you to try out verifying, one with the
original message, and one with a forged message where the client's name has
been changed. See if you can figure out which is which:

* [authorization1](https://www.dropbox.com/s/ycr0x9gruzjxlch/authorization1.txt?dl=1)
* [authorization2](https://www.dropbox.com/s/mlzyk3dd406dkqu/authorization2.txt?dl=1)

Here's an example signed authorization with a valid signature for the end of my
CV (mail merge fields in bold):

```
-----BEGIN PGP SIGNED MESSAGE-----
Hash: SHA1

Tim Abell has given permission for Test Recruiter Ltd to pass on this CV to
Some Client on 28 Oct 2015; auth code 662QP93XP4. Any copies of my CV received
without a valid signature have not been authorized for distribution.

-----BEGIN PGP SIGNATURE-----
Version: GnuPG v1

iQIcBAEBAgAGBQJWMXA8AAoJECbG4IcozfjqtKYP/0DGQBU64kRsAqmnkpRkJEIo
5gu1RVvozLE1AjE+/l7cq3LHo9jr3FUeigFD+DRcxVnfUT4pmyWHJYaqiYkm6MFf
dx/3DAwj9g1sUOr4Ef0CN3MuSiP0HqrNanRCao0qxvCw9GJlKO+vTJlo8ZZMt+V0
ImNxAIwjwKKLTvaLc7nxAlyjS8ZVuykBO5BTu5NnP4oDD359g1MEa6wI61et6bmj
jvQiSQpqJnHxs+EN1QvrkVuDLZUT2OOQxwnKJV3WfI87YBuaMH/Eguor5NIQvnXT
Z0vm5WbVgbadvpL5MP722EiNx+Ab4VCPJmEkrarH24em8f+JbZsvU753rZ4zgbOO
TtO71Bn2DtjvgT6cVEytDbpJcl0pAhCjbSYkFCXOQYeP9lcBopbdTJ6nRcFcFEFK
wlMcf+Cw/9WnYwyPMaWJi2zggJjLoWX2vRV5yUVa7y92pi9Fi2ow6Cru8WgXz/WW
FMqOTDdRcYbDWCcDT7vc3oW0yfIkaCxnSm1jcg+/VUr1X/9zuNxcV+qRPUJ15fYR
ii+cw/hIEqxn0tr+6eUsDmKdmS87PGGpo0wlGf3z7peytITIPf9y8bs2+N8ok6kA
8IXtZXqzYO3qnaIw2JUQidm/0zQ8xz4UNsSrqN2ZsxDtqGeDgHAn7+yFH7dvfTTV
ndYHkrMcYt1Yn5AmIsgZ =tFS7
-----END PGP SIGNATURE-----
```
