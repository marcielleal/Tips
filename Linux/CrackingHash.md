# Cracking Hash

### Find type of hash
```Shellscript
hashid thehash
```

### Cracking hash
```Shellscript
hashcat -m 0 -O hash.txt wordlist.txt
```

* -m 0 -> means md5
* -O -> optimization
