# Monitoring System Project

![Project Cover](doc/img/portada.png)

## Monitoring System

This project consists of deploying a monitoring system designed for small and medium-sized businesses that are taking their first steps in digital transformation and do not yet have tools to control the status of their infrastructure.

The goal is to use open-source software such as Prometheus and Grafana to collect and visualize real-time metrics (CPU, memory, disk). All metrics can be accessed through a web browser in graphical format, and alerts can be configured to notify administrators when specific thresholds are exceeded.

In addition to the practical implementation, this project includes a complete technical guide covering the full installation and configuration process. It is designed so that a person with basic technical knowledge can replicate the system with minimal effort. The entire setup runs on virtual machines, avoiding the need for additional hardware.

The objective is to provide a useful, simple, and scalable solution that helps detect technical issues before they impact business operations.

---

## Installation / Deployment

The installation of this system consists of three main stages:

1. Preparing the virtual environment (VirtualBox).
2. Creating the virtual machines.
3. Installing and configuring the tools on:
   - Machine 1 (Monitoring Server)
   - Machine 2 (Monitored Target)

After installation and configuration, testing can begin. Alerts and dashboards can be created and customized to adapt the system to specific needs.

For a detailed step-by-step installation guide, see the [Deployment section](doc/templates/6_implantacion.md) included in this repository.

---

## Usage

Once configured, services can be accessed through the IP address of the server machine. Each service uses a specific port:

- Grafana: port 3000  
- Alertmanager: port 9093  
- Prometheus: port 9090  

Grafana is the primary interface used daily. From there, dashboards can be visualized, filters applied, and new panels created.

If a predefined threshold is exceeded (for example, high CPU usage), alerts are sent to the configured communication channels (email, Telegram, etc.), depending on severity and configuration.

Most alert rules are defined in:

- [prometheus.yml](src/prometheus.yml)  
- [alertmanager.yml](src/alertmanager.yml)

Alertmanager’s web interface (port 9093) can also be used to visualize alert states.

---

## About the Author

My name is Alejandro Martínez and I am currently studying ASIR (Network Systems Administration). Since childhood, I have been interested in computers and technology, which motivated me to pursue a career in this field.

I am particularly interested in networking and cybersecurity, although I remain open to exploring new areas and continuously improving my technical skills.

With this project, I aimed to deepen my understanding of system monitoring, as I consider it a key component in maintaining infrastructure security and reliability. It also allowed me to apply the knowledge acquired throughout my studies and understand how system resources can be optimized and controlled.

You can contact me via email or through my LinkedIn profile.

---

## License

This project is licensed under the [GNU Free Documentation License Version 1.3](https://gitlab.com/iesleliadoura/asir2/alejandro-martinez/-/blob/main/doc/LICENSE.txt).

For more details, please refer to the full license text.

---

# Sistema de Monitorización (Versión en Español)

![Portada del Proyecto](doc/img/portada.png)

## Sistema de monitorización

El proyecto consiste en montar un sistema de monitorización pensado para pequeñas y medianas empresas que están dando sus primeros pasos en la digitalización y no disponen de herramientas para controlar el estado de sus equipos.

La idea es utilizar software libre, como Prometheus y Grafana, para recoger y visualizar métricas en tiempo real (CPU, memoria, disco). Todo puede consultarse desde el navegador en forma de gráficos y es posible configurar alertas para notificar si algún valor supera los límites establecidos.

Además de la parte práctica, se incluye una guía técnica con el proceso completo de instalación y configuración, pensada para que una persona con conocimientos básicos pueda replicarlo con poco esfuerzo. Todo funciona sobre máquinas virtuales, evitando la necesidad de hardware adicional.

El objetivo es ofrecer una solución útil, sencilla y que ayude a detectar problemas técnicos antes de que afecten a la actividad de la empresa.

---

## Instalación / Puesta en marcha

La instalación del sistema consta de tres partes:

1. Preparación del entorno virtual (VirtualBox).
2. Creación de las máquinas virtuales.
3. Instalación y configuración de herramientas en:
   - Máquina 1 (Servidor de monitorización)
   - Máquina 2 (Sistema monitorizado)

Una vez instalado y configurado todo, se pueden realizar pruebas y crear alertas o dashboards personalizados.

Para ver el proceso detallado paso a paso, consulte la sección de [Implantación](doc/templates/6_implantacion.md) incluida en este proyecto.

---

## Uso

Una vez configurado, se accede a los servicios a través de la dirección IP del servidor. Cada servicio utiliza un puerto específico:

- Grafana: puerto 3000  
- Alertmanager: puerto 9093  
- Prometheus: puerto 9090  

La interfaz principal es Grafana, donde se pueden visualizar dashboards, aplicar filtros y crear nuevos paneles.

Si se supera un umbral definido por el administrador (por ejemplo, alto consumo de CPU), la alerta se envía a los canales configurados (correo, Telegram, etc.).

La configuración principal se encuentra en:

- [prometheus.yml](src/prometheus.yml)  
- [alertmanager.yml](src/alertmanager.yml)

---

## Índice de la documentación del proyecto

1. Anteproyecto  
    * 1.1. [Idea](doc/templates/1_idea.md)  
    * 1.2. [Necesidades](doc/templates/2_necesidades.md)  
2. [Análisis](doc/templates/3_analise.md)  
3. [Planificación](doc/templates/4_planificacion.md)  
4. [Diseño](doc/templates/5_deseño.md)  
5. [Implantación](doc/templates/6_implantacion.md)

---

## Referencias

- Oracle. (2024). *Downloads – Oracle VirtualBox*.  
  https://www.virtualbox.org/wiki/Downloads  

- Bujarra. *Documentación sobre recolección de métricas*.  
  https://www.bujarra.com  

- Grafana Labs. *Grafana*.  
  https://grafana.com  

- Prometheus Authors. *Prometheus: Monitoring system & time series database*.  
  https://prometheus.io  
