# rename-arw

## Description
**rename-arw** is a script, for MAC OS & Linux, that operates in the folder in which it is launched and renames all the RAW files with `.ARW` extension following this format:

`YYYYMMDDHHmmss-<pattern><filename>`

> `<pattern>` must be provided by user.

> `YYYYMMDDHHmmss` is retrieved from the datetime metadata of the file.

**rename-arw** can also rename your jpg files assuming same name convention adopted for ARW files, the renamed files will have a sequential number in place of the original filename (EX. _DSC0270.ARW).

So assuming we have the file `_DSC0270.ARW` within the `DCIM` directory, i.e., a photo taken on June 3, 2023 at 19:32:37, we first proceed to rename it with the pattern example:
```
cd DCIM
rename-arw example
```
The file will be renamed as described below:
```
_DSC0270.ARW ---> 20230603193237-example_DSC0270.ARW
```
Then after importing it into Lightroom and developing the photo we will have a jpg file in the `OUT` directory with the following name:
```
20230603193237-example_DSC0270.jpg
```
Now we rename it with the `-j` option of the script:
```
cd OUT
rename-arw -j
```
The file will be renamed like this:
```
20230603193237-example_DSC0270.jpg ---> 20230603193237-example_1.jpg
```
When the directory contains more than one file, the script will produce a counter with a number of digits equal to the number of files in the directory.

For example if the directory contains 100 files we will have the counter at the end of the name with this format:
```
001
002
...
100
```

## Installation
> This script will work if the following commands are already in the system: `file`, `cut`, `tr`

Download [main.zip](https://github.com/signoredellarete/rename-arw/archive/refs/heads/main.zip) and extract zip file, then:
```
cd rename-arw-main/
```
- For Mac OS users:
```
sudo mkdir -p /usr/local/bin/
sudo chmod +x /usr/local/bin/
sudo cp rename-arw /usr/local/bin/
sudo chmod +x /usr/local/bin/rename-arw
echo 'PATH=$PATH:/usr/local/bin/' >> ~/.bashrc
```
- For Linux users:
```
sudo cp rename-arw /usr/local/bin/
sudo chmod +x /usr/local/bin/rename-arw
```


## Update
If `rename-arw` is already installed in your system and you want to update it, just download [main.zip](https://github.com/signoredellarete/rename-arw/archive/refs/heads/main.zip) and extract zip file, then:
```
cd rename-arw-main/
sudo cp rename-arw /usr/local/bin/
sudo chmod +x /usr/local/bin/rename-arw
```

## Usage

### ARW mode
Enter the directory containing `.ARW` files and run the commmand `rename-arw` followed by `<pattern>`.
```
cd <directory-containing-arw>
rename-arw <pattern>
```
### JPG mode
Enter the directory containing `.jpg` files and run the commmand `rename-arw -j`.
```
cd <directory-containing-jpg>
rename-arw -j
```

## Example
![image](https://github.com/signoredellarete/rename-arw/assets/37313214/5dedfa23-6b3d-4284-b641-41f7c584c339)

## Notes
> This little script was written for a friend who needed to automate the file renaming operation he used to perform manually on `.ARW` files generated by his camera, before importing them into Lightroom.
New features and/or bug fixing will be add to this repository.
