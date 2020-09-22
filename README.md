# ansible-netq-agent

A role for Installing NetQ3 agents on Cumulus Linux switches.

For more information, see the [NetQ documentation](https://docs.cumulusnetworks.com/display/NETQ/).

## Requirements

Cumulus Linux => 3.3
Cumulus NetQ => 3.x

## Role Variables

* `netq_backend_server`: IP of the netq server
* `netq_repo_version`: Version of the netq repo, e.g. "netq-3.0" or "netq-latest"

## Dependencies

None

## Notes

This role will handle the removal of existing 1.4, 2.4 and 3.0 repo entries in the event
you are changing the repo version from an earlier version. If the current version is
something other than 1.4, 2.4, or 3.0 (like netq-latest) this is left to the user. You could
simply change "state: present" to "state: absent" for your previous
version before updating to the new version or add the desired version
to be removed in the task: "Remove any old netq repos" in /task/main.yml

If the versions 1.4, 2.4 or 3.0 are already installed they will be upgraded to 3.1
or latest depending on `netq_repo_version`. If the Cumulus Linux host has no
agents already installed, then netq-agent and netq-apps (cli)
version 3.1 or latest will be installed.

This role currently doesn't consider Ubuntu or RHE/CentOS hosts, only Cumulus Linux.

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
