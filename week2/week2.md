# Introduction to Operating Systems
- What is an OS and how does it work?
- Tasks of an OS
- How an OS is constructed
- How different OSs, like Unix, Linux, Windows and MacOS differ from each other

# Virtualization
- Introduction to Virtual Machine
- Setup a Linux Virtual Machine

# Package Manager - Installing Software
- What is a Package Manager and what are Software Repositories?
- Learn all the options of installing software on Linux and how it all actually works in the background:
  - APT
  - APT vs APT-GET
  - SNAP
  - Ubuntu Software Center
  - YUM

# Working with Vim Editor
- What is Vim?
  - Vim =   Vi + IMproved
  - Editor Words
- Learn most important Vim Commands to work with Vim efficiently
  1. Sửa file: vi file_name
  2. Chuyển mode: Esc
    - Chuyển sang mode Insert: Esc + I , A
  3. 1 số lệnh trong mode insert
    - Xoá 1 dòng: DD
    - Xoá n dòng: DnD
    - Copy 1 dòng: YY
    - Copy n dòng: YnY
  4. 1 số lệnh khác
    - Quay lại: Esc + U
    - Tìm kiếm: Esc + /
      - Tìm kiếm tiếp theo: N
    - Di chuyển đầu dòng: Ctrl + A
    - Di chuyển xuống dòng cuối: Shift + G
    - Thoát: ":" + w (write) + q (quit) + !(force)
    - Hiển thị dòng: ":" + set number
    - Di chuyển xuống dòng n: ":" + n 

# Users & Permissions
- Linux Accounts
- Users, Groups
  - ví dụ: -rwxrw-r-x
    - ký tự đầu: file or dir
  1: Owner permissions:
    − The owner's permissions determine what actions the owner of the file can perform on the file.
    - từ ký tự 2 - 4
  2: Group permissions
    − The group's permissions determine what actions a user, who is a member of the group that a file belongs to, can perform on the file.
    - từ ký tự 5-7
    - thêm quyền cho group: chmod g+permissions
  3: Other (world) permissions
    − The permissions for others indicate what action all other users can perform on the file.
    - từ ký tự 8-10
    - thêm quyền cho other: chmod o+permission
  - Permission: --- , rwx, ...
    1. File Access Modes
    - Read: cho phép đọc, view nd của file
    - Write: cho phép chỉnh sửa, xoá nd của file
    - Execute: có thể chạy file như 1 program
    2. Directory Access Modes
    - Read: người dùng có thể đọc nội dung, có thể nhìn thấy filename bên trong
    - Write: người dùng có thểm thêm, xoá dir
    - Execute:
    3. Mỗi permission có thể đc điều khiển ở 3 lv:
    - u: user = uself
    - g: group = can be people in the same project
    - o: other = everyone on the system
- User Management in Practice
  - Thông tin username được lưu trong file /etc/passwd
    - Format: username : x : user id : user group id : : /home/username : /bin/bash 
  - Thêm 1 người dùng:
    - sudo useradd username
    - addusser username
  - Đổi mật khẩu
    - passwd username
  - Thay đổi userID
    - usermod -u new_id username
  - Thay đổi groupID của user
    - usermod -g new_groud_ip username
- File Ownership & Permissions
- Modifying Permissions
  - Thêm quyền: "+"
    - ví dụ: chmod u+wx
  - Xoá quyền: "-"
    - ví dụ: chmod u-x
  - Gắn quyền: "="
    - ví dụ: chmod u=wx
  - Changing Owners and Groups
    1. Changing Owners
    - chown user filelist
    2. Changing Groups
    - chgrp group filelist
# Linux File System

# Basic Linux Commands
- Introduction to Command Line Interface
- Learn all the essential Linux Commands like
  - Directory Operations
  - Navigating the Files System
  1. Thư mục home: cd ~
  2. Thư mục gần nhất: cd - , cd ..
  3. List file in directory: ls folder_name
  4. Tạo folder: mkdir folder_name
  5. Tạo folder tại thư mục mẹ: mkdir -p /path/folder_name
  6. Đường dẫn thư mục hiện tại: pwd
  7. Xoá: rm -rf folder_name
  8. Rename: mv old_name new_name
  9. Copy folder: cp -R source_folder destination_folder
  

  - Work with the File System (Create folders, list files, rename, remove files etc.)
  1. Tạo file: vi file_name, touch file_name, ...
  2. List: ls
  3. Rename file: mv old_name new_name
  4. Copy file: cp source_file destination_file
  5. Edit file: vi file_name, nano file_name, ...
  6. Display content of file: cat file_name
  7. Word Count: wc file_name
  8. Delete file: rm file_name
  9. Find file: find . -name "key_word" ; locate "key_word"

  - Execute Commands as Superuser
  - Pipes, Redirects, Less, Grep
  1. Grep
  - grep = g + re + p = globally search for a regular expression and print all lines containing it
  - Cú pháp: grep + pattern
    - VD: ls -la | grep "Aug" : tìm kiếm các file tạo trong tháng 8
  2. Sort
  - sắp xếp sắp xếp các dòng văn bản theo thứ tự bảng chữ cái hoặc số
  - Cú pháp: sort + file_name
    - VD: sort hello_word.txt

# Shell Scripting
- Shell vs sh vs Bash
- Write & execute a simple script
- Learn how to write Bash Scripts
  - Variables
    - Defining variables: variable_name=variable_value
      - ví dụ: name = "abc def"
    - Accessing values:
      - ví dụ: echo $name
    - Read-only variables
      - ví dụ: readonly name
    - unsetting variables
      - ví dụ: unset variable_name
    - Mảng:
      - array_name[index]=value 
  - Read user input
    - cú pháp: read 
  - Basic Operators
    - ví dụ: `expr $a + $b`
  - Passing Arguments to a Script to make it customizable and reusable
  - Conditional Statements
    - If...else statements:
      if [ điều kiện ]
      then
        do something
      elif
        do something
      else
        do something
      fi
  - Repeating code with shell loops
    - While
      while command
      do
        do something
      done
    - For
      for var in word1 word2 ... wordn
      do
        do something
      done

      for var in file_name
      do
        do something
      done
    - Until
      until command
      do
        do something
      done
  - Functions

# Environment Variables
- What are environment variables and how to access them
- Create, Delete and Persist Env Variables
- Understand what the PATH env variables is

# Networking
- How computer networks work?
- What is LAN, Switch, Router, Subnet, Firewall, Gateway
- What is an IP address and port?
- What is a DNS and how does DNS resolution work?
- Useful Networking Commands

# SSH - Secure Shell
- What is SSH and how it works
- SSH in Action:
  - Create Remote Server on Cloud
  - Generate SSH Key Pair
  - Execute a bash script on a remote machine