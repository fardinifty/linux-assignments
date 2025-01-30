Fardin Hossain Ifty, amk1008039@student.hamk.fi
30/01/2025
Created the Tupu user using the "adduser¨ script. 
Then Created the Lupu user using the "useradd" command.
Try to create a user profile, home directory, and user group similar to Tupu. 
Created the Hupu system user with the login shell set to /bin/false using "sudo useradd --system --shell /bin/false hupu" command.
Added the users Tupu and Lupu to the sudo users Using visudo to edit sudoers file following these lines "tupu ALL=(ALL:ALL) ALL","lupu ALL=(ALL:ALL) ALL".
Created a directory /opt/projekti and add both users (Tupu and Lupu) as owners. Only Tupu and Lupu should have access to list files in the directory, read, and modify them.
