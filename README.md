# Monitoring Stack with Grafana, Prometheus, and cAdvisor

## Overview

This project provides a Docker-based monitoring stack that includes Grafana, Prometheus, and cAdvisor. It is designed to monitor containerized applications and visualize their performance metrics. 

- **Grafana**: An open-source platform for monitoring and observability that allows you to visualize and analyze metrics.
- **Prometheus**: An open-source systems monitoring and alerting toolkit that collects metrics from configured targets at given intervals.
- **cAdvisor**: An open-source container resource usage and performance analysis agent that provides container metrics to Prometheus.

## Features

- **Real-time monitoring**: Collect and visualize container metrics such as CPU, memory, and network usage.
- **Pre-configured dashboards**: Out-of-the-box Grafana dashboards for quick visualization of container metrics.
- **Scalable**: Easily add more targets to Prometheus as your infrastructure grows.

## Prerequisites

Before you begin, make sure you have the following installed:

- Docker
- Docker Compose

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name
```

### 2. Start the Monitoring Stack

To start the stack, use Docker Compose:

```bash
docker-compose up -d
```

This command will pull the necessary Docker images and start the services (Grafana, Prometheus, and cAdvisor) in detached mode.

### 3. Access the Services

- **Grafana**: [http://localhost:3000](http://localhost:3000)
  - Default username: `admin`
  - Default password: `admin` (You will be prompted to change this upon first login)
- **Prometheus**: [http://localhost:9090](http://localhost:9090)
- **cAdvisor**: [http://localhost:8080](http://localhost:8080)

### 4. Configure Grafana

1. **Add Prometheus as a Data Source**:
   - Navigate to `Configuration` > `Data Sources` in Grafana.
   - Select `Prometheus`.
   - Set the URL to `http://prometheus:9090`.
   - Click `Save & Test`.

2. **Import Dashboards**:
   - Go to `Create` > `Import` in Grafana.
   - Import the pre-configured dashboards for cAdvisor.

## Directory Structure

```plaintext
your-repo-name/
├── docker-compose.yml
├── grafana/
│   ├── provisioning/
│   │   ├── dashboards/
│   │   └── datasources/
│   └── dashboards/
├── prometheus/
│   └── prometheus.yml
└── README.md
```

- **docker-compose.yml**: Docker Compose file to set up the entire monitoring stack.
- **grafana/**: Contains Grafana configuration, including dashboards and provisioning files.
- **prometheus/**: Contains the Prometheus configuration file.

## Configuration

### Prometheus Configuration

The Prometheus configuration (`prometheus/prometheus.yml`) defines the scraping jobs for cAdvisor. You can add more jobs to scrape additional metrics from other services.

### Grafana Configuration

Grafana can be configured to load dashboards and data sources automatically. Custom dashboards can be added to the `grafana/dashboards/` directory.

## Troubleshooting

- **Grafana Not Loading**: Ensure that the Grafana service is running and accessible at `http://localhost:3000`.
- **Prometheus Not Scraping Metrics**: Verify that the `prometheus.yml` file is correctly configured and that Prometheus can access the cAdvisor endpoint.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes.

## Acknowledgments

- [Grafana](https://grafana.com/)
- [Prometheus](https://prometheus.io/)
- [cAdvisor](https://github.com/google/cadvisor)

---


