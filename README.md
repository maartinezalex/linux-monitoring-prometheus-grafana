# Proxecto fin de ciclo

<img src="doc/img/portada.png"
style="width:17cm;height:12.014cm" />


## Sistema de monitorización

O proxecto consiste en montar un sistema de monitorización pensado para pequenas e medianas empresas que están dando os seus primeiros pasos na dixitalización e non dispoñen das ferramentas para controlar o estado dos seus equipos.  

A idea é usar software libre, como Prometheus e Grafana, para recoller e visualizar métricas en tempo real (CPU, memoria, disco). Todo isto pódese ver dende o navegador en forma de gráficos, tamén se poden configurar alertas para notificar se algún valor supera os límites establecidos.  

Ademais da parte práctica, inclúese unha guía técnica co proceso completo  de instalación e configuración, pensada para que unha persoa con coñecementos básicos sexa capaz de replicalo con pouco esforzo. Todo funciona sobre máquinas virtuais o cal é un plus evitando así hardware extra.  

A fin é ofrecer unha solución útil, sixela e que axude a detectar problemas técnicos antes de que afecten á actividade da empresa.

## Instalación / Puesta en marcha

A instalación deste sistema consta de 3 partes. Primeiro hai que preparar o entorno virtual que neste caso é VirtualBox, sobre o cal van a traballar as máquinas e os servizos. Unha vez a base está sentada hai que crear as máquinas virtuais e instalar/configurar as ferramentas na máquina número 1 e na máquina número 2. Con todo xa instalado e configurado podense comezar a facer probas e crear alertas ou dashboards para personalizalo e deixalo da forma que máis se adapte as necesidades.  
Para ver de forma máis detallada a instalación paso por paso pódese consultar a parte de [implantación](/doc/templates/6_implantacion.md) que consta neste mesmo proxecto.

## Uso

Unha vez que todo esté configurado imos acceder aos servizos a través da dirección IP neste caso do servidor a cal será a mesma para todos a excepción dos portos que empregamos para cada unha para acceder desde o navegador.  

A maior parte das veces accedese a interfaz de Grafana (porto 3000) e unha vez dentro poderemos visualizar/crear dashboards, aplicar filtros e crear novos paneis.  

Se en algun momento se supera certo umbral establecido polo técnico ou o administrador, a alerta chega as canles configuradas para a sua notificación (correo, telegram...) en función da hora ou o crítico que sexa. Estas configuracións tamén se poden ver a través da propia interfaz de Alertmanager no porto 9093 ainda que a maior parte da configuración recae nos ficheiro [prometheus.yml](/src/prometheus.yml) e [alertmanager.yml](/src/alertmanager.yml).

## Sobre o autor

Chámome Alejandro Martínez e son estudante de ASIR. Desde pequeno sempre me gustou trastear cos ordenadores e isto foi o que me motivou a dedicarme nesta área e continuar os meus estudos. Estou especialmente interesado polas ramas de redes e ciberseguridade, aínda que me manteño aberto a novas áreas e sempre intento aprender e actualizar os meus coñecementos día a día.

Con este proxecto pretendia afondar na monitorización de sistemas porque o considero unha parte clave para manter a seguridad no entorno e infraestructura tecnoloxica. Sirveme ademais como practica para aplicar moitas das cousas que aprendin ao longo deste curso e a entender como se poden optimizar e controlar os recursos dun sistema.

Pódese contactar comigo por correo electrónico en ou a través do meu perfil en LinkedIn.

## Licencia

Este proxecto está licenciado baixo a [GNU Free Documentation License Version 1.3](https://gitlab.com/iesleliadoura/asir2/alejandro-martinez/-/blob/main/doc/LICENSE.txt).  
Para mais detalles, ver o texto completo a continuación.


## Índice de la documentación del proyecto

1. Anteproyecto
    * 1.1. [Idea](doc/templates/1_idea.md)
    * 1.2. [Necesidades](doc/templates/2_necesidades.md)
2. [Análisis](doc/templates/3_analise.md)
3. [Planificación](doc/templates/4_planificacion.md)
4. [Diseño](doc/templates/5_deseño.md)
5. [Implantación](doc/templates/6_implantacion.md)

## Links

- Oracle. (2024, 27 de setembro). *Downloads – Oracle VirtualBox*. [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

- Bujarra. (s.f.). *Blog Bujarra: Documentación sobre recolección de métricas*. [https://www.bujarra.com](https://www.bujarra.com)

- Grafana Labs. (s.f.). *Grafana*. [https://grafana.com](https://grafana.com)

- Prometheus Authors. (s.f.). *Prometheus: Monitoring system & time series database*. [https://prometheus.io](https://prometheus.io)


