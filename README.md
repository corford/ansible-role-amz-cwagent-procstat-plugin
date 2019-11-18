# Ansible Role: amz-cwagent-procstat-plugin

Ansible role that attempts to manage the Amazon CloudWatch Agent "procstat" plugin.

## Usage

By default, this role will use the "exe" filter for matching. You can change this by defining your own
config template (e.g. at playbook level) and pointing the `amz_cwagent_procstat_plugin_fragment_template` variable to it.

#### To start monitoring a process:

```
- include_role:
    name: amz-cwagent-procstat-plugin
  vars:
    amz_cwagent_procstat_plugin_fragment_match_string: "sshd"
    amz_cwagent_procstat_plugin_fragment_suffix: "sshd"
```

#### To stop monitoring a process:

```
- include_role:
    name: amz-cwagent-procstat-plugin
  vars:
    amz_cwagent_procstat_plugin_fragment_suffix: "sshd"
    amz_cwagent_procstat_plugin_fragment_action: remove
```

## License

MIT / BSD
