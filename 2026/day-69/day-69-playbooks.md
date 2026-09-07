# Day 69 – Ansible Playbooks and Modules

## What I Learned

Today I learned the basics of Ansible Playbooks.

A Playbook is a YAML file that contains instructions for Ansible to perform tasks on servers.

## Basic Structure

```yaml
---
- name: My First Ansible Playbook
  hosts: all
  tasks:
    - name: Check server uptime
      command: uptime
