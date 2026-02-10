# FASE DE PLANIFICACIÓN DO PROXECTO

## Obxectivos do proxecto

## Guía de planificación do proxecto

### Metodoloxía

A metodoloxía que se vai empregar para desenvolver o proxecto será en cascada, esto vainos permitir definir con claridade que esperamos conseguir en cada etapa e non avanzar á seguinte ata que a fase se resolva de maneira satisfactoria. Isto garantirá unha base bastante sólida en cada paso que se dea e, no caso de que xurda algún erro, ao estar ben estructurado será máis doado localizar a orixe do problema e corrixilo.

### Fases planificadas

#### Fase 1: Idea

Descrición: Nesta fase analízanse o problema de partida, identifícase as necesidades e estudase a competencia. En base a todo isto, defínese a idea do proxecto e a quen o queremos dirixir, planifícase un modelo de negocio inicial e escollense as ferramentas que se van a usar.

Recursos hardware/software: Editor de texto, navegador, acceso a internet.

Recursos humanos: 1 persoa con perfil técnico

Duración: 7 días 


#### Fase 2: Necesidades

Descrición: Nesta fase analízanse os problemas detectados. Delimítanse as necesidades ás que se quere dar resposta e tamén se estuda o contexto actual das PEMES. Márcase un obxectivo e propoñense os medios para conseguilo asi como as actividades e os recursos a empregar. Estúdase a viabilidade técnica e económica da solución e compárase coa competencia para valorar pros e contras.

Recursos hardware/software: Editor de texto, navegador, acceso a internet.

Recursos humanos: 1 persoa

Duración: 7 días

#### Fase 3: Análise

Descrición: Nesta fase defínense os compoñentes técnicos do sistema, especifícanse as ferramentas seleccionadas e a súa interacción. Establécense as funcionalidades principais, os tipos de usuario, os requisitos non funcionais e a arquitectura da solución. Tamén se poñen en consideración posibles melloras futuras.

Recursos hardware/software: Mesmas que na fase 2

Recursos humanos: 1 persoa

Duración: 7 días

#### Fase 4: Planificación

Descrición: Nesta fase estructúrase e organízase todo o proxecto, establécense as fases de traballo, prazos estimados, recursos e a distribución de tarefas. Defínese un diagrama de Gantt cas actividades do proxecto e calcúlase un orzamento estimado para garantir un desenvolvemento controlado e realista.

Recursos hardware/software: Editor de texto, canva, ganttproject, navegador web.

Recursos humanos: 1 persoa

Duración: 7 días.

#### Fase 5: Deseño

Descrición: Nesta fase defínese a arquitectura da solución, establécese unha máquina principal que integra os servizos, completase o deseño técnico do sistema e mostranse as interfaces dos usuarios.

Recursos hardware/software: Editor de texto, VirtualBox, Ubuntu Server, Prometheus, Grafana.

Recursos humanos: 1 persoa

Duración: 7 días.

#### Fase 6: Implantación

Descrición: Nesta fase lévase a práctica o plantexado no proxecto. Instálase o software de virtualización (VirtualBox) e creanse dúas máquinas, unha centraliza os servizos (Prometheus, Grafana, Alertmanager...) mentres que a outra servirá para ser monitorizada (Node Exporter). Instálanse os servizos, créanse usuarios, axústanse permisos e realizase a configuración entre os diferentes compoñentes. Unha vez implantado o sistema realizanse probas e verificación para descartar posibles erros. 

Recursos hardware/software: VirtualBox, Ubuntu Server, Ubuntu Desktio, Prometheus, Grafana, Node Exporter, navegador web.

Recursos humanos: 1 persoa

Duración: 7 días.  

#### Fase 7: Presentación

Descrición: Nesta fase finalizase a documentación e preparase a exposición oral. Para eso elabórase un apoio visual que sexa de útilidade tanto para que o expón como para que sexa máis doado de entender para os demais. Tamén se emprega o tempo dedicado nesta fase a comprobar e verificar que a solución está lista para facer probas e demostracións.

Recursos hardware/software: Editor de texto, Canva, Powerpoint, VirtualBox

Recursos humanos: 1 persoa

Duración: 15 días.

### Diagrama de Gantt

<img src="doc/img/diagrama_gantt.png">

## Orzamento

Este proxecto foi deseñado para levarse a cabo sen incorrer en custos económicos directos. Todos os compoñentes utilizados son de software libre e gratuíto, o que elimina o gasto asociado a licenzas ou adquisición de ferramentas específicas. Ademais, a infraestrutura base foi implementada nunha máquina virtual en VirtualBox, o que permite evitar tamén o custo derivado do alugueiro de servidores ou compra de hardware.  

En canto a parte de hardware para este proxecto estou usando o meu equipo persoal que está completamente equipado para realizar as tarefas que se esperan desta actividade. A continuación comentanse as especificacións do equipo:  

- **Procesador**: Intel Core i7-12700K

- **Placa base**: ASUS TUF GAMING Z690-PLUS WIFI D4

- **Memoria RAM**: Corsair Vengeance LPX DDR4 3200MHz 32GB (2x16GB) CL16

- **Tarxeta gráfica**: Nvidia GeForce RTX 3060 12GB

- **Almacenamento principal**: Kingston FURY Renegade 2TB SSD NVMe PCIe 4.0 M.2 Gen4

- **Almacenamento secundario**: Kioxia Exceria G2 1TB SSD NVMe M.2 2280

- **Refrixeración**: Tempest Liquid Cooler 360

- **Fonte de alimentación**: Corsair RMx RM1000x 1000W

### Orzamento por partidas de inversión / gasto:

| Compoñente             | Modelo / Especificación                                                  | Prezo aproximado (€) |
|------------------------|---------------------------------------------------------------------------|----------------------|
| **Procesador**         | Intel Core i7-12700K – 12 núcleos / 20 fíos                               | 350 €               |
| **Placa base**         | ASUS TUF GAMING Z690-PLUS WIFI D4                                         | 220 €               |
| **Refrigeración**      | Tempest Liquid Cooler 360 – Refrixeración líquida AIO                     | 90 €                |
| **Memoria RAM**        | Corsair Vengeance LPX DDR4 3200MHz 32GB (2x16GB) CL16                     | 90 €                |
| **Disco SSD (principal)**  | Kingston FURY Renegade 2TB NVMe PCIe 4.0 M.2 Gen4                    | 200 €               |
| **Disco SSD (secundario)**| Kioxia Exceria G2 1TB NVMe M.2 2280                                    | 70 €                |
| **Fonte de alimentación** | Corsair RMx RM1000x 1000W 80 Plus Gold Modular                         | 160 €               |
| **TOTAL**              |                                                                           | **1.180 €**         |

### Man de obra

A pesar de que este proxecto non supón custes directos en software ou infraestrutura, cómpre facer unha estimación do tempo invertido nas distintas fases, xa que este constitúe o principal recurso consumido. A continuación detállase a repartición das horas de traballo segundo as fases do proxecto, tomando como referencia unha dedicación diaria de 8 horas entre o 28 de abril e o 15 de xuño (excluíndo fins de semana), cun total estimado de 250 horas. A tarifa de man de obra considerouse de 10 € por hora.

| Fase                               | Horas estimadas | Custo (€) |
|------------------------------------|------------------|-----------|
| 1. Idea inicial e motivación       | 10 h             | 100 €     |
| 2. Recompilación de necesidades    | 15 h             | 150 €     |
| 3. Análise do sistema              | 25 h             | 250 €     |
| 4. Planificación                   | 20 h             | 200 €     |
| 5. Deseño da solución              | 30 h             | 300 €     |
| 6. Implantación técnica            | 70 h             | 700 €     |
| 7. Probas e validación             | 30 h             | 300 €     |
| 9. Documentación técnica e final   | 50 h             | 500 €     |
| **TOTAL**                          | **250 h**        | **2.500 €** |

| **COSTE TOTAL**              |                                                                           | **3.680 €**         |





