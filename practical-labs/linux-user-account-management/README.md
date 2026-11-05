# Linux User and Account Management

## Project Overview

This practical lab demonstrates how to manage Linux user accounts, group memberships, and file ownership using Bash commands.

The scenario follows an employee's lifecycle within an organisation: joining the system, receiving access to the required groups and project resources, changing responsibilities, and eventually leaving the organisation.

The exercise highlights the role of user account administration in maintaining appropriate access to organisational systems and resources.

## Objectives

- Create a Linux user account.
- Assign a primary group to a user.
- Transfer ownership of a project file.
- Add a supplementary group without replacing existing group memberships.
- Delete a user account and remove an associated group.
- Apply the principle of least privilege when managing access.

## Scenario

An organisation hires a new employee with the username `researcher9` for its Research department.

The exercise covers the following stages:

1. Create the `researcher9` user account.
2. Assign `research_team` as the user's primary group.
3. Transfer ownership of a project file to the new user.
4. Add `sales_team` as a supplementary group when the employee takes on additional responsibilities.
5. Delete the user account when the employee leaves the organisation.

**Lab environment:** The exercise begins with the user `analyst` logged in and `/home/analyst` as the current working directory.

## Commands and Implementation

All commands in this lab are executed with `sudo` because user and group administration requires elevated privileges.

| Command | Purpose |
|---|---|
| `sudo useradd researcher9` | Creates the new user account. |
| `sudo usermod -g research_team researcher9` | Assigns `research_team` as the primary group. |
| `sudo chown researcher9 /home/researcher2/projects/project_r.txt` | Changes the file owner to `researcher9`. |
| `sudo usermod -a -G sales_team researcher9` | Adds `sales_team` as a supplementary group while preserving existing supplementary memberships. |
| `sudo userdel researcher9` | Deletes the user account. |
| `sudo groupdel researcher9` | Removes the automatically created group associated with the user, when no longer required. |

## Key Concepts

### Authentication and User Identity

Authentication is the process of verifying that a user is who they claim to be. Individual Linux user accounts provide distinct identities that help systems manage and control access.

### Primary and Supplementary Groups

- **Primary group:** The main group associated with a user account. In this exercise, `research_team` is assigned as the primary group.
- **Supplementary group:** An additional group that can provide access to resources. The `sales_team` group is added without changing the user's primary group.

### User Lifecycle Management

User access must be managed throughout the employee lifecycle:

- **Onboarding:** Create accounts and assign appropriate access.
- **Role changes:** Update group memberships and resource ownership as responsibilities change.
- **Offboarding:** Remove accounts when employees leave the organisation.

### File Ownership

Linux associates files with owners and groups. The `chown` command changes file ownership, allowing responsibility for a resource to be transferred to another user.

### Principle of Least Privilege

Users should receive only the access necessary to perform their responsibilities. Careful management of accounts, group memberships, and file ownership helps reduce unnecessary access.

## Skills Demonstrated

- Linux user account administration
- User creation and deletion
- Primary and supplementary group management
- File ownership management
- Bash command-line operations
- Privileged command execution using `sudo`
- User lifecycle and access management
- Application of the principle of least privilege

## Learning Outcomes

This exercise provided practical experience in creating and deleting Linux user accounts, managing group memberships, and transferring file ownership.

These activities build foundational knowledge relevant to identity and access management (IAM), Linux system administration, and security operations.

## Training Context

- **Programme:** Google Cybersecurity Certificate
- **Provider:** Google
- **Learning platform:** Coursera
- **Activity:** Manage user access in Linux
- **Status:** Completed practical exercise

---

*This repository documents a guided training exercise completed in a controlled lab environment. The commands and scenario are presented for educational and cybersecurity portfolio purposes.*
