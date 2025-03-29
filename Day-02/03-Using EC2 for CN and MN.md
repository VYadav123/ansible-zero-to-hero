Sure! Here is the beautified and updated version of your Markdown file with headings and code blocks formatted for easy copying:

```markdown
# Using EC2 for Control Node (CN) and Managed Node (MN)

## 1. Connect to the Control Node

```sh
ssh -i your_private_key.pem ubuntu@<control_node_public_ip>
```

## 2. Install Ansible on the Control Node

Update the package lists:

```sh
sudo apt update
```

Install Ansible:

```sh
sudo apt install ansible
```

## 3. Configure SSH Key-Based Authentication

Generate a new SSH key pair:

```sh
ssh-keygen -t rsa -N ""
```

Copy the public key to the managed node. Replace `<managed_node_public_ip>` with the actual IP address:

```sh
ssh-copy-id -i ~/.ssh/id_rsa.pub ubuntu@<managed_node_public_ip>
```

> The above command may throw an error: "permission denied (publickey)"

## 4. Workaround (Manual Copy)

On the control node, display the public key:

```sh
cat ~/.ssh/id_rsa.pub
```

Copy the entire output, which should start with `ssh-rsa` and end with your username and hostname.

Edit the `authorized_keys` file on the managed node:

```sh
vim ~/.ssh/authorized_keys
```

Enter insert mode by pressing `i`, paste the public key you copied into this file, and then press `Esc` and type `:wq` to save and exit.

Now try to connect to the managed node server using:

```sh
ssh ubuntu@<managed_node_public_ip>
```
```

You can now update the file in your repository with this beautified content. If you need any further assistance, feel free to ask!
