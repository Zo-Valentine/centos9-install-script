#!/bin/bash
home_diectory="/home/zo"
make_new_file=(){
    touch /updates.txt
}
new_file_loc="/home/zo/updates.txt"
#make sure to be at home directory 
cd $home_diectory
#make new txt file for updates and upgrades 
$make_new_file
#print file location 
echo running updates to be stored at $new_file_loc
#update and upgrade repositories
sudo apt update && sudo apt upgrade -y >> $new_file_loc
#cat the txt file 
cat $new_file_loc