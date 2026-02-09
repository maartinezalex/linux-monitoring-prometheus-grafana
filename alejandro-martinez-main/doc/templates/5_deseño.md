# FASE DE DESEÑO

## Arquitectura

Modelo da arquitectura do teu sistema
Compoñentes que participan no sistema completo.

O sistema de monitorización está estruturado cun enfoque distribuído no que os servizos centralizados nunha máquina virtual, mentres que os sistemas a monitorizar funciona como nodos remotos que expoñen as súas métricas.  

A máquina virtual principal emprega un sistema operativo Ubuntu Server escollido pola súa lixeireza e compatibilidade coas ferramentas utilizadas. Os nodos monitorizados pola súa banda, poden empregar a versión de escritorio, como Ubuntu Desktop, que permite visualizar métricas máis variadas ao contar con procesos en segundo plano.  

Como a máquina virtual principal implementaronse os seguintes compoñentes:  

- Prometheus, encargado da recolección e almacenamento de métricas.

- Grafana, para a visualización e análise gráfica dos datos.

- Alertmanager, que xestiona o envío de alertas cando se detectan valores críticos.

- Os ficheiros de configuración necesarios para integrar todos os servizos.

A arquitectura da rede empregada vai a fácilitar o acceso vía navegador web aos principais servizos. No contexto dunha implantación local mediante VirtualBox, non se vai a realizar a apertura de portos específicos. Con todo, nunha futura implementación en contornos cloud, sería necesario garantir o acceso a estos portos, que tamén se utilizan en local:

- Porto 22: acceso SSH á máquina virtual para tarefas de administración.

- Porto 3000: acceso á interface web de Grafana.

- Porto 9090: acceso á interface de Prometheus.

- Porto 9093: acceso ao panel de Alertmanager.

- Porto 9100: exposición de métricas do Node Exporter (este porto só debe ser accesible pola IP da VM)

Node Exporter por outro lado instalase en cada un dos nodos monitorizados para expoñer as súas métricas e que Prometheus as recolla e interprete.
O acceso será por vía navegador web da rede local ingresando a ip da máquina principal e o porto correspondente do servizo.

## Casos de uso 

Usuarios, roles ou tipo de actores que participan no sistema

- Usuario administrador (eu): Este usuario terá acceso completo ao sistema, pode crear e modificar dashboards, xestionar usuarios editar a configuración global de Grafana. Este rol vai estar reservado ao integrador da solución.  

- Usuario editor (técnico): Pode crear, modificar e eliminar dashboards, pero non pode cambiar a configuración global do sistema nin xestionar usuarios. Está pensado para ser usado polo persoal técnico da empresa.  

- Usuario visualizador: Só pode consultar os dashboards predefinidos polo administrador ou o editor. Este perfil está pensado para ser usado polos diferentes departamentos da empresa según o uso que se lle queira dar.


## Interfaces de Usuario

Se tes algún tipo de interfaz de usuario, sexa de tipo GUI ou tipo CLI

O sistema conta con interfaces gráficas accesible mediante navegador web, empregadas para a configuración, visualización e supervisión dos servizo.  

**Interfaz de Prometheus:**

<img src="doc/img/interfaz_prometheus.png">  

**Login Grafana:**

<img src="doc/img/login_grafana.png">

**Interfaz de Grafana:** 

<img src="doc/img/interfaz_grafana.png">

**Interfaz de Alertmanager:**

<img src="doc/img/alert_6.png">

## Diagrama de despregamento
<img src="doc/img/DIAGRAMA_DE_FUNCIONAMENTO.png">

## Ficheiros de Configuración 

- [**Prometheus.yml**](/src/prometheus.yml)

- [**Grafana.ini**](/src/grafana.ini)

- [**Alertmanager.yml**](/src/alertmanager.yml)

- [**Alert_rules.yml**](/src/alert_rules.yml)


