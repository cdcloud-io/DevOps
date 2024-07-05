# DevOps Curriculum Outline

DevOps is a great and high-paying career. DevOps, also commonly referred to or encompassed into SRE (Site Reliability Engineer), may lead to higher-paying jobs than just being a software developer. Most software developers have no clue as to the dangerous nature of the internet and typically only focus on the application layer (Layer 7). The role of a DevOps engineer is to work with developers on code that is as stateless as possible, manage state in config files, and secure the application from Layer 7 to Layer 1. This means a DevOps Engineer must know the fundamentals of a broad range of IT skills, from programming, infrastructure, networking, security, and availability. Memorizing only one way on a single cloud will do them no good if they don't understand the fundamentals.

DevOps is a field that requires a lot of self-motivation and never-ending ongoing training.

Here are the fundamentals that should be covered to give students a foundation to empower them to learn and deep-dive topics on their own.

## Introduction to DevOps
- **What is DevOps?**
  - Definition and scope of DevOps
  - Key principles: collaboration, automation, continuous improvement
  - Relation to other roles like SysAdmin and Developer

- **Understanding the origin and evolution of DevOps**
  - History and evolution of DevOps
  - Influential methodologies: Agile, Lean, ITIL
  - The DevOps movement and cultural shift

- **Benefits of cross-functional teams and automation patterns in DevOps**
  - Cross-functional teams: roles and collaboration
  - Benefits of automation in build, test, deploy
  - Common automation patterns: CI/CD, Infrastructure as Code (IaC)

## Linux
### Importance of Linux
- **Why Linux is important in DevOps**
  - Prevalence of Linux in servers and cloud environments
  - Linux as the foundation of many DevOps tools and platforms
  - Comparison with other operating systems (Windows, Mac)

### Desktop vs Servers
- **CLI Focus**
  - Importance of command-line interface (CLI) in server administration
  - Common CLI tools and their uses
  - Differences between desktop environments and server environments

### Curriculum
#### Users
- **Root and User Management**
  - Understanding the root account and its security implications
  - User management commands: adduser, usermod, passwd
  - Principles of least privilege and sudo usage

#### User Space vs Kernel Space
- **System Architecture**
  - Differences between user space and kernel space
  - Role of the kernel in managing hardware and system calls
  - How applications interact with the kernel

#### Basic Boot Process
- **System Boot Sequence**
  - Overview of the boot process: BIOS/UEFI, bootloader, kernel initialization
  - Role of GRUB in boot management
  - Understanding systemd and its role in system initialization

#### CLI Basic Commands
- **Essential Commands**
  - Navigating the filesystem: `ls`, `cd`, `pwd`
  - File manipulation: `cp`, `mv`, `rm`, `mkdir`
  - File permissions: `chmod`, `chown`, `umask`

#### Linux Directory Structure
- **Filesystem Hierarchy Standard (FHS)**
  - Key directories: `/`, `/bin`, `/etc`, `/home`, `/var`
  - Purpose and contents of each directory
  - Importance of directory structure in system administration

#### Runlevels
- **System Runlevels and Targets**
  - Traditional runlevels and their purposes
  - Transition to systemd targets
  - Managing runlevels/targets with systemd: `systemctl`

#### File Editors
- **Text Editors**
  - Basics of nano: editing, saving, and exiting
  - Introduction to vi/vim: modes, basic commands, editing
  - Advanced vi/vim usage and neovim extensions

#### File Systems
- **Common File Systems**
  - Characteristics of ext4 and its usage
  - Overview of ZFS and its advanced features (snapshots, replication)
  - Choosing the right file system for different use cases

#### Shells
- **Different Shells**
  - Overview of sh, bash, and zsh
  - Key features and differences
  - Writing portable shell scripts and considerations for cloud automation

#### Package Managers
- **Managing Software**
  - Using apt/apt-get/dpkg for Debian-based systems
  - Using yum/dnf for Red Hat-based systems
  - Installing, updating, and removing packages

#### Services
- **Service Management**
  - Understanding init.d and the transition to systemd
  - Managing services with systemd: `systemctl start`, `stop`, `enable`
  - Creating and configuring systemd service units

#### Logging
- **System Logging**
  - Using journalctl to query system logs
  - Understanding log files and their locations
  - Configuring and managing log rotation

#### Kernel Networking
- **Network Configuration and Management**
  - Basics of netfilter and iptables for firewall management
  - Configuring network interfaces and routing
  - Network troubleshooting tools: `ping`, `netstat`, `traceroute`

#### Containers
- **Containerization Fundamentals**
  - History of containers and their evolution
  - Differences between containers and virtual machines
  - Introduction to Docker and its architecture

#### Shell Scripting
- **Automating Tasks with Scripts**
  - Basics of writing and running bash scripts
  - Common scripting tasks: loops, conditionals, functions
  - Transition to Python for more complex automation tasks

#### Container Management
- **Using LXD and Docker**
  - Overview of LXD for system container management
  - Docker basics: images, containers, Dockerfile
  - Advanced Docker usage: Compose, Swarm, Kubernetes

#### Cloud-Native Foundation
- **Foundational Organizations**
  - Overview of the Cloud Native Computing Foundation (CNCF)
  - Key projects and their roles (Kubernetes, Prometheus, etc.)
  - The Linux Foundation and its impact on open-source software

## Git
- **Version Control with Git**
  - Basic git commands: clone, commit, push, pull
  - Branching and merging strategies
  - Collaboration workflows: GitFlow, forking, pull requests

## CI/CD Tools
- **Continuous Integration and Continuous Deployment**
  - Principles of CI/CD and its benefits
  - Common CI/CD tools: Jenkins, GitLab CI, CircleCI
  - Setting up and configuring CI/CD pipelines

### Common CI/CD Platforms
#### AWS CodePipeline
- **AWS CodePipeline Overview**
  - Integration with other AWS services
  - Creating and managing pipelines
  - Deploying applications to AWS infrastructure

#### GitHub Actions
- **GitHub Actions Overview**
  - Setting up workflows and actions
  - Integration with GitHub repositories
  - Using the marketplace for pre-built actions

### Differences Between AWS CodePipeline and GitHub Actions
- **Comparing Platforms**
  - Environment integration: AWS-centric vs. GitHub-centric
  - Ease of use: graphical interface vs. YAML-based configuration
  - Extensibility: AWS services vs. third-party integrations

## IaC (Infrastructure as Code)
- **Defining and Managing Infrastructure**
  - Writing procedural scripts with cloud shells and CLI tools
  - Using Terraform for declarative infrastructure management
  - Best practices for maintaining IaC repositories

## Kubernetes
- **Orchestrating Containers**
  - Kubernetes architecture: nodes, pods, services, and deployments
  - Managing Kubernetes clusters and resources
  - Extending Kubernetes with Helm, ArgoCD, Kustomize, and service meshes

## Data Types and Their Representation
- **Understanding Data Types**
  - Common data types: strings, numbers, booleans, arrays, objects
  - How data types are represented in JSON and YAML

### JSON (JavaScript Object Notation)
- **JSON Basics**
  - Syntax and structure of JSON
  - Representing data types in JSON:
    - Strings: `"key": "value"`
    - Numbers: `"key": 123`
    - Booleans: `"key": true`
    - Arrays: `"key": ["value1", "value2"]`
    - Objects: `"key": {"subkey": "subvalue"}`

### YAML (YAML Ain't Markup Language)
- **YAML Basics**
  - Syntax and structure of YAML
  - Representing data types in YAML:
    - Strings: `key: "value"`
    - Numbers: `key: 123`
    - Booleans: `key: true`
    - Arrays: 
      ```yaml
      key:
        - value1
        - value2
      ```
    - Objects:
      ```yaml
      key:
        subkey: subvalue
      ```

---
