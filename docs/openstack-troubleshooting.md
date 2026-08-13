# OpenStack Troubleshooting Notes

## 2026-08-13

- **Instance stuck in BUILD**: Check `nova list` and `nova show <id>` for error messages. Common cause: insufficient quota or image metadata issue.
- **Neutron DHCP agent not responding**: Restart `neutron-dhcp-agent` and verify `dhcp_agent` count matches `neutron agent-list`.
- **Cinder volume detach failure**: Force detach via `cinder force-detach <volume-id>` after confirming the guest OS has unmounted the device.
- **Horizon 503 errors**: Often due to keystone token expiry — check `/var/log/apache2/horizon_error.log` and restart `apache2`.

## Quick commands

```bash
# Check compute service state
openstack compute service list

# Show hypervisor stats
openstack hypervisor stats show

# Tail nova scheduler logs
tail -f /var/log/nova/nova-scheduler.log
```