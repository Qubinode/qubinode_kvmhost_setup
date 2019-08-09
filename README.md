Role Name
=========
swygue.edge_host_setup

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

| variable  | definition |
| ------------- | ------------- |
| libvirt_host_networks | dictionary variable that creates libvirt network xml file. must set the name, mode, and bridge key |
| libvirt_host_pool | Content Cell  |
| kvm_host_ipaddr | default value is ansible_default_ipv4.address  |
| kvm_host_interface | default value is ansible_default_ipv4.interface |
| kvm_host_gw | default value is ansible_default_ipv4.gateway |

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    ---
    - name: Ensure that Libvirt is configured
      hosts: all
      roles:
        - role: swygue.edge_homst_setup
          libvirt_host_networks:
            - name: 'vmnet'
              mode: 'bridge'
              bridge: 'br01'
          kvm_host_ipaddr: '192.168.1.4'
          kvm_host_interface: 'eno1'
          kvm_host_gw: '192.168.1.1'
          #kvm_bridge_type: 'Bridge' 
          kvm_host_bootproto: 'dhcp'
          
   

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
