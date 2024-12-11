
# Installing OpenSSH SFTP Server on Kali Linux Latest

In this tutorial, we will demonstrate how to install OpenSSH SFTP server on Kali Linux Latest.

---

## Prerequisites

Before you begin with the installation process, ensure that you have:

- **Kali Linux Latest** installed and up-to-date  
- **Sudo privileges** on your Kali Linux system  
- **Active internet connection**  

---

## Step 1: Update Kali Linux

Start by updating the Kali Linux system. Run the following command in the terminal:

```bash
sudo apt-get update && sudo apt-get upgrade
```

---

## Step 2: Install OpenSSH SFTP Server

Install the OpenSSH SFTP server by running the command below:

```bash
sudo apt-get install openssh-server
```

Once the installation is complete, the OpenSSH service will start automatically.  
If it does not start, you can manually start it using the following command:

```bash
sudo service ssh start
```

Next, configure the OpenSSH server to enable SFTP access.

---

## Step 3: Configure OpenSSH for SFTP Access

By default, the OpenSSH server allows SFTP access for all users.  
To restrict SFTP access to specific users, edit the `sshd_config` file:

1. Open the `sshd_config` file with the following command:

    ```bash
    sudo nano /etc/ssh/sshd_config
    ```

2. Locate the line:  
    ```plaintext
    #Subsystem sftp /usr/lib/openssh/sftp-server
    ```  
    Uncomment it by removing the `#` symbol at the beginning of the line.

3. Save the changes by pressing:
    - `Ctrl+X`
    - Then `Y`
    - Finally, press `Enter`

4. Reload the SSH configuration with the following command:

    ```bash
    sudo service ssh reload
    ```

---

## Step 4: Test the OpenSSH Server

To test the OpenSSH server, use an SFTP client application such as **FileZilla** or **WinSCP**.  

### Connection Details:
- **Hostname**: Your Kali Linux system's IP address  
- **Port**: `22` (default SSH port)  
- **Username**: Your Kali Linux username  
- **Password**: Your Kali Linux password  

Connect to the server and create a test file to verify the SFTP connection is working.

---

## Conclusion

You have successfully installed and configured the OpenSSH SFTP server on Kali Linux Latest.  
You can now securely transfer files to and from your Kali Linux system.

---

### Additional Resources

- If you want to self-host in an easy, hands-free way, need an external IP address, or prefer managing your own data, consider [IPv6.rs](https://ipv6.rs).  
- For the best virtual desktop experience, check out [Shells](https://www.shells.com).
