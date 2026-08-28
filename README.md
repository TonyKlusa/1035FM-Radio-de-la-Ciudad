# Radio de la Ciudad · 103.5 FM

Sitio web "DE PRUEBA" de **Radio de la Ciudad 103.5 FM**, emisora de Resistencia, Chaco. Reúne la programación, mensajes, información de contacto y un reproductor para escuchar la transmisión en vivo.

**Sitio publicado:** [tonyklusa.github.io/1035FM-Radio-de-la-Ciudad](https://tonyklusa.github.io/1035FM-Radio-de-la-Ciudad/)

## Características

- Reproductor de radio en vivo conectado al stream de la emisora.
- Mini reproductor fijo con pausa/reproducción y control de volumen.
- Identidad visual personalizada con ecualizador animado de 10 bandas.
- Sintonizador FM visual para la frecuencia 103.5.
- Secciones de presentación, programación, app, mensajes y contacto.
- Navegación adaptable para escritorio y dispositivos móviles.
- Enlaces a contenido externo, programación y canales oficiales.

## Tecnologías

- HTML5
- CSS3 (variables, animaciones y diseño responsive)
- JavaScript nativo
- Google Fonts: Fraunces, Manrope e IBM Plex Mono
- GitHub Pages para la publicación estática

No requiere instalación de dependencias ni proceso de compilación.

## Ejecutar localmente

1. Cloná el repositorio:

   ```bash
   git clone https://github.com/TonyKlusa/1035FM-Radio-de-la-Ciudad.git
   ```

2. Abrí la carpeta del proyecto.

3. Abrí `index.html` en un navegador, o iniciá un servidor estático local. Por ejemplo:

   ```bash
   npx serve .
   ```

## Estructura

```text
.
├── index.html    # Sitio completo: estructura, estilos y comportamiento
└── README.md     # Documentación del proyecto
```

## Radio en vivo

El reproductor utiliza la transmisión:

```text
https://cdn.instream.audio:8033/stream
```

Por las políticas de los navegadores, la reproducción solo comienza después de una interacción de la persona usuaria con el botón **Escuchar en vivo**.

## Publicación

El proyecto está configurado para publicarse con GitHub Pages desde la raíz (`/`) de la rama `main`. Cada `git push origin main` actualiza el sitio después del tiempo de despliegue de GitHub Pages.

## Mantenimiento

- Actualizá el contenido directamente en `index.html`.
- Probá los cambios en escritorio y celular antes de publicarlos.
- Verificá periódicamente que el stream de radio continúe disponible.
- Para publicar cambios:

  ```bash
  git add index.html README.md
  git commit -m "Describe el cambio realizado"
  git push origin main
  ```

## Créditos

Desarrollado para **Radio de la Ciudad · FM 103.5**.
