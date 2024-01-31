# K3S Pi Cluster Upgrade

The idea of this playbook is to automate upgrades of my [K3S cluster](https://github.com/anthares101/k3s-pi-cluster), including Linux, K3S and the monitoting stack. About the applications running in the cluster, the upgrades are managed by [Keel](https://keel.sh).

## Requisites

If you used [this installation playbook](https://github.com/anthares101/k3s-pi-cluster) go ahead! If not, make sure you know what you are doing before running this.

## Usage

Just execute the playbook and go for a coffee:
```
ansible-playbook main.yaml -K
```

If you only need to execute part of it you can use the next tags (The names are self explanatory):
- `upgrade-linux`
- `upgrade-k3s-master`
- `upgrade-k3s-workers`
- `upgrade-monitoring`
