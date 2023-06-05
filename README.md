# rename-arw

## Description
**rename-arw** is a script, for MAC OS & Linux, that operates in the folder in which it is launched and renames all the RAW files with `.ARW` extension following this format:

`YYYYMMDDHHmmss-<pattern><filename>`

> `<pattern>` must be provided by user.

> `YYYYMMDDHHmmss` is retrieved from the datetime metadata of the file.

## Installation
Download [main.zip](https://github.com/signoredellarete/rename-arw/archive/refs/heads/main.zip) and extract zip file.
```
sudo mkdir -p /usr/local/bin/
sudo chmod +x /usr/local/bin/
sudo cp rename-arw /usr/local/bin/
sudo chmod +x /usr/local/bin/rename-arw
echo 'PATH=$PATH:/usr/local/bin/' >> ~/.bashrc
```

## Usage
```
cd <directory-containing-arw>
rename-arw <pattern>
```
## Example
![image](https://github.com/signoredellarete/rename-arw/assets/37313214/5dedfa23-6b3d-4284-b641-41f7c584c339)
