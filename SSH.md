# Create and Add SSH Keys
Typing the password each time you access the VPS can be tedious. It is also vulnerable to brute force attacks. Setting up SSH keys helps provide security and convenience. It does so by providing asymmetric encryption via public and private keys. 

The remote server uses public keys to verify your identity based on their SSH key fingerprints. On the other end, the local computer holds the private keys for authenticating your SSH connection.

When you connect to a remote computer, your local machine provides the private key. Then, the server checks it against the public key to grant you access.

The two most commonly used algorithms for generating authentication keys are:

- **RSA** – an SSH RSA key is considered highly secure as it has typically larger key sizes, often 2048 or 4096 bits. It is also more compatible with older operating systems.
- **Ed25519** – a more modern algorithm with a smaller standard key size of 256 bits. However, it provides the same level of security and efficiency as an RSA key due to its strong cryptographic properties. It is not as compatible with older systems, but newer operating systems support it.

Here, I will demonstrate generating private and public SSH keys using Ed25519 as an example.

### SSH with Password

First, we'll ensure that we can access the VPS using the username and password. Type `ssh user@hostname` into your terminal window. 

<img width="1162" height="346" alt="sshonmac" src="https://github.com/user-attachments/assets/e809eb8d-8059-4e1e-8d08-5632f1228eec" />

As you can see, the server defaults to the Ed25519 algorithm. I received a security warning since this is the first time I have connected to the server from my Macbook and it is not yet trusted by the system.  
<br/>
## Generate Keys

Type `ssh-keygen -t ed25519` into your terminal. The 't' flag specifies the type of algorithm you wish to use. 

<img width="1170" height="592" alt="sshkeygen" src="https://github.com/user-attachments/assets/9bb456f5-acbb-41ec-91db-5d9af439d442" />
The system immediately generates the public/private key pair. It then asks for the file location in which to store the keys. I simply pressed enter to leave it at the default location. I created a passphrase in the case of a breach where the private key is compromised.  
<br/>

## Transfer SSH public key to a remote server

Since I'm utilizing Hostinger for my VPS, I simply used the hPanel to copy my public key to the server.  

<img width="1854" height="772" alt="sshkeyadd" src="https://github.com/user-attachments/assets/fbbe1827-0b78-4af2-8daf-27a6190278b2" />
<br/>
Now, I can verify that the key has been added. 
<img width="1434" height="344" alt="mackkey" src="https://github.com/user-attachments/assets/2f541260-958a-4602-9170-e1ff71051603" />

After that, I am able to SSH to the server with just the passphrase. 

<img width="1008" height="190" alt="sshwithpassphrasemac" src="https://github.com/user-attachments/assets/97228cd5-0fcf-4665-be29-97b6db61812f" />

## Utilize SSH agent 

As projects grow in scope and size, it may become necessary to use more than one SSH key for different servers, user accounts, or projects.

At that point, an SSH Agent is recommended. This feature runs in the background and securely stores your private keys. It lets you manage SSH key pairs across multiple connections and eliminates the need to repeatedly enter private key passphrases during a session.

To start, launch the terminal and enter the following command to start the agent:

`eval "$(ssh-agent -s)"`

Then, enter the **ssh-add** command to add your private key to the SSH agent. Replace ‘private_key’ with your file name.

<img width="914" height="152" alt="evalandadd" src="https://github.com/user-attachments/assets/d964df49-1015-4042-ad24-1193c88cf38b" /><br/>

Run the following command to confirm that your private key has been added. It will list the identities currently held by the agent.

`ssh-add -l`

<img width="1152" height="68" alt="keyverification" src="https://github.com/user-attachments/assets/fb882ed4-a55c-42d1-a904-4ad2401da400" /><br/>

Now that the SSH agent is running and your private key added, you can connect to remote servers without entering your passphrase for each session. Simply use the ssh user@hostname command to log in.
