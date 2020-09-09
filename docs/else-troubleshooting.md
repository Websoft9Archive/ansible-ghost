# Troubleshooting

We collect the most common faults in using Ghost for your reference:

> Most faults are closely related to the instance provider,cloud platforms. Provided you're sure the fault is caused by cloud platform, refer to [Cloud Platform Documentation](https://support.websoft9.com/docs/faq/tech-instance.html)

#### How can I check the error logs?

You can find the keywords **Failed** or **error** from the logs directory: `/data/logs`

#### Can't start Ghost service?

Insufficient disk space and memory, incorrect configuration file may cause the failure to start the service. 

It is recommended to first check through the command.

```shell
# restart Ghost service
systemctl status ghost
journalctl -u ghost

# view disk space
df -lh

# view memory rate
free -lh
```

#### Failed to open default theme casper folder?

As the ghost official notes, Casper is part of the kernel and only the self-uploaded themes can be modified.
