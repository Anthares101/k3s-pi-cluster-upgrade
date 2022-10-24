# K3S Pi Cluster Upgrade

The idea of this playbook is to automate upgrades of my [K3S cluster](https://github.com/anthares101/k3s-pi-cluster), including Linux, K3S and also the monitoring stack. About the applications running in the cluster, the upgrades are managed by [Keel](https://keel.sh).

## Requisites

- You need Ansible of course
- The Ansible collections in the requirements file: `ansible-galaxy install -r requirements.yaml`
- The target systems should have a valid network configuration with static IPs and hostname and SSH access configured with private key.

## Usage

Just execute the playbook and go for a coffee:
```
ansible-playbook main.yaml -K
```

If you only need to execute part of it you can use the next tags (The names are self explanatory):
- `upgrade-linux`
- `upgrade-k3s-master`
- `upgrade-k3s-workers`
- `upgrade-k3s-monitoring`

## Troubleshooting

- If you find that the canal pods are crashing with this message in the logs: `flannel.1. Link has incompatible address` try deleting the `flannel.1` interface in all nodes: `sudo ip link delete flannel.1`.
