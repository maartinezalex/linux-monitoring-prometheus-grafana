# FASE DE IMPLANTACIÓN

## Posta en marcha

### Instalación de VirtualBox  

**a) Descarga e instalación**  

Accédese a páxina oficial de [VirtualBox](https://www.virtualbox.org/wiki/Downloads/) e descárgase a versión correspondente ao host, en este caso usouse para Windows a versión 7.1.8 xunto co pack de extensións da mesma versión.  

<img src="doc/img/descargas_vbox.png" />

Unha vez descargado o instalador, procédese ca instalación por defecto.  

---

### Máquina virtual 1: Servidor de monitorización

Nesta máquina instalouse o sistema Prometheus, Grafana e Alertmanager.

- **Nome**: VM-Monitorización
- **Sistema operativo convidado**: Ubuntu Server 24.04 LTS (64 bits)
- **Memoria RAM**: 4 GB
- **Procesadores**: 2 vCPU
- **Disco duro**: 35 GB, formato VDI, almacenamento dinámico
- **Adaptador de rede**: Bridge (Adaptador Ponte)
- **Portos expostos**:  
  - 3000 (Grafana)  
  - 9090 (Prometheus)  
  - 9093 (Alertmanager)

> Esta máquina contén o núcleo do sistema de monitorización, accedéndose a Prometheus e Grafana dende o navegador do host ou dunha rede local.

<img src="doc/img/vm_1_conf.png" />

---

### Máquina virtual 2: Máquina monitorizada

Nesta máquina instalouse unicamente **Node Exporter**.

- **Nome**: VM-Monitorizada
- **Sistema operativo convidado**: Ubuntu Desktop 24.04 LTS (64 bits)
- **Memoria RAM**: 1 GB
- **Procesadores**: 1 vCPU
- **Disco duro**: 15 GB, formato VDI, almacenamento dinámico
- **Adaptador de rede**: Bridge (Adaptador Ponte)

> O Node Exporter foi configurado para escoitar no porto 9100 e ser detectado polo Prometheus da VM principal.

<img src="doc/img/vm_2_conf.png" />

---

### Instalación de Prometheus  

**a) Descarga do binario**  

Prometheus é distribuido como binario compilado. [Descárgase](https://prometheus.io/download/) a versión oficial 2.50 desde o repositorio de GitHub (ainda que a páxina sexa a oficial de Prometheus os archivos están gardados en repositorios de GitHub), descomprímese e móvese ao directorio `/opt/prometheus` para ter os ficheiros da aplicación centralizados.  

<img src="doc/img/descarga_binarios_p.png" />

**b) Creación do usuario e directorios** 

Crear usuario sen acceso a shell nin a home evita riscos de seguridade:  
Prometheus só executa procesos propios, sen privilexios de login. Os directorios `/etc/prometheus` (configuración) e `/var/lib/prometheus` (datos) créanse para separar configuración e datos persistentes, asignado a propiedade ao usuario Prometheus.

<img src="doc/img/usuarios_directorios_p.png" />

**c) Copia dos executables**  

Colocar os executables en `/usr/local/bin` permite que se executen fácilmente desde calquera ruta do sistema. A propiedade limítase ao usuario Prometheus por seguridade.  

<img src="doc/img/copia_executables_p.png" />

**d) Copia de consolas e configuración**  

Estas carpetas conteñen plantillas e recursos de consola para o panel web de Prometheus. Trasládanse a `/etc/prometheus` para centralizar.  

<img src="doc/img/copia_consolas_conf.png" />

**e)Copia do ficheiro de configuración principal**  

O ficheiro prometheus.yml define os jobs a monitorizar (os equipos/targets), intervalos e alertas.  
Colocándoo en `/etc/prometheus` facilítase a súa xestión centralizada e permítese realizar backups facilmente.  

<img src="doc/img/copia_fich_conf_p.png" />

**f) Configuración do ficheiro prometheus.yml**  

Neste ficheiro defínese qué servizos e instancias van ser monitorizadas. No exemplo incúese o propio Prometheus.  

<img src="doc/img/prometheus_yml.png" />

**g) Creación do servizo systemd**  

Crear un servizo systemd permite xestionar Prometheus como un servizo do sistema:  
arranque automática, reinicio trás caídas, control de logs, etc.  
O bloque "Service" define o usuario, execución do binario e rutas de configuración.  

<img src="doc/img/prometheus_service.png" />


**h) Activar o servizo**  

`daemon-reload` actualiza systemd tras engadir ou modificar un servizo.  
`enable --now` activa e inicia o servizo para que arranque ao iniciar a máquina e comece a funcionar de inmediato.  

***Estructura:***  

`/opt/prometheus` -> Binarios orixinais (carpeta base)  

`/usr/local/bin` -> Executables para poder chamalos desde calquera punto do sistema.  

`/etc/prometheus` -> Configuracións varias  

`/var/lib/prometheus` -> Base de datos de Prometheus  

---

### Instalación Node Exporter  

**a) Descarga do binario**  

Ao igual que con Prometheus descárgase a versión oficial 1.70 desde o repositorio de GitHub, descomprímese para poder acceder ao executable.

<img src="doc/img/node_ex_3.png" />

**b)Instalación do binario**  

O binario node_exporter colócase en `/usr/local/bin` para que poida executarse desde calquera parte do sistema.

<img src="doc/img/node_ex_4.png" />


**c)Creción do usuario** 

Crear usuario sen acceso a shell nin a home para mellorar a seguridade, e dicir, se ocorre algún problema só afectará a ese usuario e non ao sistema por completo.  

<img src="doc/img/node_ex_1.png" />


**d) Creación do servizo systemd** 

Configurase systemd para que se inicie ao arrancar o sistema e se poidas xestionar (arrancar/parar/reiniciar) coas ferramentas estándar de Linux así como que se execute co usuario node_exporter por razóns de seguridade.  

<img src="doc/img/node_ex_5.png" />


---

### Instalación de Grafana  

**a) Configuración de reposistorio**  

Instálanse utilidades básicas para manexar repositorios seguros. Engáse a chave GPG e o repositorio oficial de [Grafana](https://grafana.com/docs/grafana/latest/setup-grafana/installation/debian/).  

**b) Instalación e activación**  

Actualízanse os repositorios (apt update), instálase o software (apt install). Arráncase o servizo (enable --now) e permite que se execute ao iniciar o sistema.  

---

### Instalación de Alertmanager  

**a) Descarga e instalación**  

Proceso similar con Prometheus para garantir seguridade, separar permisos e manter estrutura.  

<img src="doc/img/alert_1.png" />  

<img src="doc/img/alert_2.png" />

<img src="doc/img/alert_3.png" />

**b) Creación systemd**  

Para arranque automático, xestions do sistema (arrancar/parar/reiniciar).  

<img src="doc/img/alert_4.png" />

**c)Activación**  

Para execución continua.  

<img src="doc/img/alert_5.png" />  

<img src="doc/img/alert_6.png" />

**d) Configuración en Prometheus**  

Permite comunicación ente Prometheus e Alertmanager para xestionar e enviar as alertas.  

---

### Configuración de Node Exporter  

**a) Engadir target**  

No ficheiro `prometheus.yml` ao final do mesmo engades o target ca IP da que se van a extraer as métricas.  

<img src="doc/img/conf_node_1.png" />  

**b) Comprobar os targets**  

Unha vez engadidos no ficheiro accedese a `prometheus/targets` desde o navegador web para verificar que está recolectando correctamente  

<img src="doc/img/conf_node_2.png" />

---

### Configuración de Grafana  

**a) Engadir data source**  

Unha vez instadas todas as ferramentas na interfaz de Grafana engádese a fonte da cal se van a enseñar as métricas.  

<img src="doc/img/conf_graf_1.png" />  

**b) Engadir Prometheus como fonte**  

<img src="doc/img/conf_graf_2.png" />  

**c) Engadir IP dos targets**  

En este paso engádese a dirección IP dos targets que se queren visualizar que neste caso é VM-Monitorizada ca IP correspondente.  

<img src="doc/img/conf_graf_3.png" />

---

### Dashboards

Unha vez que Node Exporter está recolectando as métricas do target e Grafana ten a Prometheus como fonte e ao target asignado pódese crear un dashboard para poder visualizar toda esa información.  

**a) Novo dashboard** 

<img src="doc/img/dash_1.png" />

**b) Importar dashboard**  

Nesta pestaña dache opcións para importar paneis especificos e dashboards así como crealos desde 0 personalizados. 

<img src="doc/img/dash_2.png" />  

**c) Engadir ID**  

Hai infinidade de dashboards para diferentes exporters que se adaptan as necesidades de cada proxecto e todos se atopan na páxina oficial de [Grafana](https://grafana.com/grafana/dashboards/).  
Unha vez atopes o dashboard que necesitas colles o ID e engadelo no apartado de importar dashboard.

**d) Vista previa**  

<img src="doc/img/dash_4.png" />

---

### Configuración de Alertmanager

**a) Engadir Alertmanager**

Unha vez que Alertmanager está funcionando correctamente e comprobado con `systemctl status alertmanager` pódese engadir no ficherio de configuración `prometheus.yml` como localhost xa que está na mesma máquina que o servizo e no porto 9093 que corresponde a alertmanager.  

<img src="doc/img/alert_conf_1.png" />

**b) Reiniciar o servizo**  

Cando se executan cambios no ficheiro de configuración débese reiniciar para que se garden os cambios.  

<img src="doc/img/alert_conf_2.png" />

**c) Comprobación**  

A través do navegador web accedese a `/status` e hai que comprobar que alertmanager aparece como endpoint correctamente para confirmar que se aplicou ben a configuración.

<img src="doc/img/alert_conf_3.png" />

---

### Crear alertas  

> Nota: Para recibir correos en gmail debe de estar activada a verificación en dous pasos do correo que recibe  

**a) Crear contrasinal de aplicación**  

Para notificar as alertas na conta de correo é necesario crear unha contrasinal de aplicación para non usar a propia. Para iso hai que iniciar sesión na [páxina de contrasinais de aplicación de Google](https://myaccount.google.com/apppasswords).

<img src="doc/img/alerta1.png" />

<img src="doc/img/alerta2.png" />

**b) Configurar o ficheiro de alertmanager**

No ficheiro `alertmanager.yml` engádese o servidor smtp de gmail así como o correo que se emprega e a clave que se xerou anteriormente. Engádese tamén `send_resolved: true` xa que desta maneira envía outro correo cando esta se resolva axudando e gran medida ao seguimento da mesma.

<img src="doc/img/alerta4.png" />

**c) Crear alerta**  

A continuación crease un ficheiro donde se van a establecer as reglas polas cales van a saltar as alarmas, nesta caso por uso de CPU. De así querelo podese empregar o valor de vector(1) para que a alerta se envía automáticamente sen ningún criterio para comprobar que as canles funcionan correctamente.

<img src="doc/img/alerta3.png" />

**d) Engadilo a Prometheus**  

<img src="doc/img/alerta5.png" />

**e) Comprobación**

Se as reglas se añadiron correctamente podense comprobar en prometheus `/rules`.

<img src="doc/img/alerta6.png" />

---

### Probas

a) Alerta con vector(1)

Antes de probar a notificar alertas con valores de cpu está ben usar a expresión vector(1) para comprobar que os correos chegan e que ao probar cos valores da cpu asegurse funciones tamén.

<img src="doc/img/proba1.png" />

Ao empregar esta expresión como se dixo anteriormente é como se a regla se cumplira automaticamente, polo tanto comprobase en prometheus `/alert` se ten algunha entrada asi como no correo e na interfaz de alertmanager.

<img src="doc/img/proba2.png" />

<img src="doc/img/proba3.png" />

Tanto Alertmanager como Prometheus notificaron a alerta e chegou ao correo electrónico de destino polo tanto con esta base pode comezar a facerse probar con valores reais da CPU.

<img src="doc/img/proba4.png" />

b) Alert con CPU

Para verificar agora a alerta con uso de CPU o ideal é poñer uns valores baixos para comprobar que o Node Exporter está pasando correctamente os datos e segundo o tempo medio de duración da alerta sexa detectado e notificado.

<img src="doc/img/cpu1.png" />

Como o valor que se puxo de cpu foi moi baixo salta case instantaneamente e volve a ser notificado por Prometheus Alertmanager e chega ao correo.

<img src="doc/img/cpu2.png" />

<img src="doc/img/cpu3.png" />

Ao pouco rato de volver a normalidade os valores da cpu mandase outro correo decindo que a alerta foi resolta.

<img src="doc/img/cpu4.png" />

---

## Manual técnico:

### Información relativa á instalación:

>A continuación detallanse os elementos empregados no desenvolvemento do proxecto.

#### Elementos de hardware

- **Procesador**: Intel Core i7-12700K

- **Placa base**: ASUS TUF GAMING Z690-PLUS WIFI D4

- **Memoria RAM**: Corsair Vengeance LPX DDR4 3200MHz 32GB (2x16GB) CL16

- **Tarxeta gráfica**: Nvidia GeForce RTX 3060 12GB

- **Almacenamento principal**: Kingston FURY Renegade 2TB SSD NVMe PCIe 4.0 M.2 Gen4

- **Almacenamento secundario**: Kioxia Exceria G2 1TB SSD NVMe M.2 2280

- **Refrixeración**: Tempest Liquid Cooler 360

- **Fonte de alimentación**: Corsair RMx RM1000x 1000W

---

#### Elementos de software

- **Sistema operativo**:
  - Ubuntu Server 24.04 LTS (versión empregada).

- **Software de virtualización**:
  - **Oracle VM VirtualBox 7.1.8** 

- **Software principal**:
  - **Prometheus v2.50** – Recolle e almacena métricas de sistema e servizos.

  - **Node Exporter v1.7.0** – Exportador de métricas hardware e do sistema operativo.

  - **Grafana v10.4.2** – Plataforma de visualización de datos.

  - **Alertmanager v0.27.0** – Servizo de xestión e envío de alertas.

- **Software externo co que interactúa**:
  - Sistemas para notificacións (correo electrónico, Slack, Telegram...), a través da configuración de Alertmanager.

---

#### Usuarios

##### Configuración inicial de seguridade  

- **Usuarios de servizo**: Creáronse contas especificas para cada servizo, sen acceso a shell nin a directorio persoal. Isto evita que se poidan usar para iniciar sesión e limita os permisos ao mínimo.  

- **Acceso á rede**: As máquinas están configuradas en modo bridge, para permitir a comunicación direct entre elas dentro da mesma rede. Só se abren os portos necesarios para cada servizo (9090, 3000, 9093, 9100).  

---

##### Usuarios do sistema  

A máquina **VM-Monitorización** é a única que conta con usuario administrador principal que só está ao acceso do administrador para tarefas de mantamento. Os servizos só se executan mediante os seus respectivos usuarios restrinxidos.  

---

##### Usuarios da aplicación  

- **Grafana**: Configúrase o usuario admin por defecto cun contrasinal que se cambia no primeiro inicio por unha máis forte. Dentro da aplicación podense crear máis contas con permisos especificos (visualización, edición, etc...)  

- ** Outros servizos**: Non dispoñen de xestión de usuarios na interfaz web polo tanto o contról recae na configuración de rede ou o uso de servizos externos.

---

#### Despregue  

<img src="doc/img/DIAGRAMA_DE_FUNCIONAMENTO.png" />

## Xestión de incidencias

#### 1. Incidencias de sistema

- **Caída de servizos**: Pode ocorrer que Prometheus, Grafana ou Alertmanager deixen de funcionar por erro de configuración ou consumo de recursos.  
  - Detección: mediante alertas automáticas e comandos como `systemctl status` ou `journalctl`.  
  - Solución: reiniciar o servizo afectado ou revisar os logs de erro correspondentes.

- **Accesos non autorizados**: Accesos non permitidos á interfaz web de Grafana ou Alertmanager.  
  - Prevención: uso de contrasinais seguras e xestión de usuarios con roles ben definidos.  
  - Detección: revisión dos logs de acceso ou activación de alertas ante intentos fallidos reiterados.  
  - Solución: restrinxir o acceso IP, modificar contrasinais ou revisar configuracións de seguridade.

- **Problemas de rede ou conexión**: Fallos na comunicación entre Prometheus e os exporters.  
  - Detección: métricas ausentes ou alertas de "target down".  
  - Solución: verificar conectividade, revisar o ficheiro `prometheus.yml` e comprobar se o exporter está activo.

---

#### 2. Incidencias de software
Relacionadas co funcionamento lóxico do sistema ou erros de configuración:

- **Erro na configuración de Prometheus ou Alertmanager**:  
  - Detección: Prometheus non arranca ou mostra erros de validación.  
  - Solución: revisar o ficheiro `prometheus.yml` ou `alertmanager.yml` co comando `promtool check config`.

- **Problemas coa visualización en Grafana**:  
  - Dashboards que non cargan ou que non amosan datos actualizados.  
  - Solución: comprobar que Prometheus está configurado correctamente como fonte de datos e que as consultas están ben definidas.

- **Alertas mal configuradas**:  
  - Alertas que non se activan ou que envían notificacións erróneas.  
  - Solución: revisar as regras de alerta en `prometheus.yml` e comprobar que Alertmanager está funcionando e ben enlazado.

---

### Procedemento xeral de xestión de incidencias

1. **Detección da incidencia**: a través das alertas configuradas, revisión de métricas ou supervisión directa.
2. **Análise do erro**: consultar logs de sistema (`journalctl`), revisar ficheiros de configuración, comprobar o estado dos servizos.
3. **Resolución**: aplicar a solución correspondente segundo o tipo de incidencia.
4. **Documentación da incidencia**: rexistro manual (ou futuro sistema automatizado) co resumo da causa, accións tomadas e resultado.

