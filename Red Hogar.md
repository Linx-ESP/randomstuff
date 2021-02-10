Router Gamer caca mal basura

# Hardware
- Un PC viejo (o no)
  - No requiere demasiado de nada (por no decir ni gráfica una vez todo instalado)
  - Necesita dos puertos gigabit / ethernet
    - [TP-Link TG-3468](https://www.amazon.es/dp/B003CFATNI
- Nano R4S o Raspberry-base con dos gigabit ehternet (si no se usa un PC)
- Switch neutro / non-managed
  - [TP-Link TL-SG108 V3](https://www.amazon.es/dp/B01EXDG2MO/)
- Punto de Acceso Wifi
  - [Ubiquiti Unifi 6 Lite](https://eu.store.ui.com/collections/unifi-network-access-points/products/unifi-ap-6-lite)
    - Requiere PoE, [si no tienes](https://eu.store.ui.com/collections/related/products/u-poe-af?_pos=1&_sid=215efeb46&_ss=r)
  - [TP-Link EAP110](https://www.pccomponentes.com/tp-link-eap110-punto-de-acceso-300-mbps)

# Software
### Si se va a virtualizar (adicional)
- Proxmox / UnRaid
### Si no se va a virtualizar (LO NORMAL)
- [OpenWRT (x86)](https://downloads.openwrt.org/releases/19.07.6/targets/x86/64/)
  - 'combined-squashfs.img.gz'
- [Etcher](https://www.balena.io/etcher/) (Rufus o Win32DiskImager pueden valer, pero comprobar sha256)
- Recomendado Pi-Hole
- Para ssh Windows Powershell sirve

# Instrucciones
Desconectar todo de la red
- Imagen de OpenWRT > Etcher > PC como nuevo sistema operativo
- Router de la compañia como modo puente
- Configurar OpenWRT
  - Instalar SQM package
    - Crear regla de SQM - Cake/Pie (no fq_codel o fq_cake/pie)
    - Comprobar subida y bajada reales desde el pc con OpenWRT y usar 90% (luego se puede subir hasta que la latencia sea una burrada)
    - Comprobar con DSLreports speedtest que el bufferbloat desaparezca

## Setup Físico debe quedar así
TODO POR CABLE
- Router compañía
  - OpenWRT (PC o Raspberry)
    - Switch
      - Punto de Acceso Wifi
      - Dispositivos

