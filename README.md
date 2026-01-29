# ansible-role-avahi

Ansible role to install and manage [Avahi](https://www.avahi.org/), the open-source implementation of Apple's Zeroconf/Bonjour protocol suite for local network service discovery.

## Requirements

- Ansible 2.10 or higher
- Supported operating systems:
  - Debian (bullseye, bookworm)
  - Ubuntu (focal, jammy, noble)
  - Arch Linux

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# Service name for avahi daemon
avahi_service_name: avahi-daemon

# Service state
avahi_service_state: started
avahi_service_enabled: true
```

### Variable Descriptions

- `avahi_service_name`: Name of the avahi service (default: `avahi-daemon`)
- `avahi_service_state`: Desired state of the service (default: `started`)
- `avahi_service_enabled`: Whether the service should be enabled at boot (default: `true`)

## Dependencies

None

## Example Playbook

### Basic Usage

```yaml
- hosts: servers
  roles:
    - role: frozenfoxx.avahi
```

### Custom Configuration

```yaml
- hosts: servers
  roles:
    - role: frozenfoxx.avahi
      vars:
        avahi_service_state: started
        avahi_service_enabled: true
```

## Supported Platforms

- **Debian-based**: Debian 11+, Ubuntu 20.04+
- **Arch Linux**: Current rolling release

## Handlers

- `Restart avahi-daemon`: Restarts the avahi-daemon service

## Tags

- `avahi`: Applied to all tasks in this role

## License

Apache-2.0

## Author Information

This role was created by frozenfoxx at Cult of Foxx.
