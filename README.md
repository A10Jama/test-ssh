STEP 1: Creating an SSH Key Pair

Open Git Bash
Change directory to your main folder: cd /path/to/main/folder
Create a new directory called .ssh: mkdir .ssh
Generate a new SSH key pair: ssh-keygen -t rsa -b 4096 -C "email@example.com"
Choose a name for your key pair (e.g. id_rsa for private key and id_rsa.pub for public key)
Press enter twice to use the default settings (no passphrase)
(optional) If you want to delete the key pair, run: rm /path/to/key/pair
STEP 2: Registering the Public Key with GitHub

Open Git Bash

Print the public key to the terminal: cat /path/to/public/key

Copy the entire contents of the public key to your clipboard

Open GitHub in a web browser

Click on your profile icon in the top right corner, then click Settings

Click on SSH and GPG keys, then click New SSH key

Enter a title for your key (e.g. My SSH Key)

Paste the public key into the Key field

Click Add SSH key

STEP 3: Adding the Private Key to the SSH Agent

Open Git Bash
Start the SSH agent: eval ssh-agent -s
Add the private key to the SSH agent: ssh-add /path/to/private/key
Test the connection: ssh -T git@github.com
Type "yes" if prompted to add GitHub to the list of known hosts
STEP 4: Creating a Test Repository

Open GitHub in a web browser

Click the "+" icon in the top right corner, then click New repository

Enter a name for the repository (e.g. test_ssh)

Choose "Private" or "Public", depending on your preference

Choose "Initialize this repository with a README" and click Create repository

Open Git Bash

Change directory to where you want to create the repository: cd /path/to/parent/folder

Create a new directory for the repository: mkdir test_ssh

Change directory to the new directory: cd test_ssh

Create a new README.md file: touch README.md

Open the README.md file in a text editor: nano README.md

Type a message in the file (e.g. "Hello, world!")

Save the file: press Ctrl+O, then Enter

Exit the editor: press Ctrl+X

Print the contents of the README.md file: cat README.md

STEP 5: Pushing the Repository to GitHub

Open Git Bash
Change directory to the repository: cd /path/to/test_ssh
Initialize the local repository: git init
Add all files to the repository: git add .
Check the status of the repository: git status
Commit the changes with a message: git commit -m "Initial commit"
Rename the branch to "main": git branch -M main
Connect the local repository to the remote repository: git remote add origin git@github.com:username/test_ssh.git
Push the changes to the remote repository: git push -u origin main

