# Deprovision responder
The `cloud_vpn/deprovision_responder` function will deprovision a VPN responder
on Azure.
It is performed by calling the `cloud_vpn/deprovision_responder` task from the role.
The task will process variables needed for deprovisioning a VM and call Azure Resource Manager.

Below is an example to deprovision a VPN responder VM on Azure.

```
- hosts: localhost

  tasks:
    - name: Deprovision responder
      include_role:
        name: ansible-network.azure
        tasks_from: cloud_vpn/deprovision_responder
      vars:
        cloud_vpn_name: myvpn
        cloud_vpn_responder_provisioner: azure
```

## Notes
None
