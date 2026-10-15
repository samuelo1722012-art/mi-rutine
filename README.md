# Mi Rutina — aplicación web instalable

Versión inicial para Android/Samsung Galaxy S21. Es una PWA (Progressive Web App) sencilla, sin cuentas y sin servidor de datos. El horario y las tareas completadas se guardan en el almacenamiento local del navegador.

## Incluye
- Horario base: almuerzo 13:30–14:00; loza 14:00–14:30; descanso 14:30–15:00; tareas 15:00–18:00; clase 18:00–19:00; juego 19:00–19:30.
- Cuenta regresiva para la actividad actual.
- Marcar actividad terminada y recordar la siguiente.
- Extensión de cinco minutos que desplaza el horario.
- Control por voz con comandos: “tarea terminada”, “cinco minutos más”, “qué sigue”, “cómo voy”.
- Solicitud de permiso para notificaciones del sistema.
- PWA instalable y caché básica para volver a abrir la interfaz sin conexión después de la primera carga.

## Instalación sencilla en Samsung S21

Para instalar una PWA, el sitio tiene que servirse por HTTPS (o localhost). Abrir `index.html` como archivo local no permite instalarla correctamente ni usar el service worker.

### Opción A: publicar gratis con GitHub Pages
1. En un ordenador, inicia sesión en GitHub y crea un repositorio nuevo, por ejemplo `mi-rutina`.
2. Descomprime el ZIP y sube los archivos que están dentro de la carpeta (index.html, manifest.webmanifest, sw.js, icon.svg y README.md) a la raíz del repositorio.
3. En el repositorio, entra en **Settings → Pages**.
4. En “Build and deployment”, elige desplegar desde la rama principal (`main`) y la carpeta `/ (root)`, y guarda.
5. GitHub te mostrará una URL HTTPS. Espera a que esté publicada.
6. En el Samsung S21, abre esa URL en **Chrome**.
7. Pulsa el menú ⋮ y busca **Instalar aplicación** o **Añadir a pantalla de inicio**. El nombre exacto cambia según la versión de Chrome/Android.
8. Abre Mi Rutina desde el icono. Pulsa **Activar notificaciones** y acepta el permiso. Prueba también el botón de sonido y el micrófono.

Si no tienes ordenador o una cuenta de GitHub, pide ayuda a una persona adulta de confianza para publicar los archivos. No compartas contraseñas con nadie.

### Actualizar
Cuando reemplaces archivos en el repositorio, vuelve a abrir la app con internet. Si ves una versión antigua, cierra la app por completo y vuelve a abrirla; puede tardar un poco en actualizar la caché.

## Límites reales (importante)
- **Alarmas en segundo plano:** esta versión no puede garantizar alarmas exactas cuando Chrome está cerrado, el teléfono está bloqueado o Android suspende la app. El service worker permite caché, pero no crea un temporizador persistente ni programa alarmas del sistema.
- **Notificaciones:** funcionan solo si el sitio tiene HTTPS, el permiso está concedido y Android/Chrome no las bloquea. Los temporizadores de JavaScript solo son fiables mientras la página está activa; por eso, para los avisos más fiables, deja la app abierta.
- **Voz:** usa Web Speech API, que no está disponible en todos los navegadores. En Chrome para Android suele estar disponible, pero puede depender de la versión, idioma y conexión. Requiere permiso del micrófono y una pulsación para comenzar cada escucha; no es escucha permanente ni funciona de forma fiable con la app en segundo plano. Las frases se procesan por el servicio de reconocimiento del navegador y pueden necesitar internet.
- **Voz hablada:** la lectura en voz alta depende de las voces instaladas en el teléfono y de la configuración de sonido.
- **No es una app nativa APK:** no puede garantizar el mismo control de alarmas, micrófono en segundo plano ni permisos que una aplicación Android nativa.
- **Datos:** borrar los datos del sitio o el almacenamiento del navegador puede borrar las tareas marcadas y ajustes guardados.

## Personalizar
En la app puedes cambiar la hora de inicio y la hora de la clase. El horario inicial es una base: ajusta los tiempos según tu rutina real.
