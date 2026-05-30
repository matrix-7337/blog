---
title: "Hidden In Plainsight"
date: 2026-05-30 00:00:00 +0000
categories: [Pico]
tags: [Forensics , Easy] 
---

# 🕵️ Forensics Writeup: Hidden in Plainsight

## 📂 Given Files / Artifacts

- `<img.jpg>`

---

## 🔍 Initial Inspection

- download the Img.jpg
- Then we have to look for MetaData
```bash
exiftool img.jpg
--> encoded comments hidden
echo"comment" | base64 -d
--> steghide:encoded strings
echo"strings" | base64 -d
--> give a password
steghide extract -sf img.jpg
--> enter pass: decoded strings
>> flag.txt
>> cat flag.txt
>> picoCTF[...........]
