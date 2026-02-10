# Needs Analysis and Business Model

## Justification of the Identified Needs Covered by the System

### 1. Problem Statement

The main issue identified in this project is the lack of effective control over IT systems in many organizations, either due to limited resources or a lack of awareness regarding available solutions. Considering the constant technological evolution and the strong dependence many businesses currently have on IT infrastructure, they cannot afford system failures that may affect operations and generate significant financial losses.

### 2. Justification

Deploying a monitoring system will provide companies with a continuous supervision tool that offers real-time visibility into all monitored systems. This enables organizations to detect anomalies before they escalate into major problems. In the event that an issue does arise, they will have sufficient response time to resolve it as quickly as possible.

### 3. General Objective  

The primary objective of this project is to apply all the knowledge acquired throughout the training program in order to create an effective solution that meets expectations and allows companies beginning their digital transformation to operate within a secure and controlled environment.

### 4. Development

#### 4.1 Response to the Identified Need  

To address the needs described in this proposal, it is necessary to implement a system capable of monitoring different parts of the infrastructure using real-time, continuous data collection. The system should allow visualization and analysis of various types of information tailored to the specific requirements of each business.

Additionally, when certain anomalies or variations exceed predefined thresholds, the system is designed to notify stakeholders through multiple channels, minimizing the time between anomaly detection and alert notification. This improves organizational efficiency and ensures faster response times in both preventive and corrective scenarios.

#### 4.2 Means, Activities, and Resources

##### Technical Resources

- Virtual machines to simulate a real working environment.
- Ubuntu Server as the base operating system for services.
- Tools implemented: Prometheus, Grafana, Node Exporter, and Alertmanager.

##### Human Resources  

- Technical profile with knowledge in networking and systems administration.

##### Activities  

1. **Definition and Planning:** Design of the monitoring system architecture, defining core components, configuration parameters, and technical requirements.

2. **Implementation:** Installation and configuration of Prometheus, Grafana, Node Exporter, and Alertmanager, ensuring proper integration between components.

3. **Testing and Verification:** Execution of multiple functional tests to detect and resolve potential implementation errors.

4. **Documentation:** Creation of a complete technical guide detailing installation and configuration steps to facilitate deployment in other companies.

5. **User Guide and Training:** Development of explanatory material to support dashboard usage and alert configuration for autonomous operation.

6. **Commercialization and Promotion:** Design of the final solution package along with promotional strategies.

#### 4.3 Methodology  

The project follows a waterfall methodology, where each stage and corresponding steps are clearly defined.

This structured approach enables clear task segmentation and supports the development of comprehensive documentation for each phase, designed for later distribution as a technical guide.

Furthermore, it ensures system stability, as each phase depends on the successful completion of the previous one, promoting a controlled and reliable implementation process.

#### 4.4 Personnel  

All previously mentioned activities are planned to be carried out by a single individual with technical expertise. However, the solution is designed with future scalability in mind, allowing additional functionalities and broader scope expansion. Initially, it is conceived to fulfill limited functions and be entirely developed by one person.

#### 4.5 Timeline

Considering the planned activities (planning, implementation, documentation, etc.) and the approximate two-month timeframe assigned—taking into account that only one person is responsible for execution—it is estimated that the project could be completed in a shorter period while still meeting expectations.

This estimation includes both technical implementation and documentation writing, as well as testing and review processes. If necessary, the timeline could be slightly extended to incorporate improvements or specific adaptations based on requirements.

## Commercialization Opportunities (Feasibility, Competitors…)

### 1. Feasibility  

#### 1.1 Technical Feasibility

A significant part of the project was designed with technical feasibility in mind, selecting open-source tools that significantly reduce costs and can be deployed by a single individual, at least at the system’s initial scale.

The use of mature and well-documented technologies such as Prometheus, Grafana, Node Exporter, and Alertmanager greatly simplifies implementation. Additionally, using VirtualBox as a local development environment allows simulation of a virtual scenario without requiring physical infrastructure, making the setup easily reproducible.

This approach ensures autonomy throughout the project, eliminates limitations related to external resource availability, and enables controlled and direct testing and configuration processes.

#### 1.2 Economic Feasibility  

From an economic perspective, the project is initially conceived at a small scale, requiring minimal upfront investment since it relies on open-source tools and a virtualized environment, eliminating licensing and physical infrastructure costs.

If expanded beyond a technical prototype into a commercial product, additional investment might be required to establish a more robust infrastructure and cover a broader scope. In such cases, access to public funding programs supporting digitalization initiatives—offered by governmental institutions—could be considered to offset part of the initial costs.

### 2. Competition  

Several established tools already provide system monitoring solutions, such as Zabbix, Nagios, or Datadog. While effective in certain contexts, they present limitations that this project aims to address:

- Many operate under paid service models or restrict certain features to premium versions.
- They require more powerful infrastructure to ensure stable service, which may be unfeasible for small businesses.
- Their complexity and lack of intuitiveness make autonomous usage difficult for users without specialized training.

Advanced alert management is a core element of this proposal. Unlike other tools that centralize logic within a single module, this system separates detection from notification through Alertmanager integration.

This enables:

- Definition of multiple alert severity levels.
- Custom behavior based on schedules or criticality.
- Simultaneous configuration of multiple notification channels.

This modular architecture provides flexibility and control that many traditional solutions—especially in their free versions—do not offer.

## Commercialization Strategy

### 1. Promotion  

The most effective promotion strategy is direct outreach to small and medium-sized enterprises, particularly those lacking monitoring systems or awareness of their importance.

Target organizations can be identified through their technological usage while lacking structured infrastructure control.

These companies will be offered the solution individually, accompanied by a technical demonstration showcasing system functionality and highlighting key advantages, especially in early problem detection and improved response capacity.

This personalized strategy allows closer engagement with the target audience without relying on large-scale advertising campaigns. It is economically viable and feasible for execution by a single individual, aligning with the project’s initial scope.

### 2. Business Model  

The selected business model combines two main approaches:

- **One-time payment model** for delivering a detailed technical guide that includes all documentation required to install, configure, and operate the monitoring system. This enables companies to deploy the solution independently within their environment.

- **Optional monthly subscription model** for companies that require additional technical support, customized adaptations, remote supervision, or continuous system improvements.

This hybrid model is tailored to small businesses that may not have the resources to commit to complex or long-term service contracts but may still seek a reliable and cost-effective solution.

The technical guide provides independence, while the optional subscription opens the door to professional support without long-term obligations.

This approach also allows future scalability, enabling additional subscription tiers or customized on-demand services as the project grows.
