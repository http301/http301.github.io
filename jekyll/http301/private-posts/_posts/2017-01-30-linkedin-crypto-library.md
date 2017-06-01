---
title: LinkedIn Crypto Library
date: 2017-01-30 15:02:28
tags:
---

* TOC
{:toc}


# Crypto Library

## Secret

`The term **'Secret'** refers to a triple: { Secret-alias, Version, Passphrase }`

- *Secret Alias*: This is a human readable label used to uniquely identify a set of Passphrases, each associated with a unique version.
- *Version*: For implementing secret key rotation, each Passphrase is associated with a version unique within scope of the alias.
- *Passphrase*: Actual alphanumeric character sequence used to generate key.

E.g. Alias: pin.encryptionkey
      Version:1, Passphrase: "NotTheProductionSecret_1"
      Version:2, Passphrase: "NotTheProductionSecret_2"
      current_version: "1"
