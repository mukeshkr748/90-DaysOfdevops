# Day 72 – Ansible Basic Project

## Objective

Practiced a basic Ansible project using custom roles.

## What I Practiced

- Ansible project structure
- Docker role
- Nginx role
- Master playbook
- Running multiple roles from one playbook

## Project Structure

```text
day-72/
├── site.yml
└── roles/
    ├── docker/
    │   └── tasks/
    │       └── main.yml
    └── nginx/
        └── tasks/
            └── main.yml
Docker Role

Created a basic Docker role and tested it with a debug task.

Nginx Role

Created a basic Nginx role and tested it with a debug task.

Master Playbook

The site.yml playbook runs both Docker and Nginx roles.

Result

Both roles were successfully executed through the master playbook.

This was a beginner-level practice project focused on understanding how Ansible roles work together.
