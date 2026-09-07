# Day 70 – Variables, Facts, Conditionals and Loops

Today I learned the basic concepts of making Ansible Playbooks more flexible.

## 1. Variables

Variables store reusable values.

Example:

```yaml
vars:
  app_name: my-app
  app_port: 8080

Variables can be used with:

{{ app_name }}
{{ app_port }}
2. Ansible Facts

Ansible automatically collects information about managed hosts.

I practiced:

Hostname
Operating System
RAM
IP Address

Example:

{{ ansible_hostname }}
{{ ansible_distribution }}
{{ ansible_memtotal_mb }}
{{ ansible_default_ipv4.address }}
3. Conditionals

The when condition allows a task to run only when a condition is true.

Example:

- name: Check Ubuntu
  debug:
    msg: "This is an Ubuntu server"
  when: ansible_distribution == "Ubuntu"
4. Loops

Loops allow the same task to work with multiple values.

Example:

loop:
  - /tmp/app
  - /tmp/logs
  - /tmp/config

I used a loop to create multiple directories.

Files Created
variables-demo.yml
facts-demo.yml
conditional-demo.yml
loops-demo.yml
Key Takeaway

Today I learned how Variables, Facts, Conditionals and Loops make Ansible Playbooks more flexible.

I am keeping my Ansible learning beginner-friendly and focusing on the fundamentals before moving to advanced concepts.

#90DaysOfDevOps #Ansible #DevOps #DevOpsKaJosh #TrainWithShubham
