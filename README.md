# Cronómetro · Skills Cavanilles

Aplicación web para gestionar los tiempos de entre 4 y 16 participantes durante una competición educativa. No requiere instalar dependencias ni tiene un proceso de compilación.

## Puesta en marcha

Coloca `index.html` y `visualizacion.html` en el mismo sitio web y abre `index.html` en el navegador. La gestión y la visualización comparten los datos mediante el almacenamiento local del navegador, por lo que deben abrirse desde el mismo origen (mismo protocolo, dominio y puerto).

Para desarrollo local, puedes servir la carpeta con cualquier servidor web estático. Por ejemplo, si tienes Python instalado:

```bash
python -m http.server 8000
```

Después abre `http://localhost:8000/`. Desde la gestión, pulsa **Ver competición** para abrir la pantalla de visualización en otra ventana.

> Abrir los archivos directamente como `file://` puede impedir que el navegador comparta el almacenamiento entre páginas. Usa un servidor web local o publica ambos archivos juntos.

## Acceso de gestión

La primera vez que abras `index.html`, crea una contraseña. En las siguientes visitas, tendrás que introducirla para acceder al panel de gestión. La contraseña se guarda en el navegador y no se comparte con la página de visualización.

## Gestionar contadores

- Elige entre **4 y 16 equipos** en el selector.
- Cambia el nombre de un equipo haciendo clic en su nombre.
- Pulsa **Iniciar**, **Pausar** o **Reiniciar** en una tarjeta para controlar ese contador.
- Usa los controles de la barra para iniciar, pausar o reiniciar todos a la vez.
- Pulsa **Ajustar** en una tarjeta para cambiar su duración. También puedes añadir o quitar la foto del participante.
- Pulsa **Ajustar tiempo a todos** para aplicar una duración a todos los contadores.
- Usa **Cambiar modo** para alternar entre cuenta atrás y cronómetro.

Al cambiar una duración, el contador mantiene su estado de marcha o pausa y comienza con el nuevo tiempo. Si solo cambias la foto, conserva el tiempo transcurrido.

## Fotos de participantes

En los ajustes individuales, selecciona una imagen para ver su vista previa. **Aplicar cambios** guarda la foto junto al contador; **Quitar foto** elimina la imagen. La aplicación reduce las imágenes antes de guardarlas en el navegador. Las miniaturas se muestran a **100 × 130 píxeles** en gestión y visualización.

## Pantalla de visualización

`visualizacion.html` muestra los nombres, fotos, tiempos y estados de todos los participantes. Se actualiza mientras la gestión está abierta y permite activar pantalla completa con el botón correspondiente.

Los datos y la contraseña se almacenan en `localStorage` del navegador. Se comparten entre páginas del mismo origen y perfil de navegador; no se sincronizan entre dispositivos ni navegadores distintos.

## Atajos de teclado

- **Espacio**: iniciar todos si están parados o pausar todos si alguno está en marcha.
- **R**: reiniciar todos.
- **Esc**: cerrar el cuadro de ajuste.
