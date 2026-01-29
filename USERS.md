# Creating and managing a user 

This tutorial will explain how to create a user, manage their password, and add them to the appropriate group. The steps will be done as the root user. 

## Create User

The command to create a user is `useradd username`. 

<img width="466" height="44" alt="useradd" src="https://github.com/user-attachments/assets/3907de78-b982-4d08-8d02-9e7dd89368d4" /><br/>

 Set a password by typing `passwd username`.

 <img width="562" height="126" alt="userpasswd" src="https://github.com/user-attachments/assets/e4b9dc93-4be0-4ad4-aac1-c2c8d01fd485" /></br>

 ## Manage Groups 

 Add the user to a group with `usermod -aG group username`. The 'a' and 'G' flags together ensure that the user is not removed from previous groups. 
 
 *The wheel group is a special user group that provides certain users with the ability to perform administrative tasks. This group is especially significant for managing superuser privileges and ensuring secure delegation of administrative rights.*

 <img width="598" height="52" alt="usermod" src="https://github.com/user-attachments/assets/d3995c2a-8bb4-442f-9245-b2e0c512ac8d" /><br/>

 Switch to the newly created user with `su username`.

 <img width="730" height="108" alt="switchuser" src="https://github.com/user-attachments/assets/049f7012-83ee-4cd7-908f-52ed53ba0910" /><br/>

 Type `groups` to ensure that the new user is in the correct groups. 

 <img width="438" height="64" alt="verifiygroups" src="https://github.com/user-attachments/assets/81578026-b2f8-45f1-b9a1-d03cd742300d" />


