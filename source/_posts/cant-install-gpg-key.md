---
title: Can't install GPG key
url: 711.html
id: 711
comments: false
categories:
  - Code
date: 2016-06-01 14:34:55
tags:
---

So I was trying to install a gpg key on my Ubuntu Trusty server but kept getting the following error:

```
Executing: gpg --ignore-time-conflict --no-options --no-default-keyring --homedir
/tmp/tmp.U83lQ36Gpz --no-auto-check-trustdb --trust-model always --keyring /etc/apt/trusted.gpg
--primary-keyring /etc/apt/trusted.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
gpg: requesting key EA312927 from hkp server keyserver.ubuntu.com ?: keyserver.ubuntu.com:
Host not found gpgkeys: HTTP fetch error 7: couldn't connect: Connection refused gpg:
no valid OpenPGP data found. gpg: Total number processed: 0
```

A tonne of posts were talking about proxy settings and other issues. But the easiest fix in the end was to manually add the key. All I did was to search for the key on MIT's pgp search engine - https://pgp.mit.edu/ (click on the key to see the key data) And then run the following commands to manually add the key: `sudo apt-key add -` Paste the text (middle-click or use copy/paste) Press ctrl + D In my case the pasted text was for Mongodb:

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: SKS 1.1.5
Comment: Hostname: pgp.mit.edu

mQINBFYYLZUBEADTvHI/DDlJY4JCLh7chtQiKkj8kFpqOtY4x6luOQWvYNXfvso1yoKqKnU3
3Fh3JY4dWClXzv40PcVH4pIi95enzCLGvU30GNDsfmueV9vkq5HrCMMZrQ1M9/4HgrnbRvLh
vcb4VY+RELEdcHWhUkYTpG00YuEHdgJ3PoPL5pDu1L1z...etc.
-----END PGP PUBLIC KEY BLOCK-----
```