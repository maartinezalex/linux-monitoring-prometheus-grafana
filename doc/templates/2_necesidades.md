# Estudo de necesidades e modelo de negocio

## Xustificación das necesidades detectadas que cubre o sistema a desenvolver

### 1. Problemática

A problemática principal que se detecta neste proxecto é a ausencia dun control efectivo sobre os sistemas informáticos en moitas organizacións, xa sexa por falta de recursos ou por descoñecemento das solucións dispoñibles. Tendo en conta o avance constante da tecnoloxía e a forte dependencia que moitos negocios teñen actualmente dela, non se poden permitir fallos no sistema que poidan afectar á operatividade e causar perdas económicas significativas.

### 2. Xustificación

A posta en marcha dun sistema de monitorización permitirá ás empresas dispoñer dunha ferramenta de supervisión continua, que lles ofrecerá en tempo real os valores de todos os sistemas monitorizados. Deste xeito, poderán detectar anomalías mesmo antes de que se convertan en problemas maiores e, no caso de que deriven nunha incidencia, contarán cun tempo de resposta suficiente para solucionala o máis rápido posible.

### 3. Obxectivo xeral  

O obxectivo principal do proxecto é poñer en práctica todos os coñecementos adquiridos ao longo da formación para crear unha solución efectiva, que cumpra coas expectativas e que lles permita as empresas que están comezando a súa dixitalización ter un contorno o máis seguro e controlado posible.

### 4. Desenvolvemento

#### 4.1 Resposta á necesidade  

Para responder ás necesidades desta proposta, é necesario implantar un sistema que permita controlar diferentes partes da infraestrutura con datos en tempo real e de forma ininterrompida, permitindo visualizar e analizar distintos tipos de información adaptada ás necesidades de cada negocio.

Adicionalmente, nos casos nos que certas anomalías ou variacións superen determinados limiares, preténdese que o sistema as notifique por diferentes vías, de maneira que o tempo entre a detección da fluctuación e a alerta ao usuario sexa mínimo. Isto permitirá unha maior organización e un tempo de resposta máis rápido ante distintas problemáticas, tanto en tarefas de prevención como de actuación.

#### 4.2 Medios, actividades e recursos

##### Medios técnicos

- Máquinas virtuais para simular un contorno real de traballo.

- Sistema operativo Ubuntu Server como base para os servizos.

- Ferramentas a implementar: Prometheus, Grafana, Node Exporter e Alertmanager.

    
##### Recursos Humanos  

- Perfil técnico con coñecementos en redes e sistemas.
    
##### Actividades  

1. **Definición e planificación:** Deseño da arquitectura do sistema de monitorización, establecendo os compoñentes principais así como a súa configuración e os requisitos técnicos.

2. **Implantación:** Instalación e configuración de Prometheus, Grafana, Node Exporter e Alertmanager asegurando que se integren correctamente entre eles.

3. **Probas e verificación:** Realizar varias probas de funcionamento para comprobar e descartar posibles erros no paso de implantación.

4. **Documentación:** Realizarase unha guía técnica completa cos pasos detallados da instalación do sistema e facilitar a implantación noutras empresas.

5. **Guía de uso e formación:** Creación de material explicativo para entender o uso dos dashboards e configuración de alertas para un uso autónomo da solución.

6. **Comercialización e difusión:** Deseño do paquete final xunto con estratexias de promoción.

#### 4.3 Metodoloxía 

Para a realización deste proxecto optarase por unha metodoloxía en cascada, pola cal se definirán con claridade cada etapa e os pasos a seguir.

Este enfoque permitirá delimitar de maneira estruturada as tarefas a realizar e facilitará a elaboración dunha documentación que recolla o traballo feito en cada fase, pensada para a súa posterior distribución como guía técnica.

Ademais, resultará útil para garantir a estabilidade do sistema, xa que cada fase depende da correcta realización da anterior, o que favorece unha implantación sólida e controlada da solución.

#### 4.4 Persoal  

Todas as actividades citadas con anterioridade están planificadas para seren realizadas por unha soa persoa con coñecementos técnicos. Con todo, a solución está pensada para ofrecer unha gran escalabilidade no futuro, incorporando máis funcionalidades e abarcando un ámbito moito máis amplo. Nun primeiro momento, está concibida para cumprir unhas funcións máis limitadas e poder ser desenvolvida íntegramente por unha única persoa.

#### 4.5 Temporalización

Tendo en conta as actividades que se van realizar (planificación, implantación, documentación, etc.) e que o prazo dado foi de dous meses aproximadamente contando co feito de que será unha soa persoa a encargada da súa execución, pódese facer unha estimación dun tempo moi inferior ao prazo dado, co cal se pretende entregar unha solución que cumpra coas expectativas. Esta estimación cobre tanto a parte técnica como a redacción da guía, incluíndo probas e revisións. En caso de ser necesario, podería estenderse lixeiramente para melloras ou adaptacións específicas segundo as necesidades.

## Posibilidades de comercialización (viabilidade, competidores…).

### 1. Viabilidade  

#### 1.1 Viabilidade Técnica

Unha gran parte do proxecto foi concibida tendo en conta a súa viabilidade técnica, escollendo ferramentas de software libre que reducen significativamente os custos e que, ademais, poden ser implantadas por unha soa persoa, polo menos na escala na que está deseñado inicialmente o sistema. O feito de empregar tecnoloxías maduras e ben documentadas, como Prometheus, Grafana, Node Exporter ou Alertmanager, facilita enormemente a súa implementación. Ademais, optouse por usar como contorno de desenvolvemento local con VirtualBox, o que permite simular un escenario virtual sen necesidade de infraestructura física e ser facilmente reproducible. Esto vai garantir unha mellor autonomía ao longo do proxecto, así como eliminar numerosas limitacións derivadas da dispoñibilidade de recursos ou servizos externos, ademais as probas e configuracións son máis directas e controladas.

#### 1.2 Viabilidade Económica  

En canto á viabilidade económica, o proxecto está concibido inicialmente a pequena escala, polo que non require un gran investimento inicial, xa que se basea en ferramentas de software libre e nun contorno virtualizado, o que elimina os custos asociados a licenzas ou infraestrutura física.

No caso de querer levalo máis aló dun prototipo técnico e comercializalo de forma profesional, podería ser necesaria un investimento adicional para dispoñer dunha infraestrutura máis robusta e cubrir un ámbito máis amplo. Para estes casos, valoraríase a posibilidade de acceder a axudas públicas destinadas a proxectos de dixitalización, como as que poden ofrecer o Estado ou a Xunta de Galicia, co fin de cubrir unha parte significativa dos custos iniciais.

### 2. Competencia  

Diversas ferramentas xa consolidadas no mercado ofrecen solucións para a monitorización de sistemas, como Zabbix, Nagios ou Datadog. A pesar da súa eficacia en certos contextos, presentan limitacións importantes que este proxecto pretende resolver:

- Moitas destas plataformas funcionan baixo modelos de pago ou restrinxen certas funcionalidades a versións premium.

- Requiren dunha infraestrutura máis potente para garantir un servizo estable, o que pode ser inviable para pequenas empresas.

- A súa complexidade e falta de intuitividade dificultan que usuarios sen formación específica poidan empregalas con autonomía.

A xestión avanzada das alertas é un punto central da proposta. A diferenza doutras ferramentas que concentran toda a lóxica nun único módulo, optouse por separar a detección da notificación mediante a integración de Alertmanager. Isto permite definir distintos niveis de alerta, adaptar o comportamento segundo horarios ou criticidade, e configurar múltiples canles de aviso de forma simultánea. Esta arquitectura modular ofrece unha flexibilidade e control que moitas solucións tradicionais non alcanzan, especialmente nas súas versións libres.

## Ideas para a súa comercialización.

### 1. Promoción  

A mellor forma de promoción da solución será o contacto directo con pequenas e medianas empresas, especialmente aquelas que non dispoñen dun sistema de monitorización ou non son conscientes da súa utilidade. A través das súas canles habituais, identificarase a empresas que fagan uso activo de tecnoloxía pero carezan dun control efectivo sobre os seus sistemas.

A estas organizacións ofreceráselles a solución de forma individualizada, acompañada dunha pequena demostración técnica que permita ver como funciona o sistema e que vantaxes ofrece, especialmente en canto á detección anticipada de problemas e mellora na capacidade de resposta.

Esta estratexia permite achegarse ao público obxectivo de maneira próxima e personalizada, sen depender de campañas publicitarias masivas, e adaptándose mellor ao perfil das PEMEs. Ademais, é unha opción viable a nivel económico e factible de executar por unha soa persoa, o que encaixa perfectamente co alcance inicial do proxecto.


### 2. Modelo de negocio   

O modelo de negocio elixido combina dúas opcións principais:

- **Modelo de pago único** pola entrega dunha guía técnica detallada, que inclúe toda a documentación necesaria para instalar, configurar e utilizar o sistema de monitorización. Esta guía permitirá que as empresas poidan implantar a solución de maneira autónoma e adaptada ao seu contorno.

- **Modelo de subscrición mensual opcional**, dirixido a aquelas empresas que desexen contar con soporte técnico adicional, adaptacións personalizadas, supervisión remota ou melloras continuas do sistema.

Optouse por esta combinación porque se adapta ao perfil de pequenas empresas, que poden non dispoñer de recursos para contratar servizos complexos ou permanentes, pero poden estar interesadas en contar cunha solución fiable e de baixo custo inicial. A guía permítelles acceder á ferramenta sen dependencia externa, mentres que a subscrición mensual abre a porta a un acompañamento profesional sen obrigalas a compromisos a longo prazo.

Este enfoque tamén permite escalar o servizo no futuro, ofrecendo máis niveis de subscrición ou incluso adaptacións personalizadas baixo demanda, segundo o crecemento do proxecto.

