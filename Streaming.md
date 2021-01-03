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
  - OBS para lo demás o AMD
  
## Configuración OBS

Antes de empezar
- Ajustes > Salida > Modo de salida "Avanzado"    
- Activar "Modo Juego" en Windows
- Para Gráficas Nvidia (ejecutar OBS como admin)
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
    - * Twitch bitrate es basura, 6mbs no da para 720p 60 siquiera, para YT usar 1080p + 15mbps o más si posible
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
  - Audio
    - Bitrate: 160kbps
