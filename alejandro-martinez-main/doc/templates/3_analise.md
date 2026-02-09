# REQUERIMENTOS DO SISTEMA
Este documento describe os requirimentos para o proxecto "Sistema de monitorización con Prometheus e Grafana" especificando que funcionalidade ofrecerá e de que xeito.

## Descrición Xeral

Este proxecto ten como obxectivo implementar unha solución de monitorización flexible e práctica, baseada nas ferramentas Prometheus, Grafana, Node Exporter e Alertmanager, pensada para pequenas e medianas empresas que recentemente están comezando coa súa dixitalización e carecen dos medios para levar un control sobre as súas infraestruturas.  
O obxectivo principal é crear unha guía técnica que sexa reproducible e que lles permita controlar o estado en tempo real, permitindo ver anomalías cando se produzan e antes de que afecten a outros aspectos como a produtividade ou os equipos.  
A estrutura, polo tanto, divídese en dúas partes: unha implantación práctica sobre máquinas virtuais para ver o seu funcionamento e outra parte na que se crea unha documentación técnica orientada á súa comercialización. 


## Funcionalidades
A continuación detállanse as funcionalidades principais que ofrecerá o sistema de monitorización:

1. Recolección de métricas.
  - Descrición: Obtención de datos clave como o uso da CPU, memoria, disco e rede.
  - Responsable: Node Exporter.

2. Almacenamento e procesamento de métricas.
  - Descrición: Prometheus recolle as métricas dos exporters e gárdaas en tempo real para despois procesalas.
  - Responsable: Prometheus.

3. Visualización dos datos en tempo real.
  - Descrición: Grafana interpreta as métricas recollidas e mostraas en forma de paneis ou gráficas. 
  - Responsable: Grafana.

4. Configuración e xestión de alertas.
  - Descrición: Definición das condicións que van a desencadear as alertas.
  - Responsable: Alertmanager.

5. Notificación automatizada de alertas.
  - Descrición: Envío de avisos a través das canles establecidas.
  - Responsable: Alertmanager.
 
## Tipos de usuarios


- Usuario administrador (eu): Este usuario terá acceso completo ao sistema, pode crear e modificar dashboards, xestionar usuarios editar a configuración global de Grafana. Este rol vai estar reservado ao integrador da solución.  


- Usuario editor (técnico): Pode crear, modificar e eliminar dashboards, pero non pode cambiar a configuración global do sistema nin xestionar usuarios. Está pensado para ser usado polo persoal técnico da empresa.  

- Usuario visualizador: Só pode consultar os dashboards predefinidos polo administrador ou o editor. Este perfil está pensado para ser usado polos diferentes departamentos da empresa segundo o uso que se lle queira dar.


## Avaliación da viabilidade técnica do proxecto

### Hardware requerido

Como o servizo vai a ser virtualizado, dependerá en gran medida do número de máquinas a monitorizar, no meu caso como se vai a realizar unha proba con un par de máquinas só se terá en conta o equipo de sobremesa co que se vai a realizar dita integración:

- **Procesador**: Intel Core i7-12700K

- **Placa base**: ASUS TUF GAMING Z690-PLUS WIFI D4

- **Memoria RAM**: Corsair Vengeance LPX DDR4 3200MHz 32GB (2x16GB) CL16

- **Tarxeta gráfica**: Nvidia GeForce RTX 3060 12GB

- **Almacenamento principal**: Kingston FURY Renegade 2TB SSD NVMe PCIe 4.0 M.2 Gen4

- **Almacenamento secundario**: Kioxia Exceria G2 1TB SSD NVMe M.2 2280

- **Refrixeración**: Tempest Liquid Cooler 360

- **Fonte de alimentación**: Corsair RMx RM1000x 1000W

### Software

Para a parte de desenvolvemento do proxecto seleccionáronse as seguintes ferramentas tendo en conta a integración entre elas:

- Prometheus: como sistema recolector e almacenaxe de métricas.

- Grafana: sistema que recolle as métricas recompiladas por Prometheus e dalles formato visual.

- Node Exporter: exportación de métricas do sistema para que Prometheus as almacene.

- Alertmanager: sistema de configuración e creación de alertas.

- VirtualBox: sistema de virtualización no cal se vai a levar a cabo a demostración.

- Ubuntu Server: SO para a montaxe dos sistemas.

## Arquitectura do sistema
O sistema estará formado por unha máquina virtual principal onde se implementarán a maioría de servizos: Prometheus, Grafana e Alertmanager. A isto hai que sumarlle unha ou varias máquinas adicionais que van a actuar como nodos monitorizados mediante a instalación de Node Exporter.

Prometheus vaise a encargar de recolectar as métricas que Node Exporter expón en cada máquina, almacenandoas posteriormente para que Grafana as mostre para visualizar en forma de gráficos e dashboards. En paralelo, Alertmanager está xestionando o envío de alertas se algunha supera os valores definidos.

## Análise de riscos e interesados

| Risco                                                         | Impacto | Probabilidade | Medidas correctoras                                                                 |
|---------------------------------------------------------------|---------|----------------|--------------------------------------------------------------------------------------|
| Dificultade técnica na integración das ferramentas            | Alto    | Media          | Documentación oficial, foros técnicos, probas previas en contornos controlados       |
| Fallos no sistema VirtualBox ou limitacións do hardware local | Medio   | Media          | Crear puntos de restauración e snapshots regulares                                   |
| Escasa capacidade de adaptación das PEMEs á solución          | Baixo   | Media          | Elaboración dunha guía clara, sinxela e con exemplos prácticos                      |
| Dependencia dunha única persoa para todo o proxecto           | Medio   | Alta           | Rexistro detallado de todo o proceso mediante documentación técnica                 |
| Posibles problemas na reprodución do proxecto en contornos reais | Alto | Baixa          | Probas previas intensivas, adaptación da guía técnica a diferentes escenarios       |
| Falta de tempo para completar o proxecto dentro do prazo previsto | Alto | Media        | Planificación detallada con tarefas e control do tempo dedicado por fase            |


## Actividades

1. **Definición e planificación:** Deseño da arquitectura do sistema de monitorización, establecendo os compoñentes principais así como a súa configuración e os requisitos técnicos.

2. **Implantación:** Instalación e configuración de Prometheus, Grafana, Node Exporter e Alertmanager asegurando que se integren correctamente entre eles.

3. **Probas e verificación:** Realizar varias probas de funcionamento para comprobar e descartar posibles erros no paso de implantación.

4. **Documentación:** Realizarase unha guía técnica completa cos pasos detallados da instalación do sistema e facilitar a implantación noutras empresas.

5. **Guía de uso e formación:** Creación de material explicativo para entender o uso dos dashboards e o seguimento e creación de alertas para un uso autónomo da solución.

6. **Comercialización e difusión:** Deseño do paquete final xunto con estratexias de promoción.


## Melloras futuras

É posible que o proxecto se centre en resolver un problema concreto que se poderá ampliar no futuro con novas funcionalidades, novas interfaces, etc.

Entre as melloras previstas contemplase:

- Despregamento  
Aínda que a implementación actual é local, o sistema está preparado para ser despregado tamén en contornas cloud e infraestruturas físicas máis complexas.


- Automatización e seguridade
No futuro poderían implementarse scripts que reaccionen automáticamente segundo o tipo de alerta, así como mecanismos de seguridade como VPN ou sistemas de autenticación en dous pasos.

- Sistemas e plataformas  
Contémplase poder ampliar o servizo a outros sistemas operativos como bases de datos, contedores, sistemas windows, aplicacións especificas, páxinas web e moitas máis opcións debido a que por cada servizo se emprega un exporter diferente, ademais de empregar novas canles para a notificación de alertas.

- Funcionalidades  
Tamén se contempla nun futuro a posibilidade de xerar informes automáticos para facilitar o seguimento de cada unha das alertas e poder ver o historial das mesmas.  
