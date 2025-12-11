# Trilio Workshop Collection

Ansible collection for deploying Trilio backup and restore workshops on OpenShift.

## Installation

```bash
ansible-galaxy collection install trilio.workshop
```

## Roles

### ocp4_workload_trilio_backup_restore_vms

Deploys Trilio for Kubernetes on OpenShift with VM backup/restore capabilities. Configures OAuth integration, RBAC, and console plugin.

## Quick Start

```yaml
- name: Deploy Trilio Workshop
  hosts: localhost
  tasks:
    - name: Install Trilio workload
      ansible.builtin.include_role:
        name: trilio.workshop.ocp4_workload_trilio_backup_restore_vms
      vars:
        ocp4_workload_trilio_backup_restore_vms_namespace: trilio-system
        ocp4_workload_trilio_backup_restore_vms_dr_user: dr-admin1
        ocp4_workload_trilio_backup_restore_vms_dr_user_password: changeme
```

## Requirements

- OpenShift 4.x cluster
- cluster-admin access
- `kubernetes.core` collection
- `agnosticd.core` collection

## License

GPL-2.0-or-later
