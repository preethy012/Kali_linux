Day 1 Summary – Linux Installation, Basic Commands, Permissions, and User Management

Commands I Used Today:

Today, I practiced a variety of Linux commands related to file management, user permissions, and basic system tools. Some of the key commands included:

Creating a folder with mkdir secure_folder

Creating a file inside it with touch secure_folder/data.txt

Setting strict access using chmod 700 secure_folder

Adding users with sudo adduser analyst1 and analyst2

Creating a group called security_team using sudo groupadd

Adding both users to the group using usermod -aG

Assigning the group to the folder and updating permissions using chown and chmod 770

I also explored tools like nmap for scanning the local machine, htop for monitoring system resources, and whois to check domain registration information.

Understanding chmod 770:
This command grants full read, write, and execute permissions to the owner and the group associated with a file or directory. At the same time, it restricts all access for others who are not part of the owner or group.

Purpose of Groups in Linux:
Groups allow you to manage file and folder access for multiple users more efficiently. Instead of setting permissions individually for each user, you can assign permissions to a group and add users to that group, simplifying access control.

Reflection:
Today helped me understand how Linux handles access permissions and user management. Using groups to manage shared access feels both efficient and secure. I also got a good start with tools like nmap, and I'm interested in exploring its advanced scanning capabilities in the next sessions.