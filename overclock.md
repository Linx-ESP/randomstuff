# *Disclaimer: esto es un apoyo, más te vale saber que es esto antes de empezar*
# *Manejarte en la BIOS es tu cosa, existe google y son similares, pero no voy a explicarlo aquí*´
# Esto se centra en aquellos OC con herramientas, OC Manual es coñazo
# Antes de nada: ACTUALIZA LA BIOS

# Requisitos previos
- Versión más reciente de BIOS
- Herramientas de monitorización (sobre todo para temperaturas y voltajes)
  - [MSI Afterburner](https://www.guru3d.com/files-details/msi-afterburner-beta-download.html)
  - [HWiNFO](https://www.guru3d.com/files-details/msi-afterburner-beta-download.html)
  - [Aida 64]()
- Pruebas de rendimiento o estabilidad
  - Sobre todo en gráficas, subir un valor no siginifica que suba el rendimiento
  - Se tiene que probar la estabilidad bajo estrés, no en el escritorio
  - Es más dificil de comprobar estabilidad de GPU
  - Es posible que un componente sea estable por sí, no cuando todo está bajo carga
  - [Cinebench r23 o mayor](https://www.maxon.net/en/cinebench) [Rendimiento CPU]
  - [OCCT](https://www.ocbase.com) [Estabilidad CPU]
  - [3DMark Demo](https://www.guru3d.com/files-details/3dmark-download.html) [Estabilidad y rendimiento GPU, algo CPU]
  - [Unigine Heaven](https://benchmark.unigine.com/heaven) [Estabilidad GPU]
  - [HCI Memtest](https://hcidesign.com/memtest/download.html) [Estabilida RAM]
  - [Aida64](https://www.aida64.com/downloads) [Más bien de todo]
-Dos dedos de frente

# OC Gráfica
- AMD es manual, sorry
  - Frecuancias puestas ≠ Frecuancias finales
  - Regresión de rendimiento
- NVIDIA Series 20+ (quizás 16)
  - Nvidia Overlay con Alt+Z
  - > Rendimient > Ajustes de rendimiento > Automático
  - Continuar con 3er paso NVIDIA 900+
- Nvidia Series 900+
  - MSI Afterburner > Nvidia Scanner (suele ser un icono enano de unas gráficas de barras)
  - > OC Scanner > Test (20min ello solo)
  - Activar "at startup" (icono windows dentro de Afterburner)
  - Power Limit y Temp Limit al máximo (es seguro y sano)

# OC Ram
- Como poco en BIOS habilita el perfil XMP (Intel) DOCP (AMD), esto usa la ram por encima de spec a lo que diga el fabricante
- XMP y DOCP usados intercambiablemente, requierido para RAM a 3200Mhz por ejemplo
- Más te vale toda la RAM sea igual, aunque sea cutre
- OC extendido a partir de aquí
- Intel es manual
- La frecuencia de CPU puede afectar a la estabilidad de la RAM
- Calor de la gráfica puede hacer inestable el OC
- RAM en Ryzen
  - [Thaiphoon Burner](http://www.softnology.biz/files.html)
    - Read > Cualquiera de los dos
    - En "Manufacturer" = Samsung / Micron / Hynix
    - En "Die Density" = (Letra)-die
    - Report > (abajo del todo) "Show delay in nanoseconds"
    - Export > Complete HTML Report
  - 1usmus' [DRAM Calculator for Ryzen](https://www.guru3d.com/files-details/download-ryzen-dram-calculator.html)
    - "Procesor" Zen = 1x00 , Zen + = 2X00 , Zen 2 = 3x00
    - Memory Type "Ver Thaiphoon Burner"
    - DRAM PCB revision = Manual
    - Memory Rank => 2 módulo = 1 , 4 módulos = 2, módulos de 32GB cada uno = 2
    - Frecuencia = La deseada (no venirse arriba) (Ryzen 2000 iría con 3400 si bueno, Ryzen 3000 nunca más de 3600)
      - Nuevos Ryzen hacen mejor, nuevas placas hacen mejor
    - Motherboard = tu chipset
    - (Abajo) Import XMP - Importar el Complete HTML de Thaiphoon
    - Calculate Fast (pueden o no ir) o Safe (Siempre van)
    - Llevar los timings y lo de la derecha a la placa
    - EN BIOS: Voltaje de RAM a 1.36 mín, Voltaje de SoC puede ayudar
    - Hacer un perfil de la configuración en caso se reseté, para cambiarlo más fácil


# OC Procesador (esto de aquí con pinzas)
- Aplicaciones desde windows para poner valores a la BIOS son bastante malas, no usar
- Intel, AMD viejos y AMD si no es por PBO son manuales
- AMD Ryzen
  - Si Ryzen X (2700X, 3600x etc) Usar PBO + AutoOC
  - 1usmus' [ClockTunner for Ryzen](https://www.guru3d.com/articles_pages/clocktuner_for_ryzen_ctr_guide_download,3.html) [ZEN 2 (Ryzen 3000) y BIOS Actualizada]
