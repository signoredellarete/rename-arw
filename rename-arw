#!/bin/bash
# Check pattern argument

usage(){
  echo " "
  echo "Usage:"
  echo "cd <directory-containing-arw>"
  echo "rename-arw <pattern>"
  echo " "
}

if [ -z "$1" ];then
  echo "Error!"
  echo "Argument <pattern> is missing."
  usage
  exit 1
else
  pattern=${1}
fi

# Check
if arw_num=`ls -1|grep ARW|wc -l`; then
  if [ ${arw_num} -lt 1 ];then
    echo "Error!"
    echo "No .ARW file found in this folder: $PWD"
    usage
    exit 1
  fi
fi

# Execution
for i in `ls -1 *ARW`
do
  datetime=`file -p ${i}|cut -d "," -f 13|cut -d "=" -f 2|tr ":" " "|tr -d " "`
  echo ${i} "--->" ${datetime}-${pattern}${i}
  mv ${i} ${datetime}-${pattern}${i}
done
