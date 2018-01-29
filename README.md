# ansible-netq-agent

Install NetQ agent on Cumulus switches

For more information, see the [NetQ documentation](https://docs.cumulusnetworks.com/display/NETQ/).

## Requirements

Cumulus Linux 3.x

## Role Variables

* `netq_backend_server`: IP of the netq server

## Dependencies

None

## Example Playbook

```yaml
- hosts: switches
  tasks:
    - import_role:
        name: ansible-netq-agent
```

## License

Apache License 2.0

## Author Information

Location Labs by Avast
