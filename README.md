# Prometheus-Grafana Monitoring Setup

A comprehensive monitoring solution using Prometheus for metrics collection and Grafana for visualization, monitoring Apache, system metrics, PostgreSQL, and system metrics.

## Project Structure

```
prometheus-grafana/
├── prometheus.yml              # Main Prometheus configuration
├── screenshots/               # Architecture and dashboard screenshots
│   ├── apache_expo.jpeg
│   ├── node_exporter.jpeg
│   └── postgre_expo.jpeg
└── systemd/                   # Systemd service files
    ├── apache_exporter.service
    ├── node_exporter.service
    └── postgres_exporter.service
```

## Features

- **Multi-Server Monitoring**: Monitor both old and new server infrastructure
- **Apache Monitoring**: Track Apache web server metrics and performance
- **PostgreSQL Monitoring**: Database health and performance metrics
- **System Metrics**: CPU, memory, disk, and network monitoring via Node Exporter
- **Grafana Dashboards**: Pre-configured visualization dashboards

##  Monitored Services

| Service | Port | Description |
|---------|------|-------------|
| Prometheus | 9090 | Metrics collection and storage |
| Apache Exporter | 9117 | Apache web server metrics |
| Node Exporter | 9100 | System and hardware metrics |
| PostgreSQL Exporter | 9187 | PostgreSQL database metrics |

##  Quick Start

### Prerequisites

- Ubuntu 20.04+ or similar Linux distribution
- Root or sudo access
- Docker (optional, for containerized deployment)

 **Access Prometheus UI**
   ```
   http://localhost:9090
   ```
### Exporter Configuration

Each exporter has its own systemd service file in the `systemd/` directory. Customize as needed:

- `apache_exporter.service` - Apache monitoring service
- `node_exporter.service` - System metrics service
- `postgres_exporter.service` - PostgreSQL monitoring service

##  Screenshots

Dashboard examples are available in the `screenshots/` directory:
- Apache metrics dashboard
- Node exporter system metrics
- PostgreSQL performance metrics

##  Security Considerations

- **Firewall Rules**: Ensure only authorized IPs can access exporter ports
- **Authentication**: Configure Prometheus basic auth or use a reverse proxy
- **SSL/TLS**: Enable HTTPS for Grafana and Prometheus in production
- **Secrets Management**: Never commit actual server IPs or credentials to Git

##  Monitoring Best Practices

1. **Set appropriate scrape intervals** based on your needs (default: 15s)
2. **Configure alerting rules** for critical metrics
3. **Set up retention policies** to manage disk space
4. **Regular backups** of Prometheus data and Grafana dashboards
5. **Monitor the monitors** - ensure exporters are running

##  Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

##  Resources

- [Prometheus Documentation](https://prometheus.io/docs/)
- [Grafana Documentation](https://grafana.com/docs/)
- [Node Exporter](https://github.com/prometheus/node_exporter)
- [Apache Exporter](https://github.com/Lusitaniae/apache_exporter)
- [MySQL Exporter](https://github.com/prometheus/mysqld_exporter)
- [PostgreSQL Exporter](https://github.com/prometheus-community/postgres_exporter)

##  Author

Bikram Raj Adhikari

## 🙏 Acknowledgments

- Prometheus community for excellent monitoring tools
- All exporter maintainers
- Grafana team for visualization platform

