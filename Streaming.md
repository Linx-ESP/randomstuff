Aquí configuraciones, trucos y software
RECOMENDADO [EPOSVOX](https://www.youtube.com/user/EposVox)
# Hardware
## Cámara
- Usar el móvil como webcam
  - Puedes usar el móvil con [NDI Cam Nueva](https://play.google.com/store/apps/details?id=com.newtek.ndi.hxcam) o [NDI Cam Old](https://apkcombo.com/es-es/newtek-ndi/com.newtek.ndicamera/)
  - NDI > "IP"
  - [EposVox video](https://www.youtube.com/watch?v=jpkvD3lk5QQ)
  - Requiere [NDI plugin](https://obsproject.com/forum/resources/obs-ndi-newtek-ndi™-integration-into-obs-studio.528/)
- Mejora mucho más la calidad cuando tienes buena luz, no grabes con poca luz o una muy fuerte
  - Preferible gastar el dinero antes en bombillas y difusores baratos o DIY que en cámaras

# Software
## Programas recomendado / necesarios
  - Nvidia Share si no necestias composición o controles
    - Si no se habilita "Captura de escritorio" es básicamente sin pérdida de rendimiento
    - Composición con overlays o webcam hace que deje de ser sin pérdida de rendimiento
  - OBS para lo demás o no tienes gráfica Nvidia
  
## Configuración OBS

Antes de empezar
- Ajustes > Salida > Modo de salida "Avanzado"    
- Activar "Modo Juego" en Windows

<details>
<summary> Ajustes generales de OBS </summary>

  - Emisión
    - Twitch / YT / otro
      - Servidor: España
      - Ignorar las recomendaciones de configuración...
        - Permite asignar 8kbps en twitch, pero puede twitch no te asegura eso, si la plataforma está bajo estrés perderas los 8k. Partners tienen acceso siempre a 8kbps. No se pierde nada por probar
  - Audio
    - Frecuencia de muestreo: "48khz"
    - Canales: "Estéreo"
    - Dispositivos de audio globales: configurar entradas y salidas
  - Vídeo
    - Resolución de la base: Como OBS va a hacer su composición
    - Resolución de salida: Predeterminada para grabación o emisión
      - Recomendación: Ambas a lo que se vaya a grabar, 1080p o resolución del monitor. Ambas igual
    - Filtro de escala: "Bicúbico" / "Lanczos" (si solo webcam, se puede cambiar en su entrada)
    - Valores comunes de FPS: "60"
  - Avanzados
    - Prioridad del proceso: "Mayor a normal" (parece requerir admin y no debería hacer mucho)
    - Renderizador: "Direct3D 11"
    - Formato de color: "NV12" te quita de problemas, prueba "RGB" pero puede tener mayor uso de CPU al emitir
    - Espacio de color: "sRGB" / "709" si tu monitor está configurado para REC.709
    - Gama de Colores: Se puede configurar para cada entrada, cada capturador o webcam será distintos
      - Para captura de PC: "Completo" (comprobar que en el panel de control de NVIDIA o equivalentede AMD > Cambiar la resolución aparezca como RGB - Completa)
    - Habilitar optimizaciones de red
    - Habilitar aceleración por hardware en el navegador
</details>
<details>
<summary> Para Gráficas Nvidia (ejecutar OBS como admin) </summary>
  
  - Emisión
    - Codificador: "NVEnc (new)"
    - Cambiar escala de salida: 1280x720 *
    - Control de frecuencia: "CBR" (Constant BitRate)
    - Tasa de bits / bitrate: "6000Kbps" *
    - Keyframes: "2"
    - Preajuste: "Máxima Calidad"
    - Perfil: "main"
    - Look Ahead: No
    - Psycho Visual Tuning: Sí
    - GPU: "0" / Seleccionar si multigpu
    - Máximos B-Frames: "2"
    - *->Twitch bitrate es basura, 6mbs no da para 720p 60 siquiera, para YT usar 1080p + 15mbps o más si posible
  - Grabación
    - Formato: "flv" (se puede convertir a mp4 en OBS) / "mp4 (compatible directamente con todo)"
    - Codificador: "NVEnc (new)"
    - Control de la frecuencia: "CQP" (Constant Quantization Parameter o Controlado por calidad)
    - Nivel de CQ: "21" (menos es más fiel pero mayor bitrate, jugar con ello o usar handbrake a posteriori)
    - Intervalo de Keyframe: "0" (auto)
    - Preajuste: "Máxima Calidad"
    - Perfil: "main"
    - Look Ahead: No
    - Psycho Visual Tuning: Sí
    - GPU: "0" / Seleccionar si multigpu
    - Máximos B-Frames: "2"
</details>
<details>
<summary> Para el resto (usando CPU). Basado en <a href="https://www.youtube.com/watch?v=fQ04pIcpMkM">EposVox</a> </summary>
  
  - Emisión
    - Codificador: "x264"
    - Cambiar escala de salida: 1280x720 *
    - Control de frecuencia: "CBR" (Constant BitRate)
    - Tasa de bits / bitrate: "6000Kbps" *
    - Usar tamaño de caché personalizado: "No"
    - Intervalo de fotogramas clave: "2"
    - Perfil de uso de CPU: "Medium"
    - Perfil: "High"
    - Sintonizar: (ninguno)
    - *IMPORTANTE*: Opciones x264: "threads=XX (número de hilos que quieras asignar) rc-lookahead=60 trellis=1 direct-pred=spatial"
    - *->Twitch bitrate es basura, 6mbs no da para 720p 60 siquiera, para YT usar 1080p + 15mbps o más si posible
  - Grabación
    - Formato: "flv" (se puede convertir a mp4 en OBS) / "mp4 (compatible directamente con todo)"
    - Codificador: "x264"
    - Control de frecuencia: "CRF" (Constant Rate Factor o Controlado por calidad)
    - CRF: "15" (menos es más fiel pero más bitrate, jugar con ello)
    - Perfil de uso de CPU: "medium"
    - Perfil: "High"
    - Sintonizar: (ninguno)
    - *IMPORTANTE*: Opciones x264: "threads=XX (número de hilos que quieras asignar) rc-lookahead=60 trellis=1 direct-pred=spatial"
</details>

Consejos Extra:
-Bitrate
  - Bitrate de Twitch es 6mbps asegurados, pero hasta 8mpbs libres, si la plataforma decide puede caer tu bitrate a 6 o el directo (no estoy seguro), pero solo si la plataforma está saturada
    - 8mbps está asegurado para Partners de Twitch
    - No hay consecuencias en tu cuenta si usas 8mbps, así que prueba con ello
    - Como referencia, 8mbps es lo que da YT a 720p 60fps videos
  - YT tiene un limite de bitrate de 15mbps, pero si le das más lo procesa YT, así que cuanto más mejor pero la ganancia es menor, aunque justificable
  - Para superar los límites de bitrate necesitas habiltar la función en Ajutes > Emisión > Ignorar recomendaciones...












