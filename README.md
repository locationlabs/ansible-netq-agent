# ansible-netq-agent

Install NetQ agent on Cumulus switches

For more information, see the [NetQ documentation](https://docs.cumulusnetworks.com/display/NETQ/).

## Requirements

Cumulus Linux 3.x

## Role Variables

* `netq_backend_server`: IP of the netq server
* `netq_repo_version`: Version of the netq repo, e.g. "netq-1.4"

## Dependencies

None

## Notes

This role will not handle the removal or existing repo entries in the event
you are changing the repo version. This is left to the user. You could
simply change "state: present" to "state: absent" for you previous
version before updating to the new version.  


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
