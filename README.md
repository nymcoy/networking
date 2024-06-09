
# Networking Project

## Purpose

The primary goal of this project is to provide a set of Ansible playbooks designed to configure a network infrastructure that allows accessing a home server with a non-static IP via a gateway in the cloud, which has a static IP. This setup ensures that the home server remains accessible despite changes in its IP address. The Vagrant configuration included in the project is intended to facilitate testing and validation of this setup on your local computer before deployment.

## Prerequisites

To run this project, you need to have the following software installed:

- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (or another Vagrant-compatible provider)
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Setup and Usage

### Step 1: Clone the Repository

Clone this repository to your local machine using the following command:

```bash
git clone <repository_url>
```

### Step 2: Navigate to the Project Directory

Go to the project directory:

```bash
cd networking
```

### Step 3: Start the Vagrant Environment

Start the Vagrant environment, which will set up the virtual machines according to the configuration in the `Vagrantfile`:

```bash
vagrant up
```

### Step 4: Provision the VMs with Ansible

Once the VMs are up and running, provision them using Ansible playbooks to configure the network infrastructure. Execute the following commands:

```bash
ansible-playbook ansible/gateway.yml
ansible-playbook ansible/router.yml
ansible-playbook ansible/remote.yml
ansible-playbook ansible/server.yml
```

## Playbooks

The project includes the following Ansible playbooks:

1. `gateway.yml` - Configures the gateway machine.
2. `router.yml` - Sets up the router machine.
3. `remote.yml` - Configures the remote machine.
4. `server.yml` - Sets up the server machine.

## Directory Structure

```
networking/
├── Vagrantfile
├── ansible/
│   ├── gateway.yml
│   ├── router.yml
│   ├── remote.yml
│   └── server.yml
```

## Troubleshooting

If you encounter any issues, try the following steps:

- Ensure all required software is installed.
- Check the Vagrant status using `vagrant status`.
- Re-provision the VMs using `vagrant provision`.

For further assistance, refer to the official documentation of [Vagrant](https://www.vagrantup.com/docs) and [Ansible](https://docs.ansible.com/ansible/latest/index.html).

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss any changes.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

- The [Vagrant](https://www.vagrantup.com/) and [Ansible](https://www.ansible.com/) teams for their excellent tools.
