Radio de la Ciudad · 103.5 FM
Sitio web oficial de Radio de la Ciudad 103.5 FM, emisora de Resistencia, Chaco. Reúne la programación, mensajes del fin de semana, información de contacto y un reproductor integrado para escuchar la transmisión en vivo.

🌐 Sitio publicado: tonyklusa.github.io/1035FM-Radio-de-la-Ciudad

✨ Características
🎙️ Reproductor de radio en vivo conectado al stream de la emisora vía cdnrad.com.

🎚️ Mini reproductor fijo con botón pausa/reproducción y control de volumen.

📻 Sintonizador FM visual para la frecuencia 103.5 (dial SVG animado con aguja que se mueve al cargar).

🎵 Ecualizador animado de 10 bandas como identidad visual en el logo.

🎓 Sistema de popovers bíblicos — al pasar el mouse sobre las referencias (ej. Efesios 2:19) se muestra el versículo en PDT con link a Bible.com.

📺 Última prédica automática — carga el video más reciente de la lista de YouTube de Iglesia de la Ciudad mediante el feed RSS.

🎧 Última prédica en Spotify — embed del show "Palabra de Dios".

📱 Diseño responsive para escritorio, tablet y móviles (con menú hamburguesa desde 760px).

💬 Botón flotante de WhatsApp y tarjeta de contacto con links clickeables.

🎨 Animaciones al hacer scroll con IntersectionObserver (fade-in + translateY).

🔗 Enlaces a la programación completa y redes oficiales de Iglesia de la Ciudad.

🗓️ Programación semanal — muestra días, horarios y programas a partir de los datos de `Programacion_limpia.xlsx`.

🛠️ Tecnologías
HTML5

CSS3 — variables CSS, animaciones, mask-image, media queries, backdrop-filter

JavaScript nativo — sin frameworks ni dependencias

CSV local — carga de la programación semanal en el navegador, generado desde `Programacion_limpia.xlsx`

Google Fonts: Fraunces (serif), Manrope (sans), IBM Plex Mono (mono)

YouTube RSS — a través de rss2json.com para obtener la última prédica

Spotify Embed — show 5KmhTiLmIiAFabuS6tL8G7

GitHub Pages para hosting estático

Sin dependencias, sin proceso de compilación.

📁 Estructura del proyecto
text
1035FM-Radio-de-la-Ciudad/
├── index.html       # Sitio completo (HTML + CSS + JS en un solo archivo)
├── README.md        # Este archivo
├── Logo.webp        # Logo de la radio (hero)
├── Programacion_limpia.xlsx  # Planilla original de programación
└── programacion.csv          # Datos que carga la sección de programación
El diseño, los estilos y el JavaScript están dentro de `index.html`; la programación se carga desde `programacion.csv`.

🚀 Ejecutar localmente
bash
# Clonar el repositorio
git clone https://github.com/TonyKlusa/1035FM-Radio-de-la-Ciudad.git

# Entrar a la carpeta
cd 1035FM-Radio-de-la-Ciudad

# Levantar un servidor local para que carguen la programación y el RSS
npx serve .
# o
python -m http.server 8000
Luego abrí http://localhost:8000 (o el puerto que indique el servidor).

Nota: La programación se lee desde `programacion.csv`, por lo que hace falta abrir el sitio mediante un servidor local y no directamente con `file://`. Si actualizás la planilla de Excel, actualizá también este CSV.

⚙️ Configuración y personalización
🎙️ Cambiar el stream de la radio
En la sección // ---------- live radio stream ---------- del JavaScript, modificá la URL:

javascript
const radioStream = new Audio('https://direct-ar1.cdnrad.com:9443/listen/radiodelaciudad1035');
Reemplazá por la URL del stream deseado. Formato compatible: HTTP/HTTPS directo (MP3, AAC, OGG).

📺 Cambiar la lista de YouTube
Buscá la función loadLatestSermon():

javascript
const PLAYLIST_ID = 'PLc2xXXwpj9WniCu323iCd0Qmy-W38nWFE';
Reemplazá el ID por el de la lista de reproducción deseada. El RSS se arma automáticamente.

🎧 Cambiar el show de Spotify
En la sección de Spotify, cambiá el src del iframe:

html
<iframe src="https://open.spotify.com/embed/show/5KmhTiLmIiAFabuS6tL8G7?utm_source=generator&theme=0" ...></iframe>
El ID del show está entre /show/ y ?.

📖 Agregar o editar versículos
En el objeto VERSES (arriba del script):

javascript
const VERSES = {
  'EF2.19': { 
    ref: 'Efesios 2:19', 
    text: 'Quien cree en Cristo deja de ser un extraño...', 
    url: 'https://www.bible.com/es/bible/197/EPH.2.19-20.PDT' 
  },
  // Agregá más entradas con el patrón 'LIBRO_CAP.VERS'
};
Y luego en el HTML, usá el atributo data-verse con la clave correspondiente:

html
<div class="verse" data-verse="EF2.19">Efesios 2:19</div>
📞 Datos de contacto
WhatsApp: reemplazá 5493625171234 en todas las URLs wa.me/...

Dirección y teléfono: editá la sección <section class="contact">

Redes: links en .about-cta .links y en el footer

🎨 Colores y tipografías
Los colores están definidos como variables CSS en :root:

css
--navy-0: #070F18;   /* Fondo más oscuro */
--navy-1: #0B1721;   /* Fondo principal */
--petrol: #0E7C8C;   /* Azul petróleo (acentos) */
--petrol-light: #3FC3D3;  /* Cian (highlights) */
--ice: #9FE8EF;      /* Celeste claro */
--paper: #E6EEF1;    /* Texto claro */
Cambiando estos valores se reajusta toda la paleta.

🌐 Deploy en GitHub Pages
Subí los cambios a la rama main:

bash
git add .
git commit -m "Actualización del sitio"
git push origin main
En el repositorio de GitHub, andá a Settings → Pages.

En Source, elegí Deploy from a branch → main → carpeta / (root).

Guardá y esperá unos minutos. La URL será https://<usuario>.github.io/1035FM-Radio-de-la-Ciudad/.

🎯 Secciones del sitio
Sección	Anclaje	Descripción
Hero	#inicio	Presentación con sintonizador FM animado y botón "Escuchar"
Nosotros	#nosotros	Historia de la radio + 5 pasos del journey del creyente con versículos
App	#app	Link a Google Play
Programación	#programacion	Horarios semanales cargados desde programacion.csv y descarga de la planilla completa
Próximamente	—	Aviso del canal de WhatsApp (con botón de contacto)
Mensajes	#mensajes	Última prédica YouTube + show Spotify
Contacto	#contacto	Tarjeta con dirección, teléfono, email y WhatsApp
📻 Sobre la emisora
Radio de la Ciudad es la voz de Iglesia de la Ciudad, pastoreada por José Luis y Silvia Cinalli en Resistencia, Chaco.

🌐 Sitio: iglesiadelaciudad.net

📸 Instagram: @idelaciudad

👍 Facebook: infoiglesiadelaciudad

📺 YouTube: Iglesia de la Ciudad

📍 Dirección: Avenida Castelli 314, Resistencia, Chaco, Argentina

📄 Licencia
Sitio desarrollado para Radio de la Ciudad 103.5 FM. Contenido (marca, textos, prédicas) © Radio de la Ciudad. Código disponible para consulta y aprendizaje.

🙌 Créditos
Diseño y desarrollo: Klusacek

Tipografías: Google Fonts (Fraunces, Manrope, IBM Plex Mono)

Versículos PDT: Bible.com

Hosting: GitHub Pages