# Linux

## Kali Linux

### Configuration

#### Set ABNT2 on Kali
```ShellScript
$ setxkbmap -model abnt2 -layout br
```

#### Packages
```ShellScript
$ sudo apt install nmap gobuster seclists
```

### nmap
- -sV -> scan version
- -sC -> scan scripts **CAUTION:** this acts like an attack
```ShellScript
$ nmap [IP]
```
