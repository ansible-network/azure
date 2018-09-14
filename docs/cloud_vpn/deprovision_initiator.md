# Deprovision initiator
The `cloud_vpn/deprovision_initiator` function will deprovision a VPN initiator
on Azure.
It is performed by calling the `cloud_vpn/deprovision_initiator` task from the role.
The task will process variables needed for deprovisioning a VM and call Azure Resource Manager.

Below is an example to deprovision a VPN initiator VM on Azure.

```
- hosts: localhost

  tasks:
    - name: Deprovision initiator
      include_role:
        name: ansible-network.azure
        tasks_from: cloud_vpn/deprovision_initiator
      vars:
        cloud_vpn_name: myvpn
        cloud_vpn_initiator_provisioner: azure
```

## Notes
None
