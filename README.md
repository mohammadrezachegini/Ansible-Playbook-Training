# Ansible-Playbook-Training

## Project Overview
The Ansible-Playbook-Training repository provides a collection of Ansible playbooks designed to help users understand and master Ansible. These playbooks cover various use cases and scenarios, demonstrating the power and flexibility of Ansible in automating IT infrastructure tasks.

## Features
- **Comprehensive Playbooks:** A wide range of playbooks for different scenarios.
- **Step-by-Step Instructions:** Detailed instructions for each playbook to guide users through the process.
- **Best Practices:** Follow best practices for writing and organizing Ansible playbooks.
- **Modular Design:** Playbooks are designed to be reusable and modular.

## Requirements
- Ansible installed on your machine.
- Access to target nodes (e.g., via SSH) with the necessary permissions.

## Installation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/mohammadrezachegini/Ansible-Playbook-Training.git
    cd Ansible-Playbook-Training
    ```

2. **Install Ansible:**
    Follow the [official Ansible installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) to install Ansible on your machine.

## Usage

Each playbook is located in a separate directory within the repository. Navigate to the desired playbook directory and follow the instructions provided in the `README.md` file within that directory.

### Example Playbook

#### `basic-setup/`
This directory contains a basic setup playbook for configuring a new server.

- **site.yml:** Main playbook file.
- **roles/**: Directory containing Ansible roles.

##### Usage
1. **Navigate to the playbook directory:**
    ```sh
    cd basic-setup
    ```

2. **Run the playbook:**
    ```sh
    ansible-playbook site.yml -i inventory
    ```

### Directory Structure

- **`basic-setup/`**: Basic server setup playbook.
- **`web-server/`**: Playbook for setting up a web server.
- **`database/`**: Playbook for setting up a database server.
- **`load-balancer/`**: Playbook for configuring a load balancer.
- **`monitoring/`**: Playbook for setting up monitoring tools.
- **`security/`**: Playbook for applying security configurations.

## Playbook Structure

### `site.yml`
The main playbook file that includes all the roles and tasks.

### `roles/`
Contains roles, which are reusable sets of tasks. Each role has its own directory and typically includes:
- **tasks/**: Main list of tasks to be executed by the role.
- **handlers/**: Handlers, which are tasks triggered by other tasks.
- **files/**: Files to be transferred to the target machines.
- **templates/**: Jinja2 templates to be rendered on the target machines.
- **vars/**: Variables used by the role.
- **defaults/**: Default variables for the role.
- **meta/**: Metadata about the role.

## Task Descriptions

### Directory and File Management
- **Create directory in /home/reza:** Ensures the `/home/reza/testdir1` directory exists, owned by user and group 'reza', with permissions set to 0755.
- **Create file in /home/reza/testdir1:** Creates an empty file or ensures it exists at `/home/reza/testdir1/file1`, with the same ownership and permissions as the directory.

### Debugging Tasks
- **Show my user name:** Displays the user name using the `user.name` variable.
- **Show my user email:** Displays the user email using the `user.email` variable.
- **Show my user list:** Shows the first item from the `user_list` array.
- **Show my user list 2:** Displays all elements of the `user_list2` array.
- **Extra vars:** Shows values of the `nodes` and `package_name` variables.
- **Show my var:** Outputs a custom variable `myvar` set to "salam".
- **Show my OS family:** Displays the OS family using the `ansible_os_family` variable.
- **Show my HTTP port as group vars:** Displays the HTTP port specified in group variables.

### Command Execution
- **Command module:** Executes `cat file1` within `/home/reza/testdir1` directory and captures the output.
- **Show result of command module:** Displays the output from the previous command task.
- **Command module Exercise for df -h:** Executes `df -h` and captures the output.
- **Show result of command module for df -h Exercise:** Displays the disk usage information from the `df -h` command.
- **Expect command:** Executes the `passwd` command for user 'devops', automating the input of the password '123'.

### Script and Shell Execution
- **Script Module:** Executes a script `test.sh`, creates `/home/reza/testdir2` and removes `/home/reza/testdir1`, with output registered.
- **Show value of script output:** Displays the output from executing `test.sh`.
- **Shell module for various exercises:** Executes shell commands (like `cat`, `df -h`, and `ps aux | grep ansible`), registers, and displays their outputs.

### File Operations
- **Copy module:** Copies `file1` to `/home/reza/testdir1`, sets ownership, permissions, and enables backup.
- **Fetch module:** Fetches `file1` from `/home/reza/testdir1` to a local directory, with options to flatten the structure and check checksums.

### User and Group Management
- **Group module:** Ensures a group 'mamad' is present on the system.
- **User module:** Manages a user 'user1' with home directory, shell, and password settings.

### Package Management
- **YUM and APT modules:** Manages packages via YUM or APT, with capabilities to install, update, remove, and list packages.

### Configuration Management
- **Template module:** Deploys a template `.bashrc.j2` to the user's home directory, with an option for backup.
- **Lineinfile and Replace modules:** Manages lines in files, specifically adding or replacing lines in `.bashrc` to modify aliases as specified.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Ansible Community
- Contributors and Supporters

## Troubleshooting
- **Connection Issues:** Ensure you have SSH access to the target nodes and the correct inventory configuration.
- **Runtime Issues:** Check logs for errors and ensure your environment variables are set correctly.

## Contact
For any issues or questions, please open an issue in the repository or contact the repository owner.

## Screenshots

### Playbook Execution
![Playbook Execution](path/to/screenshot1.png)

### Setup Results
![Setup Results](path/to/screenshot2.png)

## Additional Resources

- [Ansible Documentation](https://docs.ansible.com/)
- [Ansible Galaxy](https://galaxy.ansible.com/)
- [Ansible Best Practices](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)
