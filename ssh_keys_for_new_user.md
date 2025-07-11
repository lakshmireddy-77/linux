How to Give Key-Based SSH Access to a New User (e.g., ramesh)
=============================================================

----------- On Server (1st Terminal) -----------

# 1. Switch to root
sudo su -

# 2. Create the user
useradd -m ramesh     # -m creates /home/ramesh

# 3. Verify user creation
id ramesh

# 4. Go to the user's home directory
cd /home/ramesh

# 5. Create .ssh directory
mkdir .ssh
chmod 700 .ssh

# 6. Create the authorized_keys file
cd .ssh
vim authorized_keys

# Paste the PUBLIC key from client here (from ramesh.pub)

# 7. Set correct permissions
chmod 600 authorized_keys

# 8. Set correct ownership
cd ..
chown -R ramesh:ramesh .ssh


----------- On Client Machine (2nd Terminal) -----------

# 1. Generate SSH key pair
ssh-keygen -f ramesh

# This creates two files:
# - ramesh       (Private key)
# - ramesh.pub   (Public key)

# 2. View and copy the public key
cat ramesh

# Copy the entire content and paste it into the server’s authorized_keys file


----------- Connect to Server -----------

# Use the private key to connect
ssh -i ramesh ramesh@<public_ip>

# Replace <public_ip> with the actual server IP


----------- Permissions Recap -----------

/home/ramesh/.ssh             -> 700 (ramesh:ramesh)
/home/ramesh/.ssh/authorized_keys -> 600 (ramesh:ramesh)


----------- Troubleshooting -----------

If you get:
Permission denied (publickey,gssapi-keyex,gssapi-with-mic)

Check:
- Correct public key is in authorized_keys
- File permissions are correct
- You are using the private key properly:
  ssh -i ramesh ramesh@<public_ip>

