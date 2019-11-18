# Ansible Role: amz-cwagent-procstat-plugin

Ansible role that attempts to manage the Amazon CloudWatch Agent "procstat" plugin.

## Usage

To start monitoring a process:

```
- include_role:
    name: amz-cwagent-procstat-plugin
  vars:
    amz_cwagent_procstat_plugin_fragment_suffix: "sshd"
    amz_cwagent_procstat_plugin_fragment_contents: |
      {
        "exe": "/usr/sbin/sshd",
        "measurement": [
          "cpu_time",
          "cpu_time_system",
          "cpu_time_user",
          "cpu_usage",
          "memory_data",
          "memory_rss",
          "memory_swap",
          "read_bytes",
          "write_bytes",
          "read_count",
          "write_count"
        ]
      }
```

To stop monitoring a process:

```
- include_role:
    name: amz-cwagent-procstat-plugin
  vars:
    amz_cwagent_procstat_plugin_fragment_suffix: "sshd"
    amz_cwagent_procstat_plugin_fragment_action: remove
```

## License

MIT / BSD
