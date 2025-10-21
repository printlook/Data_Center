# CONSTRUCCIÓN DE DATA CENTER
## Propuesta de Implementación según Estándar ANSI/TIA-942

---

**Universidad de San Carlos de Guatemala**  
**Facultad de Ingeniería**  
**Escuela de Ciencias y Sistemas**  
**Manejo e Implementación de Archivos**

**Estudiante:** [Pablo Isai Matusalen Cutzal Mazariegos]  
**Carnet:** [202209622]  
**Sección:** [A]  
**Fecha de Entrega:** 27 de Octubre de 2025

---

## ÍNDICE

1. Introducción
2. Objetivos
3. Niveles del Data Center según ANSI/TIA-942
4. Nivel Tier Seleccionado y Justificación
5. Especificaciones de Hardware
6. Especificaciones de Software
7. Servicios en la Nube
8. Diseño de Arquitectura
9. Diseño de Seguridad
10. Infraestructura de Soporte
11. Consideraciones Ambientales
12. Análisis de Costos
13. Conclusiones
14. Referencias Bibliográficas

---

## 1. INTRODUCCIÓN

Los Data Centers representan la columna vertebral de la infraestructura tecnológica moderna, proporcionando los recursos computacionales, de almacenamiento y conectividad necesarios para soportar operaciones críticas de negocio. La construcción de un Data Center requiere una planificación meticulosa que considere aspectos de disponibilidad, seguridad, escalabilidad y eficiencia energética.

Este documento presenta una propuesta integral para la construcción de un Data Center de nivel empresarial, diseñado bajo los lineamientos del estándar internacional ANSI/TIA-942, que establece las mejores prácticas para la infraestructura de telecomunicaciones en centros de datos.

La propuesta abarca desde la selección del nivel Tier apropiado hasta el diseño detallado de la arquitectura física y lógica, considerando redundancia, seguridad y sostenibilidad como pilares fundamentales del proyecto.

---

## 2. OBJETIVOS

### 2.1 Objetivo General
Diseñar un Data Center de nivel empresarial que cumpla con los estándares internacionales ANSI/TIA-942, garantizando alta disponibilidad, seguridad y eficiencia operacional.

### 2.2 Objetivos Específicos
- Determinar el nivel Tier apropiado según las necesidades de disponibilidad del negocio
- Especificar el hardware y software necesario para la operación del Data Center
- Diseñar la arquitectura de red que garantice redundancia y alto rendimiento
- Implementar medidas de seguridad física y lógica multicapa
- Establecer sistemas de soporte para garantizar la continuidad operacional
- Optimizar el uso de recursos energéticos mediante sistemas eficientes

---

## 3. NIVELES DEL DATA CENTER SEGÚN ANSI/TIA-942

El estándar ANSI/TIA-942 (Telecommunications Infrastructure Standard for Data Centers) define cuatro niveles o "Tiers" que clasifican los Data Centers según su disponibilidad, redundancia y tolerancia a fallos.

### 3.1 Tier I - Infraestructura Básica

**Características principales:**
- Capacidad no redundante
- Único path de distribución (no redundante)
- Susceptible a interrupciones planificadas y no planificadas
- El mantenimiento requiere apagado completo del sistema

**Disponibilidad:** 99.671% (equivalente a 28.8 horas de downtime anual)

**Componentes básicos:**
- Sistema UPS simple sin redundancia (configuración N)
- Generador eléctrico único
- Sistema de enfriamiento no redundante
- Piso elevado opcional
- Sin redundancia en componentes críticos

**Aplicaciones típicas:**
- Pequeñas empresas con operaciones no críticas
- Ambientes de desarrollo y pruebas
- Organizaciones con presupuesto limitado
- Servicios que toleran interrupciones programadas

### 3.2 Tier II - Componentes de Capacidad Redundante

**Características principales:**
- Componentes de capacidad redundantes (configuración N+1)
- Único path de distribución activo
- Permite mantenimiento parcial sin apagado total
- Vulnerable a interrupciones por mantenimiento en path de distribución

**Disponibilidad:** 99.741% (equivalente a 22 horas de downtime anual)

**Componentes esenciales:**
- UPS con configuración N+1 (redundancia en unidades)
- Generadores redundantes N+1
- Sistema de enfriamiento con redundancia N+1
- Piso elevado obligatorio para distribución
- PDUs redundantes

**Aplicaciones típicas:**
- Medianas empresas con operaciones importantes
- Plataformas de comercio electrónico básico
- Servicios con ventanas de mantenimiento planificadas
- Aplicaciones con tolerancia a interrupciones breves

### 3.3 Tier III - Mantenimiento Concurrente

**Características principales:**
- Múltiples paths de distribución (uno activo, uno pasivo)
- Componentes totalmente redundantes (N+1)
- Mantenimiento sin impacto en operaciones
- Tolerante a todos los eventos planificados
- Permite actualización y mantenimiento sin downtime

**Disponibilidad:** 99.982% (equivalente a 1.6 horas de downtime anual)

**Componentes críticos:**
- Doble alimentación eléctrica independiente
- UPS y generadores redundantes N+1 en cada path
- Sistemas de enfriamiento completamente redundantes
- Múltiples rutas de red y telecomunicaciones
- Piso elevado con distribución dual
- Doble entrada de servicios públicos

**Aplicaciones típicas:**
- Empresas grandes con operaciones 24/7
- Instituciones financieras y bancarias
- Servicios críticos de comercio electrónico
- Plataformas SaaS empresariales
- Proveedores de servicios cloud regionales

### 3.4 Tier IV - Tolerante a Fallos

**Características principales:**
- Múltiples paths activos simultáneos (configuración 2N+1)
- Componentes full redundantes e independientes
- Tolerante a cualquier fallo único sin impacto
- Mantenimiento sin impacto alguno en operaciones
- Compartimentación total de sistemas críticos

**Disponibilidad:** 99.995% (equivalente a 0.4 horas de downtime anual)

**Componentes avanzados:**
- Alimentación eléctrica completamente redundante (2N+1)
- Sistemas UPS duales con bypass automático
- Múltiples generadores independientes por path
- Enfriamiento completamente redundante y compartimentado
- Sistemas de detección y supresión de incendios duales
- Compartimentación física de zonas críticas
- Redundancia en sistemas de seguridad física

**Aplicaciones típicas:**
- Bancos centrales y sistemas financieros críticos
- Infraestructura de telecomunicaciones nacional
- Organismos gubernamentales y de defensa
- Servicios de emergencia y salud críticos
- Bolsas de valores y trading de alta frecuencia

### 3.5 Comparativa de Niveles Tier

| Característica | Tier I | Tier II | Tier III | Tier IV |
|----------------|--------|---------|----------|---------|
| Disponibilidad anual | 99.671% | 99.741% | 99.982% | 99.995% |
| Downtime anual máximo | 28.8 horas | 22.0 horas | 1.6 horas | 0.4 horas |
| Paths de distribución | 1 | 1 | 2 (Activo/Pasivo) | 2 (Activo/Activo) |
| Redundancia componentes | N | N+1 | N+1 | 2N+1 |
| Mantenimiento planificado | Requiere apagado | Apagado parcial | Sin impacto | Sin impacto |
| Tolerancia a fallos | No | Parcial | Sí | Completa |
| Inversión inicial | Baja | Media | Alta | Muy Alta |
| Costo operativo anual | Bajo | Medio | Alto | Muy Alto |
| Tiempo de implementación | 3 meses | 6 meses | 12-15 meses | 18-24 meses |

---

## 4. NIVEL TIER SELECCIONADO Y JUSTIFICACIÓN

### 4.1 Selección: Tier III - Mantenimiento Concurrente

Para esta propuesta se ha seleccionado el nivel **Tier III** como el más apropiado para un Data Center empresarial moderno.

### 4.2 Análisis y Justificación de la Selección

**Razones principales para elegir Tier III:**

**1. Balance Costo-Beneficio Óptimo**

El Tier III ofrece el mejor equilibrio entre inversión y disponibilidad:
- Disponibilidad de 99.982% significa solo 1.6 horas de downtime al año
- Costo de implementación aproximadamente 40-50% menor que Tier IV
- Retorno de inversión alcanzable en 4-5 años
- Suficiente para cumplir SLAs empresariales estándar (99.9% - 99.95%)

**2. Flexibilidad Operacional y Mantenimiento**

Ventajas operativas críticas:
- Permite realizar mantenimiento preventivo sin interrumpir servicios
- Actualizaciones de hardware y firmware sin ventanas de downtime
- Expansión de capacidad sin afectar producción
- Reemplazo de componentes defectuosos sin impacto
- Pruebas de sistemas de respaldo sin riesgo operacional

**3. Redundancia Suficiente**

Protección adecuada contra fallos:
- Redundancia N+1 protege contra fallo de cualquier componente único
- Doble path de distribución elimina puntos únicos de fallo críticos
- Sistemas redundantes de energía, enfriamiento y red
- Capacidad de soportar mantenimiento simultáneo en múltiples sistemas

**4. Escalabilidad y Crecimiento Futuro**

Capacidad de evolución:
- Arquitectura permite upgrade futuro a Tier IV si es necesario
- Diseño modular facilita expansión por fases
- Infraestructura dual permite crecimiento sin rediseño
- Compatible con tecnologías emergentes (edge computing, 5G)

**5. Cumplimiento Normativo y Certificaciones**

Adecuado para estándares regulatorios:
- Suficiente para certificaciones ISO 27001 (Seguridad de la Información)
- Cumple requisitos de instituciones financieras (BASEL III)
- Apto para regulaciones de protección de datos (GDPR, CCPA)
- Compatible con auditorías SOC 2 Type II
- Cumple estándares PCI-DSS para manejo de datos de tarjetas

**6. Tolerancia a Eventos Críticos**

Protección robusta:
- Resistente a mantenimientos planificados sin impacto
- Protección contra fallos de componentes individuales
- Tiempo de recuperación aceptable ante desastres (RTO < 4 horas)
- Capacidad de operar durante eventos de fuerza mayor limitados

### 4.3 Comparación con Alternativas

**¿Por qué NO Tier II?**

Limitaciones inaceptables:
- Requiere apagados para mantenimiento mayor
- Ventanas de mantenimiento afectan productividad
- No cumple SLAs empresariales modernos (99.9%)
- Riesgo de pérdida de negocios durante mantenimiento
- Percepción negativa de clientes ante interrupciones

**¿Por qué NO Tier IV?**

Sobrecosto injustificado:
- Inversión 80-100% mayor que Tier III
- Costos operativos 50-60% superiores
- Complejidad operacional significativamente mayor
- Beneficio marginal: solo 1.2 horas menos de downtime anual
- Tiempo de implementación excesivo (18-24 meses)
- ROI difícil de justificar para la mayoría de negocios

### 4.4 Casos de Uso Ideales para Tier III

Este diseño Tier III es perfecto para:

**Sector Educativo:**
- Universidades con sistemas 24/7 (campus virtual, registro)
- Plataformas de e-learning con miles de usuarios
- Sistemas administrativos críticos

**Sector Comercial:**
- Empresas de e-commerce medianas y grandes
- Proveedores de servicios cloud regionales
- Plataformas SaaS B2B

**Sector Financiero:**
- Bancos regionales y cooperativas
- Procesadores de pagos
- Plataformas fintech

**Sector Gobierno:**
- Instituciones gubernamentales con servicios digitales
- Sistemas de información ciudadana
- Plataformas de trámites electrónicos

**Sector Tecnológico:**
- Proveedores de hosting y colocation
- Empresas de desarrollo de software
- Startups tecnológicas en crecimiento

### 4.5 Limitaciones Aceptadas

**Restricciones del Tier III que consideramos aceptables:**

- No tolerante a fallos múltiples simultáneos (requeriría Tier IV)
- Path pasivo no utilizado en operación normal (eficiencia energética)
- Posible breve interrupción ante combinación de fallo + mantenimiento simultáneo
- Downtime de 1.6 horas anuales vs 0.4 horas de Tier IV

Estas limitaciones son aceptables dado el perfil de riesgo y presupuesto de organizaciones típicas.

---

## 5. ESPECIFICACIONES DE HARDWARE

### 5.1 Servidores de Aplicación

**Modelo Principal:** Dell PowerEdge R750  
**Cantidad Total:** 6 unidades

**Especificaciones detalladas por servidor:**

**Procesamiento:**
- 2x Intel Xeon Gold 6338 (64 cores totales por servidor)
- Frecuencia base: 2.0 GHz, Turbo: 3.2 GHz
- Cache L3: 48MB por procesador
- TDP: 205W por procesador
- Soporte para AVX-512, AES-NI

**Memoria RAM:**
- Capacidad total: 256GB DDR4 ECC RDIMM
- Configuración: 16 módulos de 16GB
- Frecuencia: 3200 MHz
- Canales: 8 canales de memoria por procesador
- Protección: ECC con corrección de errores
- Capacidad máxima expansible: 2TB

**Almacenamiento Local:**
- 2x 960GB NVMe SSD (RAID 1 para sistema operativo)
  - Modelo: Dell PM1733
  - Velocidad lectura: 6,900 MB/s
  - Velocidad escritura: 4,200 MB/s
  - Endurance: 1 DWPD (Drive Writes Per Day)
  
- 4x 3.84TB NVMe SSD (RAID 10 para datos de aplicaciones)
  - Modelo: Dell PM1735
  - Velocidad lectura: 7,000 MB/s
  - Velocidad escritura: 4,000 MB/s
  - Endurance: 3 DWPD

**Controladora RAID:**
- Modelo: Dell PERC H755 Front
- Cache: 8GB con batería BBU
- Soporte RAID: 0, 1, 5, 6, 10, 50, 60
- Throughput: 12 Gb/s por puerto SAS

**Conectividad de Red:**
- 4x puertos 25GbE SFP28 (dual port cards)
- Chipset: Broadcom BCM57414
- Soporte para SR-IOV (virtualización de red)
- RDMA over Converged Ethernet (RoCE)
- Teaming y failover automático

**Fuentes de Poder:**
- 2x 1400W Titanium (96% eficiencia)
- Hot-plug redundantes
- Alimentación: 200-240VAC
- Cableado N+1 a PDUs duales

**Gestión Remota:**
- iDRAC9 Enterprise con dedicada 1GbE
- Consola remota HTML5 (sin Java)
- Power monitoring en tiempo real
- Sensor de temperatura y ventiladores
- Integración con Active Directory

**Dimensiones y Factor de Forma:**
- Altura: 2U (8.73 cm)
- Ancho: 48.26 cm (19" rack standard)
- Profundidad: 81.6 cm
- Peso: 28 kg (configurado)

**Distribución de Carga de Trabajo:**

Servidores 1-2: **Plataforma de Virtualización**
- VMware ESXi 8.0 hosts
- 40 VMs por host (80 VMs totales)
- Workloads mixtos de producción

Servidores 3-4: **Aplicaciones Empresariales**
- ERP (SAP, Microsoft Dynamics)
- CRM (Salesforce on-premise)
- Aplicaciones web personalizadas
- Middleware (Apache Tomcat, JBoss)

Servidores 5-6: **Bases de Datos**
- Microsoft SQL Server (clúster activo-pasivo)
- Oracle Database RAC
- PostgreSQL con replicación
- Redis/Memcached para caché

### 5.2 Almacenamiento Centralizado (SAN)

**Modelo:** Dell EMC PowerStore 3000T  
**Cantidad:** 2 unidades en configuración activo-activo

**Arquitectura del Sistema:**

**Controladoras:**
- 2x controladoras activo-activo por array
- Procesadores: Intel Xeon Scalable
- Memoria cache: 384GB por controladora (768GB total)
- Capacidad de procesamiento: 7 millones IOPS
- Latencia: <1ms promedio

**Capacidad de Almacenamiento:**
- Capacidad raw total: 200TB
- Capacidad efectiva: ~150TB (después de RAID y overhead)
- Expansión máxima: hasta 4PB

**Configuración de Discos:**

**Performance Tier (Tier 0):**
- 24x 3.84TB NVMe SSD
- Velocidad secuencial: 7,000/4,000 MB/s (R/W)
- IOPS: 1M por disco
- Uso: Bases de datos críticas, VMs hot

**Capacity Tier (Tier 1):**
- 48x 7.68TB SSD SATA
- Velocidad secuencial: 560/530 MB/s (R/W)
- IOPS: 98K por disco
- Uso: File storage, backups, archivos

**Esquema RAID:**
- RAID 6 para protección doble (tolera 2 fallos)
- Hot spares: 4 discos NVMe + 6 discos SATA
- Rebuild time: <2 horas por disco

**Conectividad:**

**Fibre Channel:**
- 8x puertos 32 Gb FC por controladora
- 16x puertos totales activos
- Conectividad a switches FC redundantes
- Multipathing con MPIO

**iSCSI:**
- 4x puertos 100GbE por controladora
- 8x puertos totales
- VLANs dedicadas para storage
- Jumbo frames habilitados (9000 MTU)

**Características Avanzadas:**

**Auto-Tiering Inteligente:**
- Movimiento automático de bloques entre tiers
- Análisis de patrones de acceso 24/7
- Optimización sin intervención manual
- Reporting de uso por tier

**Data Services:**
- Deduplicación inline (ratio típico 3:1)
- Compresión inline (ratio típico 2:1)
- Thin provisioning (sobre-asignación hasta 5:1)
- Space-efficient snapshots

**Protección de Datos:**
- Snapshots locales: cada 15 minutos
- Retención: 30 días local
- Replicación a sitio remoto (RPO 5 minutos)
- CloudIQ analytics predictivos

**Alta Disponibilidad:**
- Dual controllers active-active
- Cache mirroring entre controladoras
- Automatic failover <30 segundos
- Non-disruptive upgrades

### 5.3 Equipamiento de Red

#### 5.3.1 Switches Core (Núcleo de Red)

**Modelo:** Cisco Nexus 9364C  
**Cantidad:** 2 unidades (configuración activo-activo con vPC)

**Especificaciones Técnicas:**

**Puertos:**
- 64x puertos 100GbE QSFP28
- 4x puertos 400GbE QSFP-DD (upgrade path)
- Velocidades auto-negotiation: 10/25/40/50/100 GbE

**Performance:**
- Throughput total: 12.8 Tbps
- Capacidad de forwarding: 9.5 Bpps
- Latencia: <2 microsegundos (port-to-port)
- Buffer de paquetes: 32MB compartido

**Características de Capa 2:**
- VLANs: hasta 4096
- Spanning Tree: RSTP, MST
- VXLAN gateway support
- Link aggregation (LACP)

**Características de Capa 3:**
- Routing protocols: OSPF, BGP, EIGRP, IS-IS
- Virtual routing: VRF hasta 1000 instancias
- Multicast: PIM-SM, PIM-SSM
- IPv6 full support

**Alta Disponibilidad:**
- Virtual Port Channel (vPC)
- ISSU (In-Service Software Upgrade)
- Dual supervisors (redundancia)
- Hot-swappable fan trays y PSUs

**Gestión:**
- Cisco DCNM integration
- REST API programable
- Python scripting onboard
- Telemetry streaming

**Alimentación:**
- 4x fuentes 3000W Platinum
- Consumo típico: 1800W
- Configuración 2+2 redundante

#### 5.3.2 Switches de Distribución

**Modelo:** Cisco Catalyst 9300-48UXM  
**Cantidad:** 4 unidades (2 por path de distribución)

**Especificaciones:**

**Puertos de Acceso:**
- 48x puertos Multigigabit (100M/1G/2.5G/5G/10GbE)
- Auto-sensing NBASE-T
- PoE++: 60W por puerto (hasta 30W estándar)
- Presupuesto total PoE: 1100W

**Uplinks:**
- 4x puertos 40GbE QSFP+ (red uplinks a core)
- 4x puertos 100GbE QSFP28 (network module opcional)
- Bandwidth agregado: 880 Gbps

**Performance:**
- Throughput: 336 Gbps (full duplex)
- Forwarding rate: 250 Mpps
- Latencia: <5 microsegundos

**Stacking:**
- Cisco StackWise-480 (480 Gbps stack bandwidth)
- Hasta 8 switches por stack
- Single management plane

**Características Software:**
- Cisco DNA license incluida
- Software Defined Access (SDA)
- Encrypted Traffic Analytics
- MACsec encryption (802.1AE)

**Seguridad:**
- TrustSec SGT tagging
- 802.1X authentication
- Dynamic ARP inspection
- DHCP snooping
- Port security

**Alimentación:**
- 2x fuentes 1100W redundantes
- Hot-swappable
- Consumo típico: 450W

#### 5.3.3 Switches de Acceso (Top of Rack)

**Modelo:** Cisco Catalyst 9200L-48T-4G  
**Cantidad:** 8 unidades (distribuidos en racks de servidores)

**Especificaciones:**

**Puertos:**
- 48x puertos 1GbE RJ45 (10/100/1000)
- 4x puertos 10GbE SFP+ (uplinks)
- Auto-MDIX en todos los puertos

**Performance:**
- Throughput: 176 Gbps
- Forwarding: 130 Mpps
- Buffer de paquetes: 16MB

**Funcionalidades:**
- Layer 2 switching completo
- Static routing (32 rutas)
- VLANs: 1024
- Link aggregation: hasta 8 puertos

**Gestión:**
- Cisco Network Plug and Play
- Zero-touch provisioning
- USB console port
- Web GUI + CLI

**Alimentación:**
- 2x fuentes 350W redundantes
- Consumo típico: 120W

#### 5.3.4 Firewalls de Próxima Generación

**Modelo:** Fortinet FortiGate 1800F  
**Cantidad:** 2 unidades (High Availability activo-pasivo)

**Performance del Sistema:**

**Throughput:**
- Firewall: 480 Gbps
- IPS: 32 Gbps
- NGFW: 24 Gbps
- SSL Inspection: 18 Gbps
- VPN IPsec: 40 Gbps

**Capacidad:**
- Conexiones concurrentes: 90 millones
- Nuevas conexiones/seg: 3.5 millones
- Throughput de threat protection: 17 Gbps

**Interfaces:**
- 24x puertos 10GbE SFP+
- 8x puertos 40GbE QSFP+
- 2x puertos 100GbE QSFP28
- Bandwidth total: 1.2 Tbps

**Funcionalidades de Seguridad:**

**Next-Generation Firewall:**
- Application control (5000+ apps)
- User identity awareness
- SSL/TLS deep inspection
- Antivirus/antimalware (FortiGuard)

**Intrusion Prevention (IPS):**
- 10,000+ firmas actualizadas
- Zero-day threat protection
- FortiSandbox integration
- Custom IPS signatures

**Advanced Threat Protection:**
- AI/ML-based threat detection
- Botnet C&C blocking
- Advanced malware protection
- Threat intelligence feeds

**VPN:**
- IPsec site-to-site: 10,000 túneles
- SSL-VPN users: 20,000 concurrent
- Two-factor authentication

**SD-WAN:**
- Active-active WAN links
- Application-based routing
- WAN optimization
- Link quality monitoring

**Alta Disponibilidad:**
- Active-Passive cluster
- Session sync (stateful failover)
- Heartbeat cada 100ms
- Failover time: <1 segundo

**Gestión:**
- FortiManager (centralizado)
- FortiAnalyzer (logging/reporting)
- REST API completa
- CLI y GUI web

**Alimentación:**
- 4x fuentes 1200W AC redundantes
- Consumo típico: 800W

#### 5.3.5 Routers de Borde WAN

**Modelo:** Cisco ISR 4461  
**Cantidad:** 2 unidades (redundancia activo-pasivo)

**Especificaciones:**

**Performance:**
- Throughput: hasta 10 Gbps
- Paquetes por segundo: 3 Mpps
- Conexiones concurrentes: 4 millones

**Interfaces Integradas:**
- 4x puertos 1GbE RJ45/SFP combo
- 4x puertos 10GbE SFP+
- 2x módulos de red Network Interface Module

**Módulos WAN Instalados:**
- 2x puertos 100GbE QSFP28 (carrier uplinks)
- 2x puertos 10GbE SFP+ (backup links)
- Serial interfaces para legado (opcional)

**Memoria y Procesamiento:**
- CPU: Multi-core 2.2 GHz
- DRAM: 32GB
- Flash: 16GB
- Packet buffer: 2GB

**Funcionalidades:**

**Routing:**
- Protocolos: BGP, OSPF, EIGRP, RIP, IS-IS
- Policy-based routing
- Route filtering y redistribution
- BFD (Bidirectional Forwarding Detection)

**QoS (Quality of Service):**
- Classification y marking
- Policing y shaping
- Priority queuing
- WRED (Weighted Random Early Detection)

**Seguridad:**
- Zone-based firewall
- IPsec VPN (hasta 2000 túneles)
- Cisco Threat Defense (licencia)
- URL filtering

**Alta Disponibilidad:**
- HSRP/VRRP para gateway redundancy
- Dual-homed ISP connections
- BFD para detección rápida de fallos
- Event dampening

**Gestión:**
- Cisco DNA Center integration
- NETCONF/YANG support
- Embedded Event Manager (scripting)
- SNMP v2/v3

**Alimentación:**
- 2x fuentes 450W AC redundantes
- Consumo típico: 250W

### 5.4 Infraestructura Eléctrica

#### 5.4.1 Sistema UPS (Uninterruptible Power Supply)

**Modelo:** Schneider Electric Galaxy VX 500kVA  
**Cantidad:** 2 unidades (configuración N+1)

**Especificaciones de Potencia:**

**Capacidad:**
- Potencia aparente: 500 kVA por unidad
- Potencia real: 450 kW por unidad (factor 0.9)
- Capacidad total sistema: 1000 kVA / 900 kW
- Capacidad efectiva (N+1): 500 kVA / 450 kW

**Eficiencia Energética:**
- Modo Online (Double Conversion): 97%
- Modo ECO: hasta 99%
- Modo Energy Saver: 99%
- Certificación Energy Star

**Tecnología:**
- Topología: Online double-conversion
- Tecnología IGBT (Insulated Gate Bipolar Transistor)
- PFC (Power Factor Correction) activo >0.99
- THDi <3% (distorsión armónica)

**Características Eléctricas:**

**Entrada:**
- Voltaje nominal: 480V trifásico
- Rango: 380-480V ±20%
- Frecuencia: 50/60 Hz ±10%
- Corriente máxima: 750A por unidad

**Salida:**
- Voltaje: 480V/208V trifásico
- Regulación voltaje: ±1%
- Frecuencia: 50/60 Hz ±0.01%
- Factor de potencia: 0.9 lagging a 1.0 leading

**Autonomía:**
- Tiempo de respaldo: 15 minutos a carga plena
- Extensible con baterías adicionales: hasta 30 minutos
- Tiempo de transferencia: 0ms (online)
- Tiempo de recarga: 3 horas al 90%

**Protecciones:**
- Sobrecarga: hasta 150% por 1 minuto
- Cortocircuito: protección electrónica
- Sobre-temperatura: alarma y shutdown
- Bypass automático ante fallo interno

**Redundancia y Disponibilidad:**
- Configuración paralelo redundante N+1
- Hot-swap de módulos de potencia
- Bypass manual y automático
- Mantenimiento sin interrupción

**Gestión y Monitoreo:**
- Display LCD táctil 7"
- Network Management Card integrada
- SNMP, HTTP, Modbus, BACnet
- Integración con BMS (Building Management System)
- Alarmas configurables vía email/SMS

**Dimensiones y Ambiente:**
- Ancho: 600mm
- Profundidad: 1200mm
- Alto: 1950mm
- Peso: 950 kg (sin baterías)
- Temperatura operación: 0-40°C
- Altitud máxima: 1000m sin derating

#### 5.4.2 Banco de Baterías

**Modelo:** Schneider Electric Galaxy VX Battery Cabinet  
**Cantidad:** 8 gabinetes (4 por UPS)

**Especificaciones de Baterías:**

**Tipo de Batería:**
- Tecnología: VRLA (Valve Regulated Lead Acid)
- Diseño: AGM (Absorbed Glass Mat)
- Libre de mantenimiento
- Selladas y a prueba de derrames

**Capacidad:**
- Voltaje nominal: 12V por celda
- Capacidad: 200Ah por string a 25°C
- Strings por gabinete: 10
- Capacidad total sistema: 1600Ah

**Vida Útil:**
- Expectativa diseño: 10 años a 25°C
- Ciclos: 200 ciclos al 80% DOD
- Temperatura óptima: 20-25°C
- Cada 10°C adicionales reduce vida 50%

**Características:**
- Monitoreo individual por string
- Sensor de temperatura por gabinete
- Desconexión automática bajo voltaje
- Ventilación forzada con control térmico

**Dimensiones por Gabinete:**
- Ancho: 600mm
- Profundidad: 1200mm
- Alto: 1950mm
- Peso: 800 kg (con baterías)

**Mantenimiento:**
- Inspección visual: mensual
- Prueba de carga: semestral
- Reemplazo preventivo: cada 8-10 años
- Reciclaje al final de vida útil

#### 5.4.3 Generadores Diésel de Emergencia

**Modelo:** Caterpillar C18 ACERT  
**Cantidad:** 2 unidades (configuración N+1)

**Especificaciones de Motor:**

**Potencia:**
- Potencia standby: 600 kVA / 480 kW
- Potencia prime: 550 kVA / 440 kW
- Factor de potencia: 0.8
- Reserva total (N+1): 480 kW disponible

**Motor:**
- Modelo: Cat C18 ACERT
- Cilindros: 6 en línea, 4 tiempos
- Desplazamiento: 18.1 litros
- Aspiración: Turbocargado con aftercooler
- RPM: 1800 (60 Hz)

**Sistema Eléctrico:**

**Generador/Alternador:**
- Marca: Caterpillar SR5
- Voltaje salida: 480V trifásico
- Regulación voltaje: ±1%
- Eficiencia: 95%

**Arranque:**
- Baterías: 4x 12V 200Ah libres mantenimiento
- Motor arranque: 24V heavy-duty
- Tiempo arranque: <10 segundos
- Intentos automáticos: 3

**Combustible:**

**Sistema de Combustible:**
- Tanque base integrado: 800 litros
- Tanque día adicional: 1200 litros
- Capacidad total: 2000 litros por generador
- Material: Acero con recubrimiento anticorrosión

**Consumo:**
- Consumo 100% carga: 110 L/h
- Consumo 75% carga: 85 L/h
- Consumo 50% carga: 60 L/h
- Autonomía a 50% carga: 48 horas continuas

**Sistema de Transferencia:**

**ATS (Automatic Transfer Switch):**
- Marca: ASCO Series 7000
- Capacidad: 800A por switch
- Tiempo transferencia: <10 segundos
- Modos: Automático, manual, test

**Secuencia de Operación:**
1. Detección fallo red: <2 segundos
2. Señal arranque generador: inmediata
3. Estabilización generador: 8-10 segundos
4. Transferencia de carga: 2 segundos
5. Tiempo total: <15 segundos

**Sistemas de Soporte:**

**Enfriamiento:**
- Sistema: Radiador con ventilador controlado
- Capacidad radiador: 50°C ambiente
- Bomba agua: Mecánica direct-driven
- Termostato: 82-88°C

**Lubricación:**
- Capacidad aceite: 52 litros
- Filtro: Cartucho desechable
- Intervalo cambio: 500 horas

**Control y Monitoreo:**
- Panel control: EMCP 4.2 (Cat)
- Display: LCD color 5"
- Protecciones: 30+ parámetros monitoreados
- Comunicación: Ethernet, Modbus, CANbus

**Parámetros Monitoreados:**
- Voltaje y corriente (3 fases)
- Frecuencia eléctrica
- Temperatura motor y refrigerante
- Presión aceite
- Nivel combustible
- Horas operación
- Alarmas y fallas

**Sistema de Escape:**
- Silenciador: Crítico grado residencial
- Nivel ruido: 75 dBA @ 7 metros
- Material: Acero inoxidable
- Sistema evacuación al exterior

**Dimensiones y Peso:**
- Largo: 4800mm
- Ancho: 1800mm
- Alto: 2400mm
- Peso seco: 4200 kg
- Peso operativo: 5500 kg

**Instalación:**
- Base: Concreto reforzado con aislamiento vibraciones
- Ventilación: Mínimo 3 cambios aire/minuto
- Distancia muros: 1.5m mínimo
- Certificaciones: UL 2200, NFPA 110 Level 1

**Mantenimiento Programado:**
- Inspección semanal: Visual y niveles
- Prueba arranque: Semanal 30 minutos sin carga
- Prueba carga: Mensual 1 hora con 30% carga
- Servicio menor: 250 horas
- Servicio mayor: 500 horas
- Overhaul motor: 12,000 horas

#### 5.4.4 PDUs (Power Distribution Units)

**Modelo:** APC Metered Rack PDU 2G (AP8959)  
**Cantidad:** 32 unidades (2 por cada uno de los 16 racks)

**Especificaciones Eléctricas:**

**Entrada:**
- Voltaje: 208V trifásico
- Corriente nominal: 60A
- Potencia máxima: 17.3 kW
- Plug entrada: IEC 60309 3P+N+E

**Salidas:**
- 36x tomacorrientes IEC C13 (equipos estándar)
- 6x tomacorrientes IEC C19 (equipos alta potencia)
- Total: 42 outlets por PDU
- 84 outlets por rack (2 PDUs)

**Medición y Monitoreo:**

**Parámetros Medidos:**
- Corriente (Amperes) por fase en tiempo real
- Voltaje (Volts) por fase
- Potencia activa (kW) total y por fase
- Potencia aparente (kVA)
- Factor de potencia
- Energía acumulada (kWh)

**Precisión Medición:**
- Corriente: ±1%
- Voltaje: ±1%
- Potencia: ±2%
- Frecuencia muestreo: 1 segundo

**Gestión y Conectividad:**

**Interfaz de Red:**
- Puerto Ethernet 10/100 Mbps
- Dirección IP: Estática o DHCP
- Protocolos: SNMPv1/v2c/v3, HTTP, HTTPS, Telnet, SSH
- Integración: VMware, Microsoft SCOM, Nagios

**Características Software:**
- Web interface intuitiva
- CLI por SSH/Telnet
- API REST para automatización
- Datalog exportable CSV

**Alertas y Notificaciones:**
- Email alerts (hasta 4 destinatarios)
- SNMP traps
- Syslog messages
- Umbrales configurables por outlet

**Tipos de Alarmas:**
- Sobrecarga inminente (>80% capacidad)
- Sobrecarga crítica (>90% capacidad)
- Bajo voltaje
- Sobre voltaje
- Pérdida comunicación
- Cambio de estado outlet

**Características Físicas:**

**Diseño:**
- Montaje vertical en rack (0U)
- Material: Aluminio extruido
- Color: Negro
- Outlets orientables

**Dimensiones:**
- Alto: 2032mm (compatible 42U rack)
- Ancho: 51mm
- Profundidad: 44mm
- Cable entrada: 3 metros

**Seguridad:**
- Breaker magnético-térmico por fase
- Surge protection 480 Joules
- Reset manual breaker
- Certificaciones: UL, cUL, CE

**Distribución en Racks:**
- PDU A: Conectado a UPS Path A
- PDU B: Conectado a UPS Path B
- Servidores: Dual PSU conectado a ambas PDUs
- Red: Equipos críticos en ambas PDUs

### 5.5 Sistema de Enfriamiento HVAC

#### 5.5.1 Unidades de Precisión InRow

**Modelo:** Schneider Electric InRow ACRC301  
**Cantidad:** 6 unidades (2 por cada pasillo frío, configuración N+1)

**Capacidad de Enfriamiento:**

**Potencia:**
- Capacidad enfriamiento sensible: 33 kW por unidad
- Capacidad total: 198 kW (6 unidades)
- Capacidad efectiva (N+1): 165 kW
- Ratio enfriamiento: 2.5-3 kW por rack

**Eficiencia:**
- COP (Coefficient of Performance): >3.0
- EER (Energy Efficiency Ratio): 10.2 BTU/W
- Consumo energético: 11 kW por unidad

**Especificaciones Técnicas:**

**Caudal de Aire:**
- Volumen: 5000 m³/h por unidad
- Velocidad variable mediante VFD
- Presión estática: 250 Pa
- Dirección: Horizontal hacia pasillo frío

**Refrigerante:**
- Tipo: R410A (HFC)
- Carga: 8.5 kg por unidad
- GWP: 2088 (requiere gestión responsable)
- Presión operación: 12-28 bar

**Rango Operativo:**

**Temperatura:**
- Set point configurable: 18-27°C
- Precisión control: ±1°C
- Rango ambiente: 15-35°C
- Temperatura retorno máxima: 40°C

**Humedad:**
- Rango operativo: 20-80% RH
- Set point recomendado: 45-55% RH
- Control: Deshumidificación activa
- Humidificación: Opcional (no incluida)

**Componentes Principales:**

**Compresor:**
- Tipo: Scroll hermético
- Capacidad: Variable con inverter
- Arranque: Soft-start
- Protecciones: Térmica, presión, corriente

**Ventiladores:**
- Cantidad: 6 ventiladores EC (Electronically Commutated)
- Control: PWM individual por ventilador
- Velocidad: 0-100% variable
- Redundancia: N+1 (continúa operando con fallo de 1 fan)

**Evaporador:**
- Tipo: Aletas aluminio / tubos cobre
- Válvula expansión: Electrónica (EEV)
- Sensor: Temperatura y presión

**Condensador:**
- Tipo: Enfriado por agua (chilled water)
- Conexión: 1" NPT entrada/salida
- Caudal agua: 10 L/min
- ΔT agua: 5°C

**Sistema de Control:**

**Controlador:**
- Modelo: Schneider Electric EcoStruxure
- Procesador: ARM Cortex
- Display: LCD táctil 7"
- Algoritmo: PID avanzado con machine learning

**Sensores:**
- 4x temperatura supply/return (redundantes)
- 2x humedad relativa
- 2x presión diferencial
- 1x caudal agua
- Vibración compresor
- Corriente eléctrica

**Conectividad:**
- Ethernet: 10/100 Mbps
- Protocolos: Modbus TCP/RTU, BACnet IP/MSTP, SNMP
- Integración BMS (Building Management System)
- API REST para automatización

**Características Inteligentes:**

**Auto-Adaptación:**
- Aprende patrones de carga térmica
- Ajusta velocidad ventiladores proactivamente
- Optimiza arranques compresor
- Minimiza consumo energético

**Redundancia y Failover:**
- Detección fallo unidad adyacente
- Aumento automático capacidad
- Rotación equitativa horas operación
- Lead-lag scheduling

**Instalación y Montaje:**

**Ubicación:**
- Posición: Entre racks en pasillo frío
- Ancho: 300mm (ocupa espacio de 1/3 rack)
- Distribución: 1 unidad cada 3-4 racks
- Orientación: Descarga frontal a pasillo

**Dimensiones:**
- Ancho: 300mm
- Profundidad: 1200mm (alineado con racks)
- Alto: 2000mm (42U)
- Peso: 280 kg

**Conexiones:**
- Eléctrica: 208V 3-phase, 32A
- Agua chilled: 1" NPT
- Drenaje condensado: 3/4" NPT
- Red: RJ45 Cat6

**Mantenimiento:**

**Rutinas Programadas:**
- Inspección filtros: Mensual
- Limpieza evaporador: Trimestral
- Revisión refrigerante: Semestral
- Verificación sensores: Semestral
- Mantenimiento preventivo completo: Anual

**Alertas Predictivas:**
- Degradación filtros (presión diferencial)
- Fatiga compresor (horas operación)
- Pérdida eficiencia (EER decreciente)
- Fugas refrigerante (presión baja)

#### 5.5.2 Chillers (Planta Enfriadora Central)

**Modelo:** Carrier AquaEdge 19DV  
**Cantidad:** 2 unidades (configuración N+1)

**Capacidad Térmica:**

**Potencia Enfriamiento:**
- Capacidad nominal: 500 kW (142 RT) por unidad
- Capacidad total: 1000 kW (284 RT)
- Capacidad efectiva (N+1): 500 kW
- Cobertura: 6 unidades InRow + reserva

**Eficiencia Energética:**

**Indicadores:**
- IPLV (Integrated Part Load Value): 0.45 kW/ton
- COP nominal: 6.2 (a condiciones AHRI 550/590)
- EER: 21.2 BTU/W·h
- Part-load efficiency: Hasta COP 8.0 @ 30% carga

**Certificaciones:**
- AHRI Certified
- LEED v4 points eligible
- ASHRAE 90.1 compliant
- Energy Star partner

**Especificaciones Técnicas:**

**Compresor:**
- Tipo: Centrífugo de levitación magnética
- Marca: Carrier OptiSpeed
- Velocidad: Variable 12,000-28,000 RPM
- Etapas: 2 stages
- Tecnología: Oil-free bearings

**Ventajas Levitación Magnética:**
- Cero fricción = mayor eficiencia
- Sin lubricación = sin contaminación refrigerante
- Menor vibración y ruido
- Vida útil >30 años
- Arranques ilimitados sin desgaste

**Refrigerante:**
- Tipo: HFO-1234ze (muy bajo GWP)
- GWP: <1 (vs 2088 del R410A)
- ODP: 0 (no daña capa ozono)
- Carga: 280 kg por unidad
- Cumple regulaciones futuras (F-Gas Regulation)

**Evaporador:**

**Diseño:**
- Tipo: Shell & tube (casco y tubos)
- Material tubos: Cobre
- Material casco: Acero al carbón
- Conexiones: 4" NPT entrada/salida

**Circuito Agua Fría:**
- Caudal nominal: 24 m³/h
- Temperatura entrada: 12°C
- Temperatura salida: 7°C
- ΔT: 5°C
- Presión máxima: 10 bar

**Condensador:**

**Tipo:** Enfriado por agua (water-cooled)

**Circuito Agua Condensación:**
- Caudal nominal: 36 m³/h
- Temperatura entrada: 30°C
- Temperatura salida: 35°C
- ΔT: 5°C
- Presión máxima: 10 bar

**Torre de Enfriamiento:**
- Modelo: Baltimore Aircoil VTI (incluida)
- Capacidad: 600 kW por torre
- Ventiladores: VFD para eficiencia
- Tratamiento agua: Sistema automático

**Free Cooling:**

**Sistema Economizer:**
- Activación: Temperatura ambiente <15°C
- Método: Waterside economizer con válvulas modulantes
- Ahorro energético: Hasta 70% en meses fríos
- Control: Automático por temperatura exterior

**Ahorro Anual Estimado:**
- Guatemala (clima templado): 20-30% reducción kWh
- Meses octubre-febrero: Mayor beneficio
- ROI free cooling: 3-4 años

**Sistema de Control:**

**Panel de Control:**
- Controlador: Carrier i-Vu Pro
- Display: Touchscreen 10" color
- Idiomas: Español, inglés, otros
- Interfaz: Gráfica intuitiva

**Monitoreo en Tiempo Real:**
- Temperaturas: Entrada/salida evaporador y condensador
- Presiones: Alta y baja refrigerante
- Caudales: Agua fría y condensación
- Potencia: kW consumidos y kW térmicos
- Eficiencia: COP instantáneo
- Alarmas: 50+ puntos monitoreados

**Conectividad:**
- Ethernet: 10/100/1000 Mbps
- Protocolos: BACnet IP, Modbus TCP, LonWorks
- SNMP: v2c y v3
- Cloud: Carrier Abound (opcional)

**Optimización Automática:**
- Load sharing entre 2 unidades
- Lead-lag rotation (rotación equitativa)
- Staged capacity control (8 pasos modulación)
- Predictive algorithms (temperatura exterior forecast)

**Protecciones y Seguridad:**

**Protecciones Compresor:**
- Temperatura descarga alta
- Presión diferencial alta
- Sobre-corriente motor
- Fallo levitación magnética
- Vibración excesiva

**Protecciones Sistema:**
- Flujo agua bajo (flow switch)
- Temperatura anticongelamiento
- Presión agua baja
- Pérdida alimentación eléctrica
- Fallo comunicación

**Sistema Eléctrico:**

**Alimentación:**
- Voltaje: 480V trifásico 60Hz
- Corriente nominal: 180A
- Potencia conectada: 95 kW
- Factor potencia: >0.95

**Arranque:**
- Tipo: Soft-starter integrado
- Corriente arranque: <1.5x nominal
- Tiempo aceleración: 30 segundos

**Componentes Eléctricos:**
- VFD (Variable Frequency Drive): ABB ACS880
- Contactores: Siemens 3RT
- Protecciones: Disyuntores termomagnéticos
- Cableado: Calibre según NEC (National Electrical Code)

**Instalación Física:**

**Ubicación:**
- Sala mecánica independiente (20m²)
- Piso reforzado (carga 1500 kg/m²)
- Altura libre: 3.5m mínimo
- Ventilación: Natural + mecánica forzada

**Dimensiones por Chiller:**
- Largo: 3200mm
- Ancho: 1800mm
- Alto: 2400mm
- Peso operativo: 2800 kg

**Espacios Mantenimiento:**
- Frontal: 1.5m mínimo
- Lateral: 1.0m mínimo
- Superior: 2.0m para extracción compresor

**Mantenimiento:**

**Rutinas Preventivas:**
- Inspección visual: Semanal
- Verificación parámetros: Semanal
- Limpieza condensador: Trimestral
- Análisis refrigerante: Anual
- Inspección compresor: Bianual
- Overhaul completo: 10 años

**Vida Útil Esperada:**
- Compresor: 30+ años
- Heat exchangers: 25 años
- Controles: 15 años (actualizables)
- Estructura: 30+ años

#### 5.5.3 Sistema de Contención de Pasillos

**Modelo:** Vertiv SmartAisle  
**Cantidad:** 3 pasillos contenidos (configuración Cold Aisle Containment)

**Diseño y Estructura:**

**Dimensiones por Pasillo:**
- Largo: 12 metros (longitud de fila racks)
- Ancho: 1.2 metros (suficiente para acceso)
- Alto: 3.0 metros (desde piso elevado hasta techo caída)
- Volumen contenido: 43.2 m³ por pasillo

**Materiales:**

**Paneles Laterales:**
- Material: Policarbonato transparente 8mm
- Propiedades: Alta resistencia impacto
- Transmisión luz: >85%
- Retardante al fuego: UL94 V-2
- Marco: Aluminio anodizado

**Techo:**
- Material: Paneles modulares policarbonato
- Tipo: Desmontables para acceso superior
- Sellado: Burletes anti-bypass
- Iluminación: LEDs integrados 500 lux

**Puertas de Acceso:**

**Especificaciones:**
- Cantidad: 2 por pasillo (extremos)
- Tipo: Corredizas automáticas
- Ancho: 1000mm
- Activación: Sensor movimiento infrarrojo
- Velocidad apertura: 0.5 m/s
- Tiempo auto-cierre: 5 segundos ajustable

**Seguridad Puertas:**
- Sensor anti-aplastamiento
- Override manual (push bar)
- Apertura emergencia: Automática con alarma incendio
- Transparencia: Visual completa

**Beneficios de Contención:**

**Eficiencia Térmica:**
- Separación total aire frío/caliente
- Eliminación bypass mixing
- Aumento eficiencia HVAC: 40%
- Reducción PUE: 2.0 → 1.5

**Cálculo Ahorro:**
```
Sin contención:
- Consumo HVAC: 165 kW
- PUE: 2.0

Con contención:
- Consumo HVAC: 100 kW
- PUE: 1.5
- Ahorro: 65 kW = $45,000/año
```

**Temperatura Uniforme:**
- Variación antes: ±8°C entre racks
- Variación después: ±2°C
- Hot spots eliminados
- Mayor predictibilidad

**Presión Diferencial:**
- Pasillo frío: Presión positiva +15 Pa
- Pasillo caliente: Presión negativa -10 Pa
- Previene recirculación aire caliente

**Monitoreo y Control:**

**Sensores Instalados:**
- 12x sensores temperatura (4 por pasillo)
  - Ubicación: Top, middle, bottom de pasillo
  - Precisión: ±0.5°C
  - Comunicación: Modbus RTU

- 3x sensores presión diferencial
  - Rango: -50 a +50 Pa
  - Alarma: Si ΔP <5 Pa (pérdida contención)

- 3x sensores humedad relativa
  - Rango: 0-100% RH
  - Precisión: ±3%

**Panel de Control:**
- Display: LCD 7" por pasillo
- Visualización: Temps en tiempo real, estado puertas
- Alarmas: Visual y sonora
- Integración: BMS vía Ethernet

**Instalación y Montaje:**

**Anclaje:**
- Piso: Atornillado a piso elevado reforzado
- Techo: Suspendido de estructura techo técnico
- Laterales: Anclaje a marcos de racks

**Sellado:**
- Juntas: Burletes espuma cerrada
- Piso: Cepillos brush seal bajo racks
- Techo: Sellado perímetro completo
- Puertas: Cierre hermético magnético

**Acceso Cableado:**

**Pasamuros:**
- Ubicación: Cada 3 metros
- Tamaño: 200mm x 150mm
- Sellado: Brush grommets
- Para cables: Eléctrico y datos

**Mantenimiento:**

**Limpieza:**
- Paneles: Trimestral con paño microfibra
- Puertas: Lubricación guías semestral
- Sensores: Calibración anual
- Sellos: Inspección trimestral

**Normativas:**
- ASHRAE TC 9.9 compliant
- NFPA 75 fire safety
- Seismic rated Zone 4
- ADA accessible

### 5.6 Racks y Gabinetes

**Modelo:** APC NetShelter SX 42U 750mm x 1070mm  
**Cantidad:** 16 racks en total

**Especificaciones Generales:**

**Dimensiones:**
- Altura: 42U (2000mm = 2 metros)
- Ancho externo: 750mm
- Profundidad externa: 1200mm
- Profundidad útil: 1070mm
- Ancho interno: 600mm (19" EIA-310)

**Capacidad de Carga:**
- Carga estática máxima: 1360 kg
- Carga dinámica: 1135 kg
- Distribución: Uniforme sobre rieles
- Factor seguridad: 3:1

**Construcción:**

**Material:**
- Marco: Acero laminado en frío 14-16 gauge
- Acabado: Pintura epóxica negra texturizada
- Resistencia: Corrosión, rayones
- Espesor paredes: 2mm

**Puertas:**

**Puerta Frontal:**
- Tipo: Perforada 64% área abierta
- Material: Acero perforado
- Apertura: 180° reversible (izq o der)
- Cerradura: Manija con llave (2 llaves)
- Ventilación: 1200 CFM por rack

**Puerta Trasera:**
- Tipo: Doble puerta perforada split 64%
- Apertura: Cada hoja 115°
- Cerradura: Independiente por hoja
- Opción: Removible completamente

**Paneles Laterales:**
- Tipo: Sólidos removibles
- Fijación: Sin herramientas (QuickLatch)
- Acceso: Rápido para cableado/mantenimiento
- Opcionales: Perforados para más airflow

**Ventilación y Enfriamiento:**

**Flujo de Aire:**
- Diseño: Front-to-back airflow
- Área perforación: 64% (óptimo balance seguridad/flujo)
- Compatible: Hot aisle/cold aisle
- Puertas: Alto flujo con baja restricción

**Base y Techo:**

**Plinto Base:**
- Altura: 100mm
- Tipo: Perforado para cables desde piso
- Ajuste: Niveladores roscados ±20mm
- Capacidad: Soporta 1360 kg

**Techo:**
- Tipo: Perforado (opcional sólido)
- Apertura: 60% para cables superiores
- Brush strip: Sellado perímetro contención
- Montaje: Fan trays opcionales (no incluidos)

**Gestión de Cables:**

**Rieles Verticales:**
- Ubicación: Ambos lados internos
- Ancho: 150mm por lado
- Material: Acero con ganchos plásticos
- Capacidad: 50 kg por riel

**Organizadores Horizontales:**
- Cantidad: 6 unidades 1U
- Ubicación: Estratégica entre equipos
- Tipo: Finger duct con tapa
- Apertura: Frontal para acceso rápido

**Anillos Pasamuros:**
- Cantidad: 8 (top) + 4 (bottom)
- Diámetro: 80mm
- Material: Plástico con brush
- Sellado: Cierre contención

**Rieles de Montaje:**

**Rieles Ajustables:**
- Tipo: ToolLess square-hole
- Ajuste profundidad: Cada 25mm
- Rango: 610-1070mm
- Marcado: Numeración 1U-42U

**Accesorios Montaje:**
- Cage nuts: No requeridos
- Instalación: Push-in sin herramientas
- Compatibilidad: EIA-310-D, IEC 60297
- Peso soportado: 68 kg por par rieles

**PDUs Integrados:**
- Montaje: Vertical 0U (2 PDUs por rack)
- Ubicación: Posterior izquierdo y derecho
- Espacio: No consume Us del rack
- Cableado: Routing interno

**Monitoreo Ambiental:**

**NetBotz Rack Monitor 450:**
- Sensores integrados por rack:
  - Temperatura (2 puntos: top + middle)
  - Humedad relativa (1 sensor)
  - Puertas abiertas (4 contactos magnéticos)
  - Movimiento PIR (detección intrusión)

**Alertas:**
- Email: Hasta 6 destinatarios
- SNMP traps: V1/V2c/V3
- Syslog: Servidor central
- Display: Local LCD con estado

**Umbrales Configurables:**
- Temperatura warning: 25°C
- Temperatura critical: 30°C
- Humedad low: 30% RH
- Humedad high: 70% RH

**Seguridad Física:**

**Control Acceso:**
- Cerraduras: Llave mecánica (estándar)
- Upgrade disponible: Cerradura electrónica RFID
- Sistema: Registro eventos acceso
- Integración: Panel acceso Data Center

**Colores Identificación:**
- Marco: Negro RAL 9005
- Etiquetas: Blancas magnéticas
- Código barras: Asset tracking

**Distribución de los 16 Racks:**

**Zona 1 - Servidores de Producción (6 racks):**
- Rack 1-2: Servidores virtualización
- Rack 3-4: Servidores aplicaciones
- Rack 5-6: Servidores bases de datos
- Densidad: 8-10 kW por rack

**Zona 2 - Storage y Networking (4 racks):**
- Rack 7-8: SAN storage arrays
- Rack 9-10: Switches core y distribución
- Densidad: 5-7 kW por rack

**Zona 3 - Seguridad y Gestión (4 racks):**
- Rack 11-12: Firewalls y routers
- Rack 13-14: Sistemas monitoreo y backup
- Densidad: 3-5 kW por rack

**Zona 4 - Contingencia y Desarrollo (2 racks):**
- Rack 15: Equipos desarrollo/pruebas
- Rack 16: Espacio reserva expansión
- Densidad: 2-4 kW por rack

**Layout Físico (Hot Aisle / Cold Aisle):**

```
Vista Superior:

Pared Norte
═══════════════════════════════════════════════
║  [AC] ❄️ COLD AISLE ❄️ [AC]                ║
║  [R1][R2][R3][R4][R5][R6]                   ║
║       🔥 HOT AISLE 🔥                        ║
║  [R7][R8][R9][R10]                          ║
║  [AC] ❄️ COLD AISLE ❄️                      ║
║  [R11][R12][R13][R14][R15][R16]             ║
║       🔥 HOT AISLE 🔥                        ║
Pared Sur
═══════════════════════════════════════════════

R = Rack
AC = Aire Acondicionado InRow
```

**Costo Aproximado:**
- Rack NetShelter SX 42U: $2,500 USD por unidad
- PDUs (2 por rack): $800 USD
- NetBotz monitor: $600 USD
- Accesorios gestión cables: $300 USD
- **Total por rack: $4,200 USD**
- **16 racks: $67,200 USD**

**Tiempo Instalación:**
- Desempaque y ensamble: 2 horas/rack
- Nivelación y anclaje: 1 hora/rack
- Instalación PDUs: 1 hora/rack
- Cableado y etiquetado: 2 horas/rack
- **Total: 6 horas por rack**
- **16 racks: 96 horas (12 días laborales con 2 técnicos)**

---

## 6. ESPECIFICACIONES DE SOFTWARE

### 6.1 Virtualización e Hipervisor

#### 6.1.1 VMware vSphere 8.0 Enterprise Plus

**Licencias:** 12 procesadores (6 servidores x 2 CPUs)

**Componentes Principales:**

**ESXi 8.0 (Hipervisor):**
- Tipo: Bare-metal tipo 1
- Tamaño: 8 GB instalación
- Memoria mínima: 8GB RAM
- Arquitectura: 64-bit únicamente
- Boot: USB, SD card, o disco local

**Características del Hipervisor:**
- Max VMs por host: 1024
- Max vCPUs por VM: 768
- Max RAM por VM: 24TB
- Max hosts en cluster: 96
- Max VMs en cluster: 8000

**vCenter Server 8.0:**
- Plataforma: Appliance Linux (VCSA)
- Deployment: OVF sobre ESXi
- Database: PostgreSQL embebida
- RAM requerida: 24GB mínimo
- Storage: 600GB

**Funcionalidades Core:**

**vMotion:**
- Migración VMs en caliente (live)
- Sin downtime de aplicaciones
- Requisitos: Shared storage, vSwitch compatible
- Tiempo migración: 1-5 minutos típico
- Uso: Balance carga, mantenimiento hosts

**Storage vMotion:**
- Migración storage sin downtime
- Entre datastores diferentes
- Cambio formato disco en movimiento
- Tiempo: Dependiente tamaño VM

**DRS (Distributed Resource Scheduler):**
- Balance automático carga CPU/RAM
- vMotion automático según reglas
- Affinity/Anti-affinity rules
- Resource pools con prioridades
- Predictive DRS con vROps

**HA (High Availability):**
- Failover automático ante fallo host
- Detección fallo: <15 segundos
- Restart VMs: 1-3 minutos
- Admission control: Garantiza recursos
- Application monitoring: Restart app si falla

**Fault Tolerance (FT):**
- Protección cero-downtime
- VM secundaria sincronizada lockstep
- Failover instantáneo (<1 segundo)
- Limitación: hasta 8 vCPUs por VM
- Uso: Aplicaciones ultra-críticas

**vSAN (Virtual SAN):**
- Storage distribuido definido por software
- Pooling discos locales servidores
- Políticas flexibles (RAID 1, 5, 6)
- Caché NVMe + capacidad SATA/SAS
- Deduplicación y compresión

**NSX-T Data Center:**
- Virtualización red completa
- Micro-segmentación
- Firewall distribuido
- Load balancing
- VPN, NAT, routing L2-L7

**vSphere Replication:**
- Replicación asíncrona VMs
- RPO desde 15 minutos
- Compresión y deduplicación
- Destino: Otro site o cloud
- Disaster recovery integrado

**Licenciamiento:**
- Modelo: Per-processor
- Soporte: Production 24x7
- Actualizaciones: Incluidas
- Costo aproximado: $6,000 USD/proc
- **Total 12 procs: $72,000 USD**

### 6.2 Sistemas Operativos

#### 6.2.1 Windows Server 2022 Datacenter

**Licencias:** 20 núcleos físicos (mínimo 16 cores por licencia)

**Ediciones:**
- Datacenter: Virtualización ilimitada
- GUI o Server Core (sin interfaz)
- Licenciamiento: Per-core model

**Roles y Servicios Implementados:**

**Active Directory Domain Services:**
- Controladores dominio: 2 VMs (redundancia)
- Forest functional level: 2022
- Sites: 1 principal + 1 DR
- Usuarios: Hasta 10,000
- Políticas grupo (GPOs): Seguridad, despliegue

**DNS Server:**
- Zonas: Primaria y secundaria
- Integración: AD-integrated zones
- DNSSEC: Habilitado
- Forwarding: A DNS ISP
- Scavenging: Limpieza automática

**DHCP Server:**
- Scopes: Por VLAN/subnet
- Reservas: Equipos críticos
- Failover: Entre 2 servidores
- Options: DNS, gateway, NTP

**File Services:**
- File Server Resource Manager
- DFS (Distributed File System)
- Quotas por usuario/carpeta
- File screening (tipos bloqueados)
- VSS (Shadow copies) cada 2 horas

**Windows Admin Center:**
- Gestión centralizada web
- Monitoreo servidores cluster
- Update management
- Performance monitoring
- Azure hybrid services

**Características Avanzadas:**

**Hyper-V Role:**
- Backup hipervisor (alternativa VMware)
- Nested virtualization
- Shielded VMs (cifrado)
- Host Guardian Service

**Storage Spaces Direct:**
- HCI (Hyperconverged Infrastructure)
- Pooling storage local
- Replicación síncrona
- Alternativa SAN tradicional

**Containers Support:**
- Windows Containers
- Docker compatible
- Kubernetes integration
- Hyper-V isolated containers

**Seguridad Windows Server:**
- BitLocker: Cifrado disco completo
- Credential Guard: Protección credenciales
- Device Guard: Control código ejecutable
- Windows Defender ATP integrado
- Just Enough Administration (JEA)

**Licensing:**
- Costo 16-core pack: $6,155 USD
- 20 cores: 2 packs = $12,310 USD
- Software Assurance: +$3,000 USD/año
- **Total inicial: $12,310 USD**

#### 6.2.2 Red Hat Enterprise Linux 9 (RHEL 9)

**Suscripciones:** 10 servidores virtuales

**Edición:** RHEL Server Standard

**Características RHEL 9:**

**Kernel:**
- Versión: Linux 5.14+
- Long-term support: 10 años
- Live patching: Sin reboot
- Real-time kernel: Opcional

**Application Streams:**
- Múltiples versiones software
- Python: 3.9, 3.11, 3.12
- Node.js: 16, 18, 20
- PHP: 8.0, 8.1, 8.2
- Java: OpenJDK 11, 17, 21

**Gestión y Automatización:**

**Red Hat Satellite:**
- Gestión centralizada sistemas
- Patch management
- Configuration management
- Provisioning automatizado
- Content management

**Ansible Integration:**
- Playbooks certificados Red Hat
- Automation Hub access
- Tower/AWX compatible
- System roles incluidos

**Casos de Uso en Data Center:**

**Servidores Web:**
- Apache HTTP Server 2.4
- Nginx 1.20+
- HAProxy load balancer
- ModSecurity WAF

**Bases de Datos:**
- PostgreSQL 13, 14, 15
- MariaDB 10.5, 10.6
- MySQL 8.0
- Redis 6.2

**Contenedores:**
- Podman (rootless containers)
- Buildah (build images)
- Skopeo (manage images)
- CRI-O runtime

**Servicios Backend:**
- Microservicios Java (Quarkus)
- Python APIs (FastAPI, Django)
- Node.js services
- Go applications

**Seguridad RHEL:**
- SELinux: Mandatory access control
- Firewalld: Dynamic firewall
- Crypto policies: System-wide
- FIPS 140-2: Certified mode
- Audit: Logging detallado

**Soporte Red Hat:**
- Production Support: 24x7
- Response time: 1 hora (Severity 1)
- Portal acceso: Documentación, KBs
- Actualizaciones: CVE patches inmediatos
- Technical Account Manager: Opcional

**Licensing:**
- Standard subscription: $799 USD/año/server
- 10 servers: $7,990 USD/año
- Descuento volumen: 15%
- **Total anual: $6,792 USD**

#### 6.2.3 Ubuntu Server 22.04 LTS

**Licencias:** Open source (Ubuntu Pro opcional)

**Características:**

**Long Term Support:**
- Soporte: 5 años (hasta 2027)
- Kernel: 5.15 LTS
- Updates: Gratuitos
- Extended Security Maintenance: +5 años con Pro

**Ubuntu Pro (Opcional):**
- Costo: $500 USD/año/servidor
- CVE patching: 10 años
- Compliance: FIPS, CIS hardening
- Landscape: Management tool
- Soporte: 24x5 (weekdays)

**Implementaciones en Data Center:**

**Docker Host:**
- Docker Engine: Última versión
- Docker Compose: Orchestration
- Portainer: Web management
- Registry local: Harbor

**Kubernetes Workers:**
- Kubeadm cluster
- MicroK8s (snap)
- Kubelet 1.28+
- CNI: Calico, Flannel

**Desarrollo y Testing:**
- Ambientes dev/staging
- CI/CD runners (GitLab, Jenkins)
- Test automation
- Sandbox environments

**Microservicios:**
- Spring Boot apps
- Node.js Express
- Python Flask/FastAPI
- Go services

**Ventajas Ubuntu:**
- Amplia comunidad
- Documentación extensiva
- Paquetes actualizados
- Cloud integration (AWS, Azure, GCP)
- Snap packages: Apps containerizadas

**Costo:**
- Base OS: $0 (gratis)
- Ubuntu Pro: $500/año/server opcional
- **10 servers con Pro: $5,000 USD/año**

### 6.3 Bases de Datos

#### 6.3.1 Microsoft SQL Server 2022 Enterprise

**Licencias:** 32 cores (servidores DB dedicados)

**Características Principales:**

**Alta Disponibilidad:**

**Always On Availability Groups:**
- Configuración: 2 réplicas sincrónicas
- Failover: Automático <30 segundos
- Readable secondaries: Lectura desde réplica
- Backup offload: Backup desde secundaria
- Multi-subnet: Diferente VLAN/datacenter

**Failover Cluster Instance:**
- Shared storage: SAN
- Active-passive cluster
- Failover automático
- IP virtual flotante

**Performance:**

**In-Memory OLTP:**
- Tablas memory-optimized
- Compilación nativa procedimientos
- 10-100x más rápido transacciones
- Sin lock/latch contention

**Columnstore Indexes:**
- Compresión 10x
- Queries analíticos 100x faster
- Real-time operational analytics
- Updateable columnstore

**Query Store:**
- Historial planes ejecución
- Regression detection
- Query tuning advisor
- Automatic plan correction

**Machine Learning:**

**ML Services:**
- R y Python integrados
- Modelos scoring in-database
- No movimiento datos
- GPU acceleration support

**BI y Analytics:**
- Integration Services (SSIS)
- Analysis Services (SSAS)
- Reporting Services (SSRS)
- Power BI integration

**Seguridad:**

**Always Encrypted:**
- Cifrado columnas sensibles
- Transparent a aplicaciones
- Keys en Azure Key Vault
- Protección datos en reposo y tránsito

**Dynamic Data Masking:**
- Enmascaramiento automático
- Sin cambios aplicación
- Reglas por rol usuario
- Tipos: Partial, random, email

**Row-Level Security:**
- Filtrado automático filas
- Basado en usuario/rol
- Implementación transparente
- Multi-tenant security

**Otros Features:**
- Transparent Data Encryption (TDE)
- Audit logging completo
- SQL Injection prevention
- Compliance (HIPAA, PCI-DSS)

**Licensing:**
- Modelo: Per-core
- Core pack: 2 cores mínimo
- Costo: $15,123 USD/2-core pack
- 32 cores: 16 packs = $242,000 USD
- Software Assurance: +$60,000 USD/año
- **Total: $242,000 USD inicial**

**Alternativa Licensing:**
- Server+CAL: Para <25 usuarios
- SQL Azure: Cloud subscription
- Developer Edition: Gratis (no producción)

#### 6.3.2 Oracle Database 19c Enterprise Edition

**Licencias:** 16 procesadores (conteo Oracle específico)

**Oracle Processor License:**
- Intel Xeon: Factor 0.5
- 32 cores físicos × 0.5 = 16 processors
- Mínimo: 1 processor por servidor

**Características Enterprise:**

**Real Application Clusters (RAC):**
- Cluster activo-activo
- Load balancing automático
- Failover transparente
- Scalability horizontal
- Hasta 100 nodos cluster

**Active Data Guard:**
- Standby database sincronizada
- Automatic failover
- Read-only queries en standby
- DML redirect a primaria
- Fast-Start Failover: <30 seg

**Partitioning:**
- Tables y indexes particionados
- Partition pruning automático
- Mantenimiento por partición
- 10-100x performance
- Tipos: Range, hash, list, composite

**Advanced Compression:**
- Hybrid Columnar Compression
- Compresión 10-50x
- Deduplicación
- Heat Map: Análisis uso datos
- Automatic Data Optimization

**Advanced Security:**

**Transparent Data Encryption (TDE):**
- Cifrado tablespaces completos
- Hardware acceleration (AES-NI)
- Key management integrado
- Sin cambios aplicaciones

**Data Redaction:**
- Enmascaramiento dinámico
- Full, partial, random, regexp
- Basado en políticas
- Real-time masking

**Database Vault:**
- Separation of duties
- Privileged user restrictions
- Realms y command rules
- Compliance reporting

**Performance:**

**Automatic Workload Repository (AWR):**
- Snapshots performance cada hora
- Retención 8 días
- 10,000+ métricas
- Trending y anomaly detection

**SQL Tuning Advisor:**
- Análisis automático SQL
- Recomendaciones índices
- SQL profiles
- Reescritura queries

**Multitenant Architecture:**
- Consolidación múltiples bases
- Container Database (CDB)
- Pluggable Databases (PDBs)
- Resource management
- 252 PDBs máximo por CDB

**Machine Learning:**
- Oracle ML in-database
- Algoritmos 30+ incluidos
- R y Python integration
- AutoML automated pipelines
- SQL queries modelos ML

**Licensing Oracle:**
- Processor license: $47,500 USD/proc
- 16 processors: $760,000 USD
- Support (22%/año): $167,200 USD/año
- **Total inicial: $760,000 USD**
- **Costo anual: $167,200 USD**

**Opciones Incluidas en Enterprise:**
- Partitioning: $11,500/proc
- Advanced Compression: $11,500/proc
- Advanced Security: $15,000/proc
- RAC: $23,000/proc
- **Opciones suman: +$488,000 USD**

**Total con Opciones:**
- Licenses + Options: $1,248,000 USD
- Support anual: $274,560 USD

**Nota Importante:** Oracle es muy costoso. Alternativa para presupuesto limitado: PostgreSQL con extensiones empresariales.

#### 6.3.3 PostgreSQL 15 (Open Source)

**Licencia:** Open source (PostgreSQL License, similar MIT)

**Costo:** $0 USD (gratis)

**Características PostgreSQL 15:**

**Performance:**
- Mejoras sort performance: 25% faster
- Parallel queries mejorados
- Partitioning eficiente
- JIT compilation queries
- Connection pooling (PgBouncer)

**Alta Disponibilidad:**

**Streaming Replication:**
- Asíncrona o sincrónica
- Múltiples standbys
- Cascading replication
- Automatic failover con Patroni

**Logical Replication:**
- Replicación selectiva tablas
- Cross-version replication
- Multi-master (con BDR)
- Filtering rows/columns

**Extensiones Utilizadas:**

**PostGIS:**
- Datos geoespaciales
- Tipos geometry y geography
- 400+ funciones GIS
- Raster support
- Routing (pgRouting)

**TimescaleDB:**
- Time-series data optimizado
- Hypertables automáticas
- Compression 90%+
- Continuous aggregates
- Data retention policies

**Citus:**
- Sharding horizontal
- Distributed queries
- Multi-tenant isolation
- Scalability massive

**pgAdmin 4:**
- Web-based administration
- Query tool avanzada
- Visual explain plans
- Backup/restore GUI
- Multi-server management

**Patroni:**
- HA cluster management
- Automatic failover
- Etcd/Consul/Zookeeper backed
- REST API monitoring
- DCS (Distributed Configuration Store)

**Configuración HA:**
```
Nodo 1 (Primaria):
- PostgreSQL 15
- Patroni leader
- Replicación sincrónica

Nodo 2 (Standby):
- PostgreSQL 15
- Patroni follower
- Hot standby queries

Load Balancer (HAProxy):
- Puerto 5432: Escritura (primaria)
- Puerto 5433: Lectura (standby)
```

**Seguridad PostgreSQL:**
- SSL/TLS connections obligatorio
- pg_hba.conf: Control acceso granular
- Row Level Security (RLS)
- SCRAM-SHA-256 authentication
- Audit logging (pgAudit extension)

**Backup Strategy:**
- pg_basebackup: Full backups diarios
- WAL archiving: Point-in-time recovery
- pgBackRest: Incremental/differential
- Retención: 30 días local, 1 año remoto

**Soporte Comercial (Opcional):**
- EDB Postgres Advanced Server: $5,000/año/server
- Crunchybridge managed: Cloud alternativa
- 2ndQuadrant support: €3,000/año
- Comunidad: Gratis vía foros/listas

**Comparación con Oracle:**
- Funcionalidad: 80-90% equivalente
- Performance: Comparable <10TB
- Costo: $0 vs $1.2M+ (ahorro enorme)
- Lock-in: Ninguno (open source)
- Migración: Herramientas disponibles (ora2pg)

---

### 6.4 Gestión, Monitoreo y Backup

#### 6.4.1 Zabbix 6.4 Enterprise

**Licencia:** Open source (gratis)

**Componentes:**

**Zabbix Server:**
- Backend de procesamiento
- Database: PostgreSQL o MySQL
- Pollers: 100 procesos concurrentes
- Trapper: Recepción activa datos

**Zabbix Frontend:**
- Web interface PHP
- Apache o Nginx
- Dashboards personalizables
- Maps de red visuales

**Zabbix Proxy:**
- Recolección distribuida
- Reduce carga servidor
- Operación offline
- Hasta 10,000 dispositivos/proxy

**Capacidades de Monitoreo:**

**Infraestructura:**
- Servidores: Linux, Windows, Unix
- Hipervisores: VMware, Hyper-V, KVM
- Storage: Dell EMC, NetApp, Pure
- UPS: APC, Schneider, Eaton

**Networking:**
- Switches: Cisco, Juniper, Arista
- Routers: Cisco ISR, ASR
- Firewalls: Fortinet, Palo Alto
- Load balancers: F5, HAProxy

**Aplicaciones:**
- Web servers: Apache, Nginx, IIS
- Databases: MySQL, PostgreSQL, Oracle, SQL Server
- Middleware: Tomcat, JBoss, WebLogic
- Mensajería: RabbitMQ, Kafka

**Servicios Cloud:**
- AWS: EC2, RDS, S3 via CloudWatch
- Azure: VMs, SQL Database via Monitor
- GCP: Compute Engine via Stackdriver

**Métricas Monitoreadas:**

**Sistema:**
- CPU: Usage, load, processes
- Memoria: Used, free, cached, swap
- Disco: I/O, usage, inodes
- Red: Bandwidth, packets, errors

**Aplicación:**
- Response time
- Throughput (TPS)
