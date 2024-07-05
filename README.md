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
  - Advanced vi/vim usage and neovim extensions (optional)

#### File Systems
- **Common File Systems**
  - Characteristics of ext4 and its usage
  - Overview of ZFS and its advanced features (snapshots, replication)
  - Choosing the right file system for different use cases (optional)

#### Shells
- **Different Shells**
  - Overview of sh, bash
  - Key features and differences
  - Writing portable shell scripts and considerations for cloud automation
 
#### Remote connecting using SSH (like RDP for Windows but better)
SSH (Secure Shell) is a powerful and secure protocol used to connect to and manage Linux and Unix-like systems remotely. Just as Remote Desktop Protocol (RDP) is commonly used to access Windows systems, SSH is the standard method for accessing Linux systems.

### Why SSH is Important

- **Security**: SSH provides strong encryption, ensuring that data transmitted between the client and server is secure and protected from eavesdropping.
- **Versatility**: SSH is not just for remote login; it can be used for executing commands, transferring files, and more.
- **Portability**: SSH can be used across different platforms and operating systems.

### Key Features of SSH

#### SSH Keys

SSH keys are a pair of cryptographic keys (a private key and a public key) used for authenticating users in a secure manner. Using SSH keys is more secure than password-based authentication.

##### NOTE: most cloud provisioned linux vm do NOT allow for password based auth, and must use SSH keys

**Creating SSH Keys**:
```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
This command generates a new SSH key pair. The `-t rsa` specifies the type of key to create, `-b 4096` specifies the number of bits in the key, and `-C` adds a comment to the key.

**Adding SSH Keys to the SSH Agent**:
```sh
ssh-add ~/.ssh/id_rsa
```
This command adds your private key to the SSH agent, which manages your keys and makes them available for SSH sessions.

**Copying SSH Keys to a Server**:
```sh
ssh-copy-id user@server
```
This command copies your public key to the server, allowing you to authenticate without a password.

#### SSH Configuration

SSH configuration files can be used to simplify and manage multiple SSH connections.

**Example `.ssh/config` File**:
```
Host myserver
    HostName myserver.example.com
    User myusername
    IdentityFile ~/.ssh/id_rsa
    Port 22
```
This configuration allows you to connect to `myserver` with a simple command (`ssh myserver`) instead of specifying the hostname, username, and other details each time.

#### Basic SSH Commands

- **Connecting to a Server**:
  ```sh
  ssh user@hostname
  ```

- **Executing a Command on a Remote Server**:
  ```sh
  ssh user@hostname "command"
  ```

- **Transferring Files with SCP**:
  ```sh
  scp file.txt user@hostname:/path/to/destination
  ```

#### SSHFS (SSH Filesystem)

SSHFS allows you to mount a remote filesystem over SSH, enabling you to access files on a remote server as if they were on your local machine.

**Mounting a Remote Filesystem**:
```sh
sshfs user@hostname:/remote/path /local/mount/point
```

**Unmounting a Remote Filesystem**:
```sh
fusermount -u /local/mount/point
```

#### Advanced Utilities

- **`ssh-add`**: Adds private key identities to the SSH agent.
- **`ssh-copy-id`**: Copies public keys to a remote server for key-based authentication.


#### Package Managers
- **Managing Software**
  - Using apt/apt-get/dpkg for Debian-based systems
  - Using yum/dnf for Red Hat-based systems
  - Installing, updating, and removing packages

#### Services
- **Service Management**
  - Understanding init.d and the transition to systemd
  - Managing services with systemd: `systemctl start`, `stop`, `enable`
  - Creating and configuring systemd service units (how to make an app a service)

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
 
# Compiling/Building Artifact for Docker Registries

Understanding how different programming languages compile and run is crucial for effectively packaging them into containers. Here’s an overview of the compilation and runtime processes for Java, Go, Node.js, and Python, and how to package applications written in these languages into containers.

### Java
Java is a statically typed, compiled language that runs on the Java Virtual Machine (JVM).

#### Compilation Process
1. **Source Code**: Written in `.java` files.
2. **Compilation**: Compiled into bytecode using the `javac` compiler, generating `.class` files.
3. **Execution**: Bytecode is executed on the JVM.

#### Packaging into Containers
1. **Dockerfile Example**:
   ```Dockerfile
   # Use an official OpenJDK runtime as a parent image
   FROM openjdk:11-jre-slim

   # Set the working directory in the container
   WORKDIR /app

   # Copy the compiled jar file to the container
   COPY target/myapp.jar /app/myapp.jar

   # Command to run the jar file
   ENTRYPOINT ["java", "-jar", "myapp.jar"]
   ```

2. **Build and Run**:
   ```sh
   # Build the Docker image
   docker build -t my-java-app .

   # Run the Docker container
   docker run -d -p 8080:8080 my-java-app
   ```

### Go
Go (Golang) is a statically typed, compiled language known for its simplicity and performance.

#### Compilation Process
1. **Source Code**: Written in `.go` files.
2. **Compilation**: Compiled into a standalone binary using the `go build` command.
3. **Execution**: The binary is executed directly on the operating system.

#### Packaging into Containers
1. **Dockerfile Example**:
   ```Dockerfile
   # Use the official Golang image to build the application
   FROM golang:1.16-alpine as builder

   # Set the working directory inside the container
   WORKDIR /app

   # Copy the source code to the container
   COPY . .

   # Build the Go app
   RUN go build -o myapp .

   # Use a minimal base image
   FROM alpine:latest

   # Set the working directory inside the container
   WORKDIR /app

   # Copy the binary from the builder stage
   COPY --from=builder /app/myapp .

   # Command to run the binary
   ENTRYPOINT ["./myapp"]
   ```

2. **Build and Run**:
   ```sh
   # Build the Docker image
   docker build -t my-go-app .

   # Run the Docker container
   docker run -d -p 8080:8080 my-go-app
   ```

### Node.js
Node.js is a runtime environment that allows the execution of JavaScript on the server side.

#### Execution Process
1. **Source Code**: Written in `.js` files.
2. **Execution**: Run directly using the Node.js runtime.

#### Packaging into Containers
1. **Dockerfile Example**:
   ```Dockerfile
   # Use the official Node.js image
   FROM node:14

   # Set the working directory inside the container
   WORKDIR /app

   # Copy package.json and package-lock.json
   COPY package*.json ./

   # Install dependencies
   RUN npm install

   # Copy the rest of the application code
   COPY . .

   # Expose the application port
   EXPOSE 8080

   # Command to run the app
   CMD ["node", "app.js"]
   ```

2. **Build and Run**:
   ```sh
   # Build the Docker image
   docker build -t my-node-app .

   # Run the Docker container
   docker run -d -p 8080:8080 my-node-app
   ```

### Python
Python is an interpreted, dynamically typed language.

#### Execution Process
1. **Source Code**: Written in `.py` files.
2. **Execution**: Run directly using the Python interpreter.

#### Packaging into Containers
1. **Dockerfile Example**:
   ```Dockerfile
   # Use the official Python image
   FROM python:3.9-slim

   # Set the working directory inside the container
   WORKDIR /app

   # Copy the requirements file and install dependencies
   COPY requirements.txt .
   RUN pip install --no-cache-dir -r requirements.txt

   # Copy the rest of the application code
   COPY . .

   # Command to run the app
   CMD ["python", "app.py"]
   ```

2. **Build and Run**:
   ```sh
   # Build the Docker image
   docker build -t my-python-app .

   # Run the Docker container
   docker run -d -p 8080:8080 my-python-app
   ```

By understanding these languages' compilation and runtime processes, you can effectively package and deploy applications in containers, ensuring consistent and isolated environments.

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

Advanced Topics

# Linux Kernel Features around Containers

Understanding the core components of how containers work is essential. Containers are not VMs; they are more like lightweight, isolated environments or service wrappers. LXD and Docker are container management systems that rely on various Linux kernel components and user-space tools to facilitate their functionality. Here are the key Linux components that underpin LXD and Docker:

### Linux Kernel Features

1. **Namespaces**
   - **PID Namespace**: Isolates process IDs so that processes inside a container have their own PID space.
   - **Net Namespace**: Provides isolated network stacks, including interfaces, routing tables, and IP addresses.
   - **IPC Namespace**: Isolates inter-process communication mechanisms (e.g., System V IPC, POSIX message queues).
   - **UTS Namespace**: Allows containers to have their own hostname and domain name.
   - **Mount Namespace**: Isolates filesystem mount points, allowing each container to have its own filesystem hierarchy.
   - **User Namespace**: Provides user and group ID isolation, enabling containers to run as a non-root user on the host.

2. **Control Groups (cgroups)**
   - **Resource Limitation**: Limits the resources (CPU, memory, disk I/O) that a container can use.
   - **Prioritization**: Sets priority levels for resource access.
   - **Accounting**: Tracks resource usage by each container.
   - **Control**: Freezes and resumes groups of processes, making it possible to pause and resume containers.

3. **Seccomp (Secure Computing Mode)**
   - Provides a mechanism to restrict system calls that a container can make, enhancing security.

4. **Capabilities**
   - Allows fine-grained control over the privileges that a containerized process can have, reducing the need for full root privileges.

5. **OverlayFS**
   - A type of union filesystem that allows multiple filesystems to be overlaid, enabling the creation of layers used by Docker images.

6. **AppArmor/SELinux**
   - Provides mandatory access control (MAC) to restrict what a containerized process can do, adding an extra layer of security.

### User-Space Tools and Libraries

1. **LXC (Linux Containers)**
   - The foundation for LXD, LXC provides tools and templates to create and manage containers using the kernel's namespaces and cgroups.

2. **liblxc**
   - A library used by LXD for managing LXC containers programmatically.

3. **containerd**
   - An industry-standard core container runtime that manages the container lifecycle (creation, execution, and destruction) and is used by Docker.

4. **runc**
   - A CLI tool for spawning and running containers according to the Open Container Initiative (OCI) specification. It is used by Docker as the default low-level container runtime.

5. **criu (Checkpoint/Restore In Userspace)**
   - Used by LXD for live migration of containers. It allows for checkpointing a running container and restoring it later or on another machine.

### LXD-Specific Components

1. **LXD Daemon**
   - The central service for LXD that handles API requests, manages container instances, networks, storage pools, and more.

2. **LXD Client**
   - The command-line client (`lxc`) used to interact with the LXD daemon.

3. **ZFS, Btrfs, and Other Filesystems**
   - LXD can use advanced filesystems like ZFS and Btrfs to provide efficient storage management features like snapshots and clones.

### Docker-Specific Components

1. **Docker Daemon (`dockerd`)**
   - The core service that manages Docker containers, images, networks, and storage.

2. **Docker CLI (`docker`)**
   - The command-line interface used to interact with the Docker daemon.

3. **Docker Images**
   - Read-only templates used to create containers. Images are composed of multiple layers stacked using OverlayFS.

4. **Docker Compose**
   - A tool for defining and running multi-container Docker applications using a YAML file.

### Example: Basic Docker Workflow

Here’s a simple example to demonstrate a basic Docker workflow:

1. **Pull an Image**
   ```sh
   docker pull nginx
   ```

2. **Run a Container**
   ```sh
   docker run -d -p 80:80 --name mynginx nginx
   ```

3. **List Running Containers**
   ```sh
   docker ps
   ```

4. **Stop a Container**
   ```sh
   docker stop mynginx
   ```

5. **Remove a Container**
   ```sh
   docker rm mynginx
   ```

### Example: Basic LXD Workflow

Here’s a simple example to demonstrate a basic LXD workflow:

1. **Initialize LXD**
   ```sh
   lxd init
   ```

2. **Launch a Container**
   ```sh
   lxc launch ubuntu:20.04 mycontainer
   ```

3. **List Running Containers**
   ```sh
   lxc list
   ```

4. **Stop a Container**
   ```sh
   lxc stop mycontainer
   ```

5. **Delete a Container**
   ```sh
   lxc delete mycontainer
   ```

These Linux components and tools together provide the foundation for containerization, enabling systems like LXD and Docker to offer robust, isolated, and manageable environments for applications.
