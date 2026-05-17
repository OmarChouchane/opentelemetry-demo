# OpenTelemetry Demo - AWS EC2 Deployment

A comprehensive guide to deploying and testing the OpenTelemetry Astronomy Shop demo application on AWS EC2 using Docker Compose.

---

## 📋 Overview

This project demonstrates the successful deployment of the OpenTelemetry demo application on AWS infrastructure. The deployment includes a complete observability stack featuring:

- **Multi-language Microservices**: A distributed system spanning Java, Go, .NET, Python, Ruby, Node.js, and C++
- **Complete Observability**: Traces, metrics, and logs collection
- **Cloud-Native Architecture**: Containerized services orchestrated with Docker Compose

### Key Features

✅ **Full Microservice Architecture** - Real-world distributed system  
✅ **Multi-Protocol Tracing** - OpenTelemetry instrumentation across services  
✅ **Metrics & Dashboards** - Prometheus metrics with Grafana visualization  
✅ **Load Testing Ready** - Built-in load generation capabilities

---

## 🚀 Quick Start

### Prerequisites

- AWS EC2 instance (t3.medium or larger recommended)
- Docker and Docker Compose installed
- 20GB+ available disk space
- Port access: 80, 443, 3000 (Grafana), 6831 (Jaeger), 8080 (Locust)

### Deployment Steps

1. **Clone the Repository**

```bash
git clone <your-forked-repo-url>
cd opentelemetry-demo
```

2. **Pull Docker Images**

```bash
docker-compose pull
```

3. **Start Services**

```bash
docker-compose up -d
```

4. **Verify Deployment**

```bash
docker-compose ps
```

---

## 🔍 Observability Components

The following components have been tested and verified operational:

### 1. Grafana Dashboards

**URL**: `http://<ec2-ip>:3000`

Monitor real-time metrics and performance indicators across all services.

- Metrics visualization from Prometheus
- Pre-configured dashboards for microservices
- Custom alert and monitoring setup

![Grafana Dashboard]<img width="1920" height="973" alt="677682200_882600164845297_4299873477948562491_n" src="https://github.com/user-attachments/assets/d09ed7bd-bdbc-4f12-a815-3f37f29a5e3c" />


---

### 2. Jaeger Distributed Tracing

**URL**: `http://<ec2-ip>:16686`

Track distributed requests across the entire microservice architecture.

- End-to-end request tracing
- Service dependency mapping
- Performance bottleneck identification

![Jaeger UI]<img width="1920" height="975" alt="689221468_27253489090913349_8589601263391541974_n" src="https://github.com/user-attachments/assets/7baa4742-5215-4c2b-9f54-d473447bb656" />


---

### 3. Locust Load Generator

**URL**: `http://<ec2-ip>:8089`

Generate realistic load patterns and stress-test the system.

- Customizable load scenarios
- Real-time traffic simulation
- Performance metrics collection

![Locust Load Generator]<img width="1919" height="975" alt="670369562_1648727153029406_2903472964815502629_n" src="https://github.com/user-attachments/assets/fdc342bc-4120-4b5f-b7de-4b41c1b9a5ff" />


---

## 📊 Deployment Results

| Component         | Status         | Function                |
| ----------------- | -------------- | ----------------------- |
| Docker Compose    | ✅ Running     | Container orchestration |
| Grafana           | ✅ Operational | Metrics visualization   |
| Jaeger            | ✅ Operational | Distributed tracing     |
| Locust            | ✅ Operational | Load testing            |
| Prometheus        | ✅ Running     | Metrics collection      |
| All Microservices | ✅ Running     | Demo application        |

---

## 🛠️ Service Architecture

### Frontend Services

- **Frontend**: Next.js web application
- **Frontend Proxy**: Envoy proxy for traffic management

### Business Services

- **Cart**: Shopping cart management
- **Product Catalog**: Product inventory
- **Payment**: Payment processing
- **Shipping**: Shipping calculations
- **Recommendation**: ML-based recommendations
- **Checkout**: Checkout orchestration

### Infrastructure Services

- **Postgres**: Primary database
- **Redis**: Caching layer
- **Kafka**: Message broker
- **Load Generator**: Synthetic traffic generation

### Observability Stack

- **Jaeger**: Distributed tracing
- **Prometheus**: Metrics collection
- **Grafana**: Metrics visualization
- **OpenTelemetry Collector**: Telemetry aggregation

---

## 📈 Monitoring & Observability

### Key Metrics Available

1. **Application Performance**
   - Request latency distribution
   - Error rates by service
   - Throughput metrics

2. **Infrastructure Health**
   - Container resource usage
   - Network I/O metrics
   - Database connection pool status

3. **Business Metrics**
   - Transaction success rates
   - Cart abandonment tracking
   - Payment processing times

### Creating Custom Dashboards

Grafana dashboards can be customized to focus on specific metrics or services. Access Grafana settings to:

- Create new dashboards
- Set up alert thresholds
- Configure data sources
- Define custom metrics

---

## 🧪 Testing & Validation

### Load Testing with Locust

1. Access Locust at `http://<ec2-ip>:8089`
2. Set number of users and spawn rate
3. Monitor real-time metrics in Grafana
4. Observe traces in Jaeger for detailed request flows

### Tracing Custom Requests

Use Jaeger's search interface to:

- Filter by service name
- Search by operation name
- View request timelines
- Identify latency contributors

---

## 📝 Configuration

### Docker Compose Environment

Configuration is managed through:

- `.env` files for environment variables
- `docker-compose.yml` for service definitions
- `otel-config.yml` for OpenTelemetry collector settings

### Customization Points

- Modify resource limits in `docker-compose.yml`
- Adjust metric collection intervals in `otel-config.yml`
- Update application environment variables in `.env`

---

## 🔧 Troubleshooting

### Common Issues

**Port conflicts**: Ensure required ports are not in use

```bash
netstat -tuln | grep LISTEN
```

**Image pull failures**: Verify internet connectivity and Docker credentials

```bash
docker-compose pull --no-parallel
```

**Service startup delays**: Check logs for specific service

```bash
docker-compose logs <service-name>
```

### Checking Service Status

```bash
docker-compose logs -f
docker-compose stats
```

---

## 📚 Additional Resources

- [OpenTelemetry Documentation](https://opentelemetry.io/docs/)
- [OpenTelemetry Demo Repository](https://github.com/open-telemetry/opentelemetry-demo)
- [Grafana Documentation](https://grafana.com/docs/)
- [Jaeger Documentation](https://www.jaegertracing.io/docs/)
- [Docker Compose Reference](https://docs.docker.com/compose/reference/)

---

## 🤝 Contributing

This is a forked repository based on the official OpenTelemetry Demo project. For contributions to the main project, please visit [open-telemetry/opentelemetry-demo](https://github.com/open-telemetry/opentelemetry-demo).

---

## 📄 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

---

## 📞 Support

For issues or questions:

1. Check the troubleshooting section above
2. Review official OpenTelemetry documentation
3. Consult Docker and Docker Compose documentation
4. Check service-specific logs: `docker-compose logs <service>`

---

**Last Updated**: May 2026  
**Deployment Status**: ✅ Production Ready
