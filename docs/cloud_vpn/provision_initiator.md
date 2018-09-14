# Provision initiator
The `cloud_vpn/provision_initiator` function will provision a VPN initiator
on Azure.
It is performed by calling the `cloud_vpn/provision_initiator` task from the role.
The task will process variables needed for provisioning a VM and call Azure Resource Manager.

Below is an example to provision a VM that will be the initiator of the VPN on Azure.

```
- hosts: localhost

  tasks:
    - name: Provision initiator
      include_role:
        name: ansible-network.azure
        tasks_from: cloud_vpn/provision_initiator
      vars:
        cloud_vpn_name: myvpn
        cloud_vpn_initiator_provisioner: azure
        cloud_vpn_initiator_vpc_cidr: 10.0.0.0/16
        cloud_vpn_initiator_cidr: 10.0.0.0/24
        cloud_vpn_initiator_private_ip: 10.0.0.10
        cloud_vpn_initiator_ssh_private_key_file: /my/path/to/my/key
        cloud_vpn_initiator_instance_size: Standard_D2_V2
        cloud_vpn_initiator_image_id: "cisco:cisco-csr-1000v:csr-azure-byol:latest"
```

## Notes
None
