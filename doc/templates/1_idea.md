# Monitoring System
### Project Type

This project aims to document how to deploy a monitoring system using the open-source tools Prometheus and Grafana, incorporating a practical component at the end to demonstrate the real-world operation of the proposed solution.

### Foundations

The goal of this initiative is to create a monitoring system based on Prometheus and Grafana, with the purpose of applying the knowledge acquired throughout this course. This solution may represent an attractive option for companies that lack the necessary resources to monitor and analyze their IT systems in real time, which can otherwise lead to vulnerabilities, financial losses, and reduced productivity if issues are not detected early.

### Problem Statement

In a context where many companies are undergoing digital transformation, this project seeks to provide a flexible, intuitive, and customizable solution that encourages organizations to recognize the importance of monitoring their systems and preventing incidents that could otherwise be avoided with minimal proactive control and management.

### Context

This proposal targets small and medium-sized enterprises that, despite progressing in their digital transformation and investing in software and hardware (such as servers, workstations, or virtual machines), still lack or are unaware of the tools required to properly monitor their infrastructure. As a result, when incidents occur, they may not understand their origin or be adequately prepared to respond effectively.

### Needs

The objective is for companies to gain visibility into their systems and detect vulnerabilities or anomalies before they directly impact business operations, thereby improving security and response times within their working environment.

This creates a market opportunity for a wide range of businesses and sectors that wish to benefit from the advantages of such a monitoring solution.

For commercialization purposes, the project proposes delivering a detailed technical guide including all necessary steps to configure the tools used, along with practical examples of alerts that each company can adapt according to its priorities and operational requirements.

Additionally, the possibility of offering initial support or customized adaptation services is considered as a complementary service to the base documentation.

### Alternative Tools

Currently, there are many applications designed to address system monitoring needs. The most prominent include Zabbix, Nagios, Pandora FMS, Centreon, and Datadog (which offers a cloud-based service).

These tools, like Prometheus and Grafana, allow real-time monitoring and analysis of metrics. However, they also present certain limitations that motivated the selection of a clearer and more streamlined solution as proposed in this project.

In general terms, while some of these tools are highly powerful, many of them:

- Operate under paid service models, such as Datadog.
- Require more robust infrastructure.
- Present a steeper learning curve.
- Offer less scalability flexibility.
- Rely on legacy or more complex architectures.

The proposed solution aims to provide companies—particularly those taking their first steps in digital transformation—with a system that is intuitive, practical, and accessible, without compromising quality or adaptability.

### Objective

In line with the previous section, and with the goal of facilitating the deployment of a monitoring system for companies that currently lack one, this project seeks to design and document as precisely as possible a solution capable of visualizing real-time data and detecting anomalies before they evolve into critical issues.

To ensure effective response times, the system incorporates automated notifications through Alertmanager, allowing customized alerts to be created and delivered simultaneously through multiple channels such as email, Telegram, or SMS, thereby enabling immediate reaction to potential incidents.

### Technological Resources

- Prometheus – Metrics collection and storage
- Grafana – Data visualization and dashboard creation
- Node Exporter – System metrics export
- Alertmanager – Alert management and notification delivery
- Ubuntu Server – Base operating system
- VirtualBox – Virtualization environment
