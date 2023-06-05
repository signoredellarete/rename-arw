# rename-arw

## Description
**rename-arw** is a script that operates in the folder in which it is launched and ranames all the RAW files with `.ARW` extension following this path:

`YYYYMMDDHHmmss-<pattern><filename>`

> `<pattern>` must be provided by user.

> `YYYYMMDDHHmmss` is retrieved from the datetime metadata of the file.

## Installation
Download [main.zip](https://github.com/signoredellarete/rename-arw/archive/refs/heads/main.zip) and extract zip file.
```
sudo mkdir -p /usr/local/bin/
sudo chmod +x /usr/local/bin/
cp rename-arw /usr/local/bin/
echo 'PATH=$PATH:/usr/local/bin/' >> ~/.bashrc
```

## Usage
```
cd <directory-containing-arw>
rename-arw <pattern>
```