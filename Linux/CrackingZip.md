# Cracking Protected Zip File

```Shellscript
sudo apt install zip unzip john
```

### Generate hash of file
```Shellscript
zip2john file.zip > hash.txt
```

### Try to find password
```Shellscript
john hash.txt
```
