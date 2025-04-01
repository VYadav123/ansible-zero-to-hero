# Push your Ansible roles to Ansible Galaxy

1. Make sure your role is structured correctly. The basic structure should look like this:

```
my_role/
├── defaults/
│   └── main.yml
├── files/
├── handlers/
│   └── main.yml
├── meta/
│   └── main.yml
├── tasks/
│   └── main.yml
├── templates/
├── tests/
│   ├── inventory
│   └── test.yml
└── vars/
    └── main.yml
```

2. Make sure ansible-galaxy CLI exists

```
ansible-galaxy --version
```

3. Push Your Role to GitHub

```
cd <role-name>
git init
git remote add origin <https://github.com/your_github_username/my_role.git>
git add .
git commit -m "Initial commit"
git push -u origin main
```

4. Import the Role to Ansible Galaxy

```
ansible-galaxy role import <your_github_username> <role-name> --token
```
![image](https://github.com/user-attachments/assets/9a799aa3-e875-4d2b-bde2-46fd5bf280a5)
5. Getting token from Galaxy
![image](https://github.com/user-attachments/assets/be6469a3-d2a5-4b58-9305-9c9f331c0405)

6. Whenever you create the roles, it always create the different folders below

   ![image](https://github.com/user-attachments/assets/0ad4f3e6-3185-4805-8329-357909116df9)
