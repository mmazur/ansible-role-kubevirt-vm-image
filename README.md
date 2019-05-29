# ansible-role-kubevirt-vm-image

## Vars

### Top level

| Name                   | Default | Description |
| ---------------------- | ------- | ----------- |
| kubevirt_image_volumes | UNDEF   | List of volumes to be created |

### Volume spec

| Name            | Default        | Description |
| --------------- | -------------- | ----------- |
| name            | | |
| namespace       | | |
| size            | | |
| labels          | | |
| annotations     | | |
| source          | | |
| storage_class   | | |

## Examples

```yaml
---
- name: Create 
  hosts: localhost

  vars:
    kubevirt_image_volumes:
      - name: volume1
        namespace: default
        size: 100Mi
        source: "https://download.cirros-cloud.net/0.4.0/cirros-0.4.0-x86_64-disk.img"

      - name: volume2
        namespace: default
        size: 100Mi
        source: "docker://kubevirt/cirros-container-disk-demo:latest"

      - name: volume3
        namespace: default
        size: 100Mi
        source: "/tmp/disk.qcow2"

  roles:
    - kubevirt.vm_image

```


<!-- vim: set et ts=2 sw=2: -->
