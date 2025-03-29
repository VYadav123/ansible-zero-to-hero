1. Connect to the Control Node
    ssh -i your_private_key.pem ubuntu@<control_node_public_ip>

2. Install Ansible on the Control Node
    Update the package lists:
        sudo apt update
    Install Ansible:
        sudo apt install ansible

3. Configure SSH Key-Based Authentication
    Generate a new SSH key pair:
        ssh-keygen -t rsa -N ""
    Copy the public key to the managed node. Replace <managed_node_public_ip> with the actual IP address:
        ssh-copy-id -i ~/.ssh/id_rsa.pub ubuntu@<managed_node_public_ip>
    (The above command may throw an error: "permission denied (publickey)")

4. Workaround (Manual Copy)
    On the control node, display the public key:
        cat ~/.ssh/id_rsa.pub
    Copy the entire output, which should start with "ssh-rsa" and end with your username and hostname.
    Edit the authorized_keys file on the managed node:
        vim ~/.ssh/authorized_keys
    Enter insert mode by pressing 'i', paste the public key you copied into this file, and then press 'Esc' and type ':wq' to save and exit.
    Now try to connect to the managed node server using:
        ssh ubuntu@<managed_node_public_ip>
