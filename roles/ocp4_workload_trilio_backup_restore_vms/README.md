# ocp4_workload_trilio_backup_restore_vms

Deploys Trilio for Kubernetes on OpenShift for VM backup and restore workshops.

## What It Does

- Installs Trilio operator from certified-operators catalog
- Creates RBAC roles and bindings for workshop users
- Deploys TrilioVault Manager with license
- Configures OAuth integration with OpenShift
- Enables OpenShift console plugin
- Supports single or multiple users

## Key Variables

```yaml
# Namespace for Trilio installation
ocp4_workload_trilio_backup_restore_vms_namespace: trilio-system

# Operator channel
ocp4_workload_trilio_backup_restore_vms_operator_channel: 4.0.x

# User configuration
ocp4_workload_trilio_backup_restore_vms_dr_user: dr-admin1
ocp4_workload_trilio_backup_restore_vms_dr_user_password: ""
ocp4_workload_trilio_backup_restore_vms_user_count: 1

# S3 credentials for backup storage
ocp4_workload_trilio_backup_restore_vms_s3_accessKey: minio
ocp4_workload_trilio_backup_restore_vms_s3_secretKey: password
```

See [defaults/main.yml](defaults/main.yml) for all options.

## Example Usage

```yaml
- hosts: localhost
  roles:
    - role: trilio.workshop.ocp4_workload_trilio_backup_restore_vms
      vars:
        ocp4_workload_trilio_backup_restore_vms_namespace: trilio-system
        ocp4_workload_trilio_backup_restore_vms_dr_user: workshop-user
        ocp4_workload_trilio_backup_restore_vms_dr_user_password: workshop123
```

## Requirements

- OpenShift 4.x with cluster-admin access
- `kubernetes.core` Ansible collection
- `agnosticd.core` Ansible collection
- `install_operator` role (dependency)

## License

GPL-2.0-or-later
