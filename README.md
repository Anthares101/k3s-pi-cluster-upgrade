# K3S Pi Cluster Upgrade

The idea of this playbook is to automate upgrades of my [K3S cluster](https://github.com/anthares101/k3s-pi-cluster), including Linux and K3S versions. About the applications running in the cluster (including monitoring), the upgrades are managed by [Keel](https://keel.sh).

## Requisites

- You need Ansible of course
- The Ansible collections in the requirements file: `ansible-galaxy install -r requirements.yaml`
- The target systems should have a valid network configuration with static IPs and hostname and SSH access configured with private key.

## Configuration

You can tweak the next variables under the `group_vars` folder:
- `suffix_domain`: The domain suffix to use in the Grafana, Prometheus and AlertManager ingresses
- `grafana_from_email`: The admin email used in Grafana

## Usage

Just execute the playbook and go for a coffee:
```
ansible-playbook main.yaml -K
```

If you only need to execute part of it you can use the next tags (The names are self explanatory):
- `upgrade-linux`
- `upgrade-k3s-master`
- `upgrade-k3s-workers`
