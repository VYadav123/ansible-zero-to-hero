Here is the beautified content of the file:

---

### Command to Execute the Playbook Along with Vault

```bash
abhishekveeramalla@aveerama-mac day-07 % ansible-playbook -i inventory.ini ec2_stop.yaml --vault-password-file vault.pass
```

---

### For debugging Ansible gather facts

- hosts: all
become: true

tasks:
- name: Print all the ansible gathered ansible_facts
ansible.builtin.debug:
var: ansible_facts
