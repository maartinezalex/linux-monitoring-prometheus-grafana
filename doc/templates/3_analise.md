# SYSTEM REQUIREMENTS
This document describes the requirements for the project "Monitoring System with Prometheus and Grafana", specifying the functionality it will provide and how it will operate.

## General Description

This project aims to implement a flexible and practical monitoring solution based on Prometheus, Grafana, Node Exporter, and Alertmanager, designed for small and medium-sized enterprises that are starting their digital transformation and lack the resources to properly monitor their infrastructure.  
The main objective is to create a reproducible technical guide that enables real-time infrastructure visibility, allowing anomalies to be detected as they occur and even before they impact other aspects such as productivity or equipment availability.  
Therefore, the structure is divided into two parts: a practical deployment on virtual machines to demonstrate how it works, and a technical documentation component oriented towards potential commercialization.

## Functionalities
Below are the main functionalities the monitoring system will provide:

1. Metrics collection.
   - Description: Collection of key data such as CPU, memory, disk, and network usage.
   - Responsible: Node Exporter.

2. Metrics storage and processing.
   - Description: Prometheus collects metrics from exporters and stores them in real time for later processing.
   - Responsible: Prometheus.

3. Real-time data visualization.
   - Description: Grafana interprets collected metrics and displays them as panels or graphs.
   - Responsible: Grafana.

4. Alert configuration and management.
   - Description: Definition of the conditions that will trigger alerts.
   - Responsible: Alertmanager.

5. Automated alert notification.
   - Description: Sending notifications through the configured channels.
   - Responsible: Alertmanager.

## User Types

- Administrator user (me): This user will have full access to the system, can create and modify dashboards, manage users, and edit Grafana’s global configuration. This role is reserved for the solution integrator.

- Editor user (technician): Can create, modify, and delete dashboards, but cannot change global system configuration or manage users. Intended for the company’s technical staff.

- Viewer user: Can only view dashboards predefined by the administrator or editor. Intended for different company departments depending on the intended use.

## Technical Feasibility Assessment

### Required Hardware

Since the service will be virtualized, requirements will largely depend on the number of machines to be monitored. In my case, since the test environment will include only a couple of machines, the following desktop hardware used for the deployment will be considered:

- **Processor**: Intel Core i7-12700K
- **Motherboard**: ASUS TUF GAMING Z690-PLUS WIFI D4
- **RAM**: Corsair Vengeance LPX DDR4 3200MHz 32GB (2x16GB) CL16
- **Graphics card**: Nvidia GeForce RTX 3060 12GB
- **Primary storage**: Kingston FURY Renegade 2TB SSD NVMe PCIe 4.0 M.2 Gen4
- **Secondary storage**: Kioxia Exceria G2 1TB SSD NVMe M.2 2280
- **Cooling**: Tempest Liquid Cooler 360
- **Power supply**: Corsair RMx RM1000x 1000W

### Software

For the development phase of the project, the following tools were selected based on their integration capabilities:

- Prometheus: metrics collection and storage system.
- Grafana: system that consumes metrics gathered by Prometheus and presents them visually.
- Node Exporter: exports system metrics so that Prometheus can store them.
- Alertmanager: alert configuration and notification component.
- VirtualBox: virtualization platform used to build the demonstration environment.
- Ubuntu Server: operating system used to deploy the systems.

## System Architecture
The system will consist of a main virtual machine where most services will be deployed: Prometheus, Grafana, and Alertmanager. In addition, one or more extra machines will act as monitored nodes by installing Node Exporter.

Prometheus will collect metrics exposed by Node Exporter on each machine, storing them so that Grafana can visualize them through charts and dashboards. In parallel, Alertmanager will manage alert notifications when any metric exceeds predefined thresholds.

## Risk and Stakeholder Analysis

| Risk                                                           | Impact | Probability | Mitigation Measures                                                                 |
|----------------------------------------------------------------|--------|-------------|-------------------------------------------------------------------------------------|
| Technical difficulty integrating the tools                      | High   | Medium      | Official documentation, technical forums, preliminary tests in controlled environments |
| VirtualBox failures or local hardware limitations               | Medium | Medium      | Create restore points and regular snapshots                                         |
| Limited SME adaptability to the solution                        | Low    | Medium      | Create a clear, simple guide with practical examples                               |
| Dependence on a single person for the entire project            | Medium | High        | Detailed process logging through technical documentation                            |
| Potential issues reproducing the project in real environments   | High   | Low         | Intensive preliminary testing, adapting the technical guide to different scenarios  |
| Insufficient time to complete the project within the expected deadline | High | Medium | Detailed planning with tasks and time tracking per phase                            |

## Activities

1. **Definition and planning:** Design of the monitoring system architecture, establishing core components, configuration, and technical requirements.

2. **Implementation:** Installation and configuration of Prometheus, Grafana, Node Exporter, and Alertmanager, ensuring correct integration between them.

3. **Testing and verification:** Perform multiple functional tests to validate operation and identify possible issues during implementation.

4. **Documentation:** Produce a complete technical guide with detailed installation steps to facilitate deployment in other companies.

5. **User guide and training:** Create explanatory material to understand dashboard usage and the monitoring and creation of alerts for autonomous operation.

6. **Commercialization and dissemination:** Design the final package along with promotion strategies.

## Future Improvements

The project may focus on solving a specific problem that could be expanded in the future with new functionalities, new interfaces, etc.

Planned improvements include:

- Deployment  
  Although the current implementation is local, the system is prepared to be deployed in cloud environments and more complex physical infrastructures.

- Automation and security  
  In the future, scripts could be implemented to react automatically depending on the alert type, as well as security mechanisms such as VPNs or two-factor authentication systems.

- Systems and platforms  
  The service could be expanded to monitor other systems such as databases, containers, Windows systems, specific applications, websites, and many more options, since each service can be monitored through different exporters. Additional notification channels could also be added.

- Functionalities  
  In the future, it may be possible to generate automatic reports to facilitate tracking of each alert and to view alert history.
