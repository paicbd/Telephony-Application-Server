#Telephony Application Server – Open Source Version

**Telephony Application Server (TAS)** is an open source telecom platform by PAiCore Technologies. It lets MNOs and MVNOs deliver VoIP services—call control, IVR, conferencing—through a no-code service builder and a scalable, high-availability core.

---

## Features

- **Core Call Control**: routing, forwarding, conferencing, termination
- **No-Code Service Creation**: visual IVR and voice-service builder
- **Scalability & High Availability**: Kubernetes-ready, clustered operation
- **Billing Integration**: hooks for usage-based charging engines
- **Media Processing**: transcoding, codec negotiation, QoS metrics
- **API-First Design**: REST and WebSocket APIs for CRM/OSS/BSS integration

---

## Included Components

- **Frontend**: React + Tailwind.js GUI for managing services
- **Backend**: Spring Boot microservices for SIP/CSCF logic

---

## Prerequisites

- Java 11 or newer
- Node.js 16+ and npm
- Redis 6+ (cluster mode recommended)
- PostgreSQL 12+
- Ubuntu 22.04 LTS or similar

> Ensure your DB user has CREATE/DROP privileges and Redis persistence is enabled.

---

## Installation & Configuration

1. **Clone repos**

   ```bash
   git clone https://github.com/paicbd/telephony-application-server-be.git
   git clone https://github.com/paicbd/telephony-application-server-fe.git
   ```

2. **Backend**

   ```bash
   cd telephony-application-server-be
   cp config.example.yaml config.yaml
   # Edit config.yaml with DB and Redis settings
   ./mvnw clean package
   java -jar target/tas-be.jar
   ```

3. **Frontend**

   ```bash
   cd ../telephony-application-server-fe
   npm install
   npm run build
   npm start
   ```

---

## Best Practices

- Use separate Redis/DB per environment (dev, staging, prod)
- Store secrets in Vault or Kubernetes Secrets, not in code
- Expose JMX/SIP metrics to Prometheus and Grafana
- Prototype with small PCAP samples before scaling

---

## Contributing

1. Fork the repo
2. Create a feature branch
3. Add tests and docs
4. Submit a pull request

---

## Support & Contact

This open source edition is community-maintained by PAiCore Technologies.  
For enterprise support or custom solutions, visit:  
https://paicore.tech/
