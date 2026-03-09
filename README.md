Análisis Integral de la Topología de Red, Infraestructura Tecnológica y Arquitectura de Comunicaciones en Corferias para los Procesos Electorales en Colombia

La infraestructura tecnológica desplegada en la Corporación de Ferias y Exposiciones (Corferias) durante los certámenes electorales en Colombia constituye uno de los ecosistemas de red más robustos, complejos y críticos de la región andina. Corferias no solo funciona como el puesto censo más grande del país, albergando a miles de ciudadanos cuya cédula fue expedida en Bogotá y nunca fue inscrita en otro lugar, sino que también sirve como el epicentro de las Comisiones Escrutadoras, el Puesto de Mando Unificado (PMU) y el centro neurálgico para la consolidación de datos a nivel distrital y nacional. La topología de red que se implementa en este recinto debe responder a exigencias de disponibilidad superiores al 99.9%, integrando capas de seguridad que protejan la integridad de la voluntad popular frente a amenazas físicas y cibernéticas en un entorno de alta densidad de dispositivos y usuarios.
Marco Contractual y Modelos de Provisión de Infraestructura Tecnológica
La configuración de la red en Corferias no es un despliegue estático, sino una arquitectura efímera pero de alto rendimiento que se instala bajo el modelo de "Solución Integral" contratada por la Registraduría Nacional del Estado Civil (RNEC). Históricamente, este proceso ha sido gestionado por un ecosistema de contratistas especializados que conforman uniones temporales, siendo la UT Disproel e Indra Colombia los actores más relevantes en la última década. El modelo de contratación se basa en la externalización de la infraestructura, donde el contratista debe proveer no solo el hardware y el software, sino también la conectividad de última milla, el soporte técnico y la ciberseguridad.
Para el periodo 2025-2026, la RNEC ha presupuestado inversiones masivas en tecnología que superan los 1.3 billones de pesos, destinando una fracción significativa al fortalecimiento de la plataforma tecnológica que soporta la identificación y el escrutinio. En este contexto, Corferias es contratado de manera directa como el inmueble idóneo debido a sus capacidades técnicas únicas, con contratos que rondan los 7.671 millones de pesos solo por concepto de arrendamiento y adecuación básica de espacios.
La relación entre Corferias y la RNEC es técnica y operativa. El recinto debe garantizar internet de banda ancha, suministro eléctrico ininterrumpido y una infraestructura de audio y video distribuida en múltiples pabellones. Esta base física es la que permite al contratista de la "Solución Integral" superponer una topología lógica de red segura, aislando el tráfico de datos electorales del resto de los servicios del recinto.
Topología Física de Red: El Diseño en Estrella Extendida
La topología física de red en Corferias durante las elecciones se define como una Estructura en Estrella Extendida (Extended Star Topology). Esta configuración es la respuesta técnica a la magnitud geográfica del recinto, que abarca más de 23 pabellones y áreas de servicio que deben estar interconectadas en un tiempo de respuesta de milisegundos.
El Nodo Central de Comunicaciones (MDF)En el centro de esta estrella se sitúa el Main Distribution Frame (MDF) o nodo central, ubicado generalmente en una zona de alta seguridad dentro del pabellón administrativo o en el Gran Salón de Corferias. Este nodo alberga los switches de núcleo (Core Switches) de alta capacidad, los cuales gestionan el tráfico total de la red. Desde este punto central, se despliegan troncales de fibra óptica monomodo hacia cada uno de los pabellones operativos, actuando estos como nodos de distribución secundaria o IDFs (Intermediate Distribution Frames).
Capa de Distribución y Acceso en Pabellones
Cada pabellón (como el Pabellón 3, 6 o los pabellones 10 al 16) funciona como un segmento de red independiente pero integrado. Los switches de distribución en estos pabellones reciben el enlace de fibra óptica y lo redistribuyen mediante cableado de cobre de alta categoría (Cat 6A o Cat 7) hacia los puntos de acceso finales. Estos puntos incluyen:
Estaciones de Biometría: Ubicadas en las entradas de los pabellones y junto a las mesas de votación para la autenticación de los 755.323 ciudadanos aptos para votar en el departamento.
Comisiones Escrutadoras: 
Áreas que requieren internet de banda ancha y conectividad LAN para el ingreso de datos en los sistemas de escrutinio.
Oficinas de Control y PMU: 
Espacios que demandan una latencia mínima para el monitoreo de comunicaciones en tiempo real.
Requisitos de Equipamiento por Área Operativa
El despliegue físico debe cumplir con especificaciones técnicas rigurosas para soportar la carga de trabajo de la jornada electoral. Los pliegos de condiciones exigen áreas de alistamiento de al menos 8.000 m² y salones de capacitación equipados con infraestructura tecnológica completa.
Espacio en Corferias:
Salones de Capacitación7.000 m² (Aprox.)
350 escritorios con puntos de red Comisiones de Escrutinio
Áreas de 1.500 m²
Conectividad LAN/WAN para 280 escritorios 
PMU y Centro de Mando 200 m²
Enlaces redundantes y monitoreo 24/7 
Bodegas de Material 8.000 m² 
CCTV y control de acceso digital 
Topología Lógica y Segmentación de Red: Seguridad por Aislamiento
Si bien la topología física es una estrella, la topología lógica se estructura mediante una segmentación estricta a través de Redes de Área Local Virtuales (VLANs) y túneles encriptados (VPNs). Esta arquitectura lógica garantiza que el tráfico de voz, video, datos biométricos y resultados electorales no se mezcle, evitando colisiones de red y, sobre todo, minimizando la superficie de ataque para posibles intrusiones.
Arquitectura de VLANs y Priorización de Tráfico
La red se divide en segmentos lógicos según la función del usuario. La VLAN destinada a la biometría tiene la prioridad más alta en los protocolos de Calidad de Servicio (QoS), asegurando que la validación de un votante no se retrase por el tráfico generado en la red de prensa o administrativa.
1.	VLAN de Autenticación Biométrica: Conecta las estaciones de validación con las bases de datos locales o el ABIS (Automated Biometric Identification System). Utiliza protocolos de cifrado AES-256 para proteger las minucias dactilares y faciales.
2.	VLAN de Escrutinio y Consolidación: Es una red de acceso restringido donde operan los softwares de Indra y Disproel. El acceso a este segmento está limitado por direcciones MAC y requiere autenticación multifactor.
3.	VLAN de Seguridad y CCTV: Gestiona el flujo de video de alta definición de las cámaras de vigilancia en todo el recinto de Corferias, integrándose con el PMU.
4.	VLAN de Prensa y Divulgación: Segmento con salida a internet controlada para que los medios de comunicación puedan transmitir resultados preliminares (preconteo) sin comprometer la red interna de escrutinio.
El Modelo de Red "Air-Gapped" en el Voto Electrónico
En las pruebas piloto de Voto Electrónico Presencial (VEP) que se han planteado para recintos como Corferias, la topología lógica introduce un concepto de aislamiento total o "Air-gap". Las máquinas de votación en las mesas no están conectadas físicamente ni vía Wi-Fi a ninguna red externa durante la jornada. Los resultados de estas mesas se extraen mediante medios extraíbles (USB) con firmas digitales y sellos de tiempo, los cuales se transportan físicamente a un Punto de Transmisión dentro de Corferias que cuenta con una conexión segura vía VPN hacia el Centro Nacional de Procesamiento de Datos.
Infraestructura de Biometría: Edge Computing y Centralización
La biometría es el componente que mayor presión ejerce sobre la topología de red en Corferias. Con la meta de llegar a 80.000 mesas con biometría dactilar y facial para 2026, la red debe ser capaz de gestionar ráfagas masivas de solicitudes de autenticación.
Funcionamiento de las Estaciones Biométricas
Para mitigar los riesgos de una caída de conectividad WAN, la topología de biometría en Corferias utiliza un modelo híbrido de Edge Computing. Cada dispositivo o estación de verificación cuenta con una base de datos local (Censo de la Mesa) cargada en formato ISO encriptado. Cuando un ciudadano pone su huella o presenta su rostro, el dispositivo realiza el cotejo 1:1 localmente contra la información almacenada en el chip de la cédula o en su memoria interna, lo que reduce la latencia a menos de un segundo.
Posteriormente, la estación sincroniza el "log" de la votación con el servidor central de la RNEC. Esta sincronización ocurre a través de redes inalámbricas privadas (APN dedicados) o mediante la red LAN segura del pabellón, utilizando túneles IPsec. Este flujo de datos permite que las autoridades tengan una visión en tiempo real de la participación sin comprometer el secreto del voto, ya que el sistema biométrico solo certifica la identidad y no la elección del ciudadano.

 

Transmisión desde la Mesa hasta la Consolidación
La topología de red debe soportar dos procesos paralelos con requerimientos de integridad y velocidad diferenciados: el Preconteo y el Escrutinio. En Corferias, ambos procesos coexisten pero fluyen por canales lógicos distintos.
La Red de Preconteo (Información Rápida)
El preconteo es el proceso de transmisión de los resultados de las mesas a través de voz o digitalización rápida para informar a la ciudadanía. En Corferias, los transmisores de datos utilizan la red de telefonía o dispositivos móviles conectados a una red Wi-Fi segura para dictar o enviar las actas E-14. Este tráfico se dirige a centros de recepción de datos (call centers o servidores de carga) que consolidan la información para su publicación en la web de la Registraduría. Aunque este proceso es el más visible, carece de valor jurídico, por lo que su red se prioriza por disponibilidad y velocidad.
La Red de Escrutinio (Validez Legal)
El escrutinio es el proceso formal donde los jueces y comisiones verifican las actas E-14 físicas contra las digitales. La red de escrutinio en Corferias es una Intranet altamente protegida. Los escáneres de alta velocidad digitalizan los formularios E-14 originales, y estas imágenes se transmiten a servidores locales de alta disponibilidad.
Un aspecto crítico de esta topología es la redundancia de servidores. Los servidores de consolidación deben ser físicos y estar hospedados en un data center seguro dentro del recinto o en una ubicación privada de la RNEC; el uso de nubes públicas (Cloud) está explícitamente prohibido para el almacenamiento de resultados por razones de soberanía y seguridad de los datos. La integridad se garantiza mediante el uso de firmas digitales y el "sellado" del código fuente del software, cuya contraseña se fragmenta entre diferentes actores (Registraduría, auditores, Procuraduría) para evitar que un solo individuo pueda alterar el sistema.
Ciberseguridad: Blindaje y Resiliencia de la Topología de Red
La topología de red en Corferias está diseñada bajo el principio de "Defensa en Profundidad". Dado que el sistema electoral colombiano ha sido objeto de narrativas de fraude y ataques cibernéticos, la infraestructura debe ser capaz de resistir incidentes sin interrumpir el proceso.
Capas de Protección Implementadas
1.	Protección de Borde (Anti-DDoS): La red de Corferias cuenta con mitigación de ataques de Denegación de Servicio Distribuido a través de servicios de limpieza de tráfico (Scrubbing Centers). Esto previene que ataques masivos desde el exterior saturen los enlaces de salida y bloqueen la transmisión de resultados.
2.	Firewalls de Próxima Generación (NGFW): Implementados en el Core y en los IDFs de cada pabellón, realizan inspección profunda de paquetes (DPI) para identificar comportamientos anómalos o intentos de inyección SQL en las bases de datos de escrutinio.
3.	Detección y Respuesta (EDR/XDR): Los terminales (laptops y estaciones de trabajo) utilizados por los jurados y escrutadores cuentan con software que monitorea actividades sospechosas en tiempo real, bloqueando cualquier intento de conexión no autorizada a puertos críticos.
4.	Aislamiento de Bases de Datos: Las bases de datos que contienen el censo y los resultados están aisladas en un segmento de red que solo permite conexiones desde aplicaciones autorizadas, impidiendo el acceso directo a nivel de red.
Resiliencia Física y Energía
La topología de red se sustenta sobre una infraestructura de soporte vital. Corferias garantiza esquemas de contingencia que cubren ausencias de fluido eléctrico mediante plantas de emergencia y UPS (Uninterruptible Power Supply) en cada nodo de red. Esto es vital para evitar la corrupción de datos en las bases de datos SQL de escrutinio durante un corte de energía imprevisto. Además, el cierre de vías y perímetros de seguridad alrededor de Corferias actúa como una capa de "seguridad física de la red", impidiendo que atacantes tengan acceso físico a los puntos de red o cámaras de inspección de cableado.
Retos Técnicos y Hallazgos en la Auditoría de Red
A pesar de la sofisticación de la topología, diversas misiones de observación y organizaciones técnicas han identificado áreas de mejora y riesgos inherentes al modelo de tercerización.
El Riesgo de la Interconexión de Niveles
Un hallazgo técnico relevante de la Fundación Karisma señala que no siempre existe un mecanismo automatizado que verifique que la información que sale del software de escrutinio municipal (gestionado por Disproel) sea exactamente la misma que ingresa al nivel nacional (gestionado por Indra). En la topología de red, esto se traduce en un "salto" de datos que depende de procesos manuales o de carga de archivos, lo que representa un cuello de botella para la integridad absoluta si no se aplican funciones de hash o firmas digitales consistentes en todo el trayecto.
La Propiedad del Software y la "Caja Negra"
La dependencia de software privado para los escrutinios territoriales ha sido un punto de contención. Mientras que el software del Consejo Nacional Electoral (CNE) es de propiedad estatal, los sistemas utilizados en Corferias para los escrutinios auxiliares y zonales suelen ser propiedad de los contratistas. Esto limita la visibilidad total de la red lógica y del código fuente para auditores externos, quienes a menudo enfrentan restricciones físicas (como la prohibición de celulares) y contratos de confidencialidad estrictos al intentar auditar la infraestructura.
Futuro de la Topología: 5G, IA y Biometría Facial hacia 2026
La hoja de ruta para las elecciones de 2026 en Corferias contempla una evolución significativa en la topología de comunicaciones. La implementación masiva de biometría facial requerirá una infraestructura de red con mayor ancho de banda y menor latencia, posiblemente aprovechando tecnologías como el 5G para los dispositivos móviles de los delegados.
Integración de Inteligencia Artificial
La red no solo transportará datos, sino que integrará capas de Inteligencia Artificial para la detección temprana de anomalías en los patrones de votación. Redes neuronales especializadas operarán sobre el tráfico de datos para identificar si los rasgos faciales de los votantes coinciden con los registros históricos, alertando al PMU sobre posibles suplantaciones sistemáticas.
Plan de Ciberseguridad 2026
El plan de blindaje tecnológico para el próximo ciclo electoral incluye:
1.	Monitoreo 24/7 con IA: Análisis especializado de amenazas para detectar campañas de suplantación o intentos de intrusión a las plataformas digitales.
2.	Fortalecimiento de la Identidad Digital: Uso de la cédula digital como llave de acceso para los jurados de votación en la plataforma de red.
3.	Simulacros Nacionales de Estrés de Red: Pruebas de carga en Corferias para asegurar que la topología física y lógica pueda soportar el doble del tráfico registrado en 2022 sin degradación del servicio
 
Diseño de infraestructura de la red
Diseñar la infraestructura de red para un centro de votación masivo como Corferias (el puesto de votación más grande de Colombia) para las elecciones es un proyecto crítico. La red debe garantizar alta disponibilidad, integridad de los datos, seguridad extrema y tolerancia a fallos.
1.	Criterios de Diseño de la Red
Para un evento de seguridad nacional como unas elecciones, la red en Corferias se diseña bajo el modelo jerárquico de Cisco (Core, Distribución, Acceso) con los siguientes criterios:
Alta Disponibilidad (Redundancia): Si un switch o router falla, la red no puede caerse. Todo equipo central y enlace debe estar duplicado.
Segmentación Estricta: Los equipos de transmisión de resultados (E-14) no pueden estar en la misma red que el WiFi de la prensa o el sistema de biometría.
Seguridad y Cifrado: Los datos de preconteo que viajan desde Corferias hasta el Data Center central de la Registraduría deben ir cifrados.
Trazabilidad temporal: Los relojes de todos los equipos deben estar sincronizados exactamente para propósitos de auditoría legal.
2.	Topología Lógica y Segmentación (VLANs)
se debio configurar las siguientes VLANs para separar el tráfico dentro de los diferentes pabellones de Corferias
3.	Protocolos Implementados
Capa 2 (Switching):RSTP (Rapid Spanning Tree Protocol): Para evitar bucles de red debido a las conexiones redundantes entre pabellones.
Port Security: En los puertos de la VLAN 20, para que solo las MAC Address de los portátiles autorizados por la Registraduría puedan conectarse.
Capa 3 (Routing y Alta Disponibilidad):HSRP (Hot Standby Router Protocol): Para crear una puerta de enlace virtual (Gateway) redundante. Si el switch Core A falla, el Core B asume el enrutamiento sin desconectar los equipos.OSPFv2: Protocolo de enrutamiento dinámico interno para que los equipos de Corferias conozcan las rutas.
Seguridad perimetral:IPsec VPN (Site-to-Site): Túnel cifrado desde el Router de Borde de Corferias hasta un Router que simule el "Data Center de la Registraduría Nacional".ACLs (Listas de Control de Acceso): Reglas para bloquear que la VLAN de Prensa (40) haga ping o se comunique con la VLAN de Resultados (20).
4.	Armado de un pabellon
