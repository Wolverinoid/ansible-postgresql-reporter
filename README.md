# PostgreSQL Exporter Role

This Ansible role installs and configures the PostgreSQL exporter for Prometheus monitoring.

## Requirements

- Ansible 2.9 or higher
- Target system with systemd
- PostgreSQL server accessible from the target system

## Role Variables

### Network Configuration

| Variable | Default | Description |
|----------|---------|-------------|
| `listen_interface` | `enp7s0` | Network interface to bind the exporter to |

### PostgreSQL Exporter Configuration

| Variable | Default | Description |
|----------|---------|-------------|
| `postgres_exporter_version` | `0.17.1` | Version of PostgreSQL exporter to install |
| `postgres_exporter_arch` | `linux-amd64` | Architecture of the exporter binary |

### PostgreSQL Connection Parameters

| Variable | Default | Description |
|----------|---------|-------------|
| `postgres_exporter_host` | `localhost` | PostgreSQL server hostname |
| `postgres_exporter_port` | `5432` | PostgreSQL server port |
| `postgres_exporter_user` | `postgres` | PostgreSQL username |
| `postgres_exporter_password` | `postgres` | PostgreSQL password |
| `postgres_exporter_dbname` | `postgres` | PostgreSQL database name |
| `postgres_exporter_sslmode` | `disable` | PostgreSQL SSL mode |

## Dependencies

None.

## Example Playbook

```yaml
- hosts: database_servers
  roles:
    - role: postgres_exporter
      vars:
        listen_interface: eth0
        postgres_exporter_version: "0.17.1"
        postgres_exporter_host: "db.example.com"
        postgres_exporter_user: "monitoring"
        postgres_exporter_password: "secure_password"
        postgres_exporter_dbname: "postgres"
```

## License

MIT

## Author Information

Your Name - your.email@example.com