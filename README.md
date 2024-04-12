## Overview
This document outlines various Ansible playbook tasks used in the configuration and management of servers. Each task is described to provide insights into its purpose and functionality.

## Task Descriptions

### Directory and File Management
- **Create directory in /home/reza**: Ensures the `/home/reza/testdir1` directory exists, owned by user and group 'reza', with permissions set to 0755.
- **Create file in /home/reza/testdir1**: Creates an empty file or ensures it exists at `/home/reza/testdir1/file1`, with the same ownership and permissions as the directory.

### Debugging Tasks
- **Show my user name**: Displays the user name using the `user.name` variable.
- **Show my user email**: Displays the user email using the `user.email` variable.
- **Show my user list**: Shows the first item from the `user_list` array.
- **Show my user list 2**: Displays all elements of the `user_list2` array.
- **Extra vars**: Shows values of the `nodes` and `package_name` variables.
- **Show my var**: Outputs a custom variable `myvar` set to "salam".
- **Show my OS family**: Displays the OS family using the `ansible_os_family` variable.
- **Show my HTTP port as group vars**: Displays the HTTP port specified in group variables.

### Command Execution
- **Command module**: Executes `cat file1` within `/home/reza/testdir1` directory and captures the output.
- **Show result of command module**: Displays the output from the previous command task.
- **Command module Exercise for df -h**: Executes `df -h` and captures the output.
- **Show result of command module for df -h Exercise**: Displays the disk usage information from the `df -h` command.
- **Expect command**: Executes the `passwd` command for user 'devops', automating the input of the password '123'.

### Script and Shell Execution
- **Script Module**: Executes a script `test.sh`, creates `/home/reza/testdir2` and removes `/home/reza/testdir1`, with output registered.
- **Show value of script output**: Displays the output from executing `test.sh`.
- **Shell module for various exercises**: Executes shell commands (like `cat`, `df -h`, and `ps aux | grep ansible`), registers, and displays their outputs.

### File Operations
- **Copy module**: Copies `file1` to `/home/reza/testdir1`, sets ownership, permissions, and enables backup.
- **Fetch module**: Fetches `file1` from `/home/reza/testdir1` to a local directory, with options to flatten the structure and check checksums.

### User and Group Management
- **Group module**: Ensures a group 'mamad' is present on the system.
- **User module**: Manages a user 'user1' with home directory, shell, and password settings.

### Package Management
- **YUM and APT modules**: Manages packages via YUM or APT, with capabilities to install, update, remove, and list packages.

### Configuration Management
- **Template module**: Deploys a template `.bashrc.j2` to the user's home directory, with an option for backup.
- **Lineinfile and Replace modules**: Manages lines in files, specifically adding or replacing lines in `.bashrc` to modify aliases as specified.
