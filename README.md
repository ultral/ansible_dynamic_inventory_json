# Introduction

By default Ansible supports ini & yaml formats, I decided to create short demos and compare dynamic inventory & inventory plugins mechanism. 

## Run IT

```
ansible-playbook -i inventory.yml demo.yml
ansible-playbook -i inventory.ini demo.yml
INVENTORY_SRC=inventory.json ansible-playbook -i inventory_json.py demo.yml
ANSIBLE_INVENTORY_ENABLED=jsn ansible-playbook -i inventory.json demo.yml
```

As expected output you should recieve for each run:

```
ok: [demo2] => {
    "msg": "demo2 - value - bar"
}
ok: [demo1] => {
    "msg": "demo1 - value - foo"
}

```

## Dynamic inventory

![schema](assets/inv.png?raw=true "Schema")

1. Execute Dynamic Inventory.
2. Collect Target information.
3. Output Inventory to STDOUT.
4. Read Inventory Information.
