# 🐎 Ride to Gondor - HLS Streaming Server

Un sistema de streaming infinito automatizado para la saga de la Tierra Media. Este proyecto utiliza una arquitectura ligera basada en **FFmpeg**, **Python** y **Nginx** para emitir video en alta definición con audio en español y títulos dinámicos.

## 🚀 Características

- **Streaming Infinito:** Bucle continuo de la saga completa sin cortes.
- **Títulos Dinámicos:** Monitorización en tiempo real de los logs de FFmpeg para mostrar el nombre de la película actual en el frontend.
- **Audio Optimizado:** Transcodificación a AAC Estéreo (2.0) para compatibilidad universal (Safari, Chrome, Móviles).
- **Arquitectura en RAM:** Los fragmentos de video se generan en `/dev/shm` para minimizar el desgaste del disco y reducir la latencia.
- **Interfaz Inmersiva:** Frontend minimalista con temática de Gondor y soporte para dispositivos Apple.

## 🛠️ Requisitos Técnicos

- **SO:** Ubuntu / Debian Linux.
- **Software:** - `ffmpeg` (Motor de video)
  - `python3` (Controlador y monitor de títulos)
  - `nginx` (Servidor web y entrega HLS)
- **Librerías Python:** `subprocess`, `threading`, `re`.

## 📂 Estructura de Archivos

```text
/var/www/ridetogondor/
├── backend/
│   ├── streamer.py       # Script principal (FFmpeg + Monitor)
│   └── playlist.txt      # Lista de reproducción generada
├── frontend/
│   ├── index.html        # Interfaz de usuario
│   ├── ridetogondor.png  # Logo y Favicon
│   └── live/             # Enlace simbólico a /dev/shm/hls/
