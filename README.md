# Landing Page Personal de Karina Rojas

Proyecto realizado como ejercicio del **módulo cero del Bootcamp de Desarrollo Web Full Stack** de The Bridge. Consiste en una *landing page* personal que presenta el perfil de Karina Rojas como desarrolladora Full Stack: su presentación, formación, habilidades, tecnologías, los dos proyectos destacados (LiterAlura y NeoFichaje) y los datos de contacto.

La web es **estática**, sin dependencias externas ni gestor de paquetes: está construida únicamente con HTML5, CSS3 (Flexbox + Media Queries) y un pequeño archivo de JavaScript.

---

## Tabla de contenidos

1. [Tecnologías usadas](#tecnologías-usadas)
2. [Estructura del proyecto](#estructura-del-proyecto)
3. [Páginas de la web](#páginas-de-la-web)
4. [Secciones y funcionalidades](#secciones-y-funcionalidades)
5. [Cómo se ha implementado](#cómo-se-ha-implementado)
6. [Diseño responsive](#diseño-responsive)
7. [Cómo ejecutar el proyecto](#cómo-ejecutar-el-proyecto)
8. [Despliegue en GitHub Pages](#despliegue-en-github-pages)
9. [Proyectos destacados](#proyectos-destacados)
10. [Estado de avance](#estado-de-avance)
11. [Siguientes pasos](#siguientes-pasos)
12. [Autora](#autora)

---

## Tecnologías usadas

### Frontend (la web en sí)

- **HTML5** — Maquetación semántica de todas las páginas (`header`, `nav`, `main`, `section`, `article`, `figure`, `footer`).
- **CSS3** — Estilos de toda la interfaz.
  - **Variables CSS (`:root`)** para gestionar la paleta de colores y reutilizarla en todo el proyecto.
  - **Flexbox** para distribuir el contenido (menús, columnas, tarjetas, galerías).
  - **Media Queries** para el diseño responsive.
  - **Transiciones y pseudo-clases** (`:hover`, `:focus`) para los efectos visuales.
- **JavaScript (script.js)** — Archivo enlazado a las páginas, actualmente vacío (esqueleto preparado para añadir interactividad, como el envío del formulario de contacto).

### Proyectos mostrados en el portfolio (no es tecnología de esta web, sino de los proyectos documentados)

- **LiterAlura**: Java 17+, Spring Boot 3, Spring Data JPA / Hibernate, PostgreSQL, API de Gutendex, Maven.
- **NeoFichaje**: Kotlin, XML, Android Studio, Firebase Authentication, Firestore, Firebase Cloud Storage, Google Sign-In, MaterialCalendarView.

### Herramientas de desarrollo

- **Git y GitHub** — Control de versiones y despliegue del repositorio.
- **VS Code** — Editor utilizado; el proyecto incluye `.vscode/settings.json` con el puerto `5503` para **Live Server**.

---

## Estructura del proyecto

```
landing_web/
│
├── index.html              → Página principal (landing page) con todas las secciones
├── style.css               → Hoja de estilos global (todas las páginas la usan)
├── script.js               → JavaScript global (actualmente vacío)
├── README.md               → Documentación del proyecto
│
├── assets/                 → Recursos estáticos (imágenes y PDF)
│   ├── foto_perfil_porfolio.png
│   ├── libros.jpg
│   ├── login.png
│   ├── registro.png
│   ├── menuEmpresario.png
│   ├── menuEmpleado.png
│   ├── gestionAsistencia.png
│   ├── inicioEmpleado.png
│   └── karina_rojas_cv.pdf
│
├── pages/                  → Páginas secundarias
│   ├── formulario.html     → Formulario de contacto
│   └── proyectos.html      → Detalle de los proyectos NeoFichaje y LiterAlura
│
└── .vscode/                → Configuración del editor
    └── settings.json       → Puerto de Live Server (5503)
```

> Nota: aunque el README original mencionaba una carpeta `css`, en la estructura real los estilos se gestionan en un único `style.css` en la raíz, compartido por las tres páginas mediante rutas relativas.

---

## Páginas de la web

### 1. `index.html` — Landing page principal

Es la página de entrada y la más completa. Incluye las secciones (ver [Secciones y funcionalidades](#secciones-y-funcionalidades)):

- `#presentacion`
- `#sobre-mi`
- `#tecnologias`
- `#proyectos`
- `#habilidades`
- `#contacto` (en el `footer`)

### 2. `pages/proyectos.html` — Detalle de proyectos

Página dedicada a mostrar en profundidad los dos proyectos del portfolio con sus capturas y documentación técnica. Usa anclas internas para navegar entre los dos proyectos.

### 3. `pages/formulario.html` — Formulario de contacto

Página con un formulario de contacto funcional en el frontend (validación HTML nativa) pero sin backend asociado (enviaría al `action="#"`).

---

## Secciones y funcionalidades

### Navegación (`header > nav`)

Menú de navegación presente en todas las páginas:

- Enlaces a secciones internas mediante **anclas** (`#sobre-mi`, `#tecnologias`, `#proyectos`, `#contacto`).
- Enlace al formulario de contacto (`pages/formulario.html#contacto-formulario`).
- **Botón "Descarga CV"** (`.btn-cv`) que descarga el PDF `assets/karina_rojas_cv.pdf` usando el atributo `download`.
- `:hover` con cambio de color de fondo (Efecto de resaltado), con transición suave.

### `#presentacion` — Presentación

- Foto de perfil circular con borde y sombra rosa.
- Nombre y título profesional.
- Descripción breve como desarrolladora Full Stack (backend con Java/Spring Boot y frontend con HTML/CSS/JavaScript).
- Lista de tecnologías principales.

**Cómo se ha implementado:** la imagen se estiliza con `border-radius: 50%`, borde y `box-shadow` rosa. Los encabezados y párrafos se centran con Flexbox (`align-items: center; justify-content: center`).

### `#sobre-mi` — Sobre mí

- Formación académica (CFP, bootcamp).
- Experiencia práctica (prácticas en Esencial Global Eventos).
- Habilidades.
- Destacado que indica que está en búsqueda de proyectos.

**Cómo se ha implementado:** usa una sección interna `.columna-sobre-mi` con **dos columnas** Flexbox (`.col`), separadas visualmente por un `border-right` a la primera. La clase `.destacado` tiene un efecto `:hover` que aplica `text-shadow` rosa y negrita.

### `#tecnologias` — Tecnologías

Tarjetas agrupadas por categoría:

- Lenguajes de programación.
- Frameworks y librerías.
- Bases de datos.
- Servicios y APIs.
- Herramientas.
- Otros conocimientos.

**Cómo se ha implementado:** la sección `.columna-tecnologias` usa Flexbox con `flex-wrap: wrap` y cada tarjeta `.col-tec` tiene `width: 30%`. Al pasar el ratón, se aplica un `box-shadow` cian. `align-items: stretch` iguala la altura de todas las tarjetas.

### `#proyectos` — Proyectos destacados

Dos tarjetas (LiterAlura y NeoFichaje). Cada una incluye:

- Imagen del proyecto.
- Descripción general.
- Columnas con funcionalidades y tecnologías.
- **Botones de acción**: "Ver detalles del proyecto" (te lleva a `pages/proyectos.html`) y "Ver en GitHub" (enlace externo con `target="_blank" rel="noopener"`).

**Cómo se ha implementado:** las tarjetas `.liter-alura` y `.neo-fichaje` usan Flexbox con dos columnas cada una (`.col-pro` y `.col-neo`), separadas por bordes. Los enlaces `.enlaces-proyecto` se distribuyen con `justify-content: space-around`. Las imágenes tienen `object-fit: cover`, borde y sombra, con cambio de color al `:hover`.

### `#habilidades` — Habilidades transversales

- Píldoras (badges) con habilidades blandas: planificación, adaptación, trabajo en equipo, trabajo bajo presión.

**Cómo se ha implementado:** lista `.habilidades` con `display: flex` y `flex-wrap: wrap`; cada `li` tiene `border-radius: 20px` formando píldoras con fondo de tarjeta.

### `#contacto` — Datos de contacto (en el `footer`)

- Email (enlace `mailto:`).
- LinkedIn.
- GitHub.
- Enlace de descarga del CV.

### `pages/proyectos.html` — Detalle de proyectos

Para **NeoFichaje**:

- Descripción general.
- **Roles de usuario** en dos columnas: Empleado/Técnico y Administrador/Empresario.
- Tecnologías utilizadas.
- Funcionalidades destacadas.
- **Flujo de uso** numerado (lista ordenada con círculos numerados `.numero` que escalan al `:hover`).
- **Galería de capturas** de pantalla en `figure`/`figcaption`.
- Contenedor de vídeo de demostración (placeholder vacío).
- Autora y seguimiento del desarrollo.

Para **LiterAlura**:

- Descripción general.
- Funcionalidades.
- Tecnologías utilizadas.
- **Instalación y configuración** numerada, con variables de entorno y comandos (`mvn spring-boot:run`).
- **Estructura del proyecto** (model, repository, service, record, Main).
- API utilizada y captura del menú de consola (tarjetas `.proy-tarjeta`).
- Sublistas desplegables al hacer `:hover` (clase `.has-sublista` + `.sublista`).

### `pages/formulario.html` — Formulario de contacto

- Campos **Nombre**, **Correo electrónico**, **Mensaje** con validación HTML nativa (`required`, `type="email"`).
- Botón "Enviar" (`type="submit"`).
- Estilos `.input-contacto` con foco (`:focus`) que aplican `box-shadow` rosa y `translateY(-2px)`.
- Sin backend: el `action` es `#`, por lo que de momento no envía datos a ningún servidor.

---

## Cómo se ha implementado

### Maquetación (HTML5)

Uso de etiquetas semánticas en todas las páginas:
- `header` + `nav` para la cabecera de navegación.
- `main` como contenedor central.
- `section` para agrupar contenido por tema.
- `article` para cada proyecto y para cada tarjeta independiente.
- `figure` + `figcaption` para las capturas.
- `footer` para el bloque de contacto y copyright.
- Atributos de accesibilidad: `lang="es"`, `alt` descriptivo en imágenes, `title` en enlaces externos, `target="_blank" rel="noopener"` para seguridad.

### Estilos (CSS3)

- **Variables CSS en `:root`**: toda la paleta está centralizada:
  - Fondos: `--fondo-principal`, `--fondo-secundario`, `--fondo-card`.
  - Colores de acento: `--color-principal` (cian), `--rosa-acento`, `--morado-acento`.
  - Textos: `--texto-principal`, `--texto-suave`.
- **Sistema de diseño Flexbox**: casi todas las secciones usan `display: flex` para alinear, centrar y distribuir el contenido.
- **Efectos mediante transiciones**: `transition` de `0.3s` / `0.4s` / `0.5s` junto con `:hover` para sombras, cambios de color, escalados (`transform: scale`) y elevaciones (`translateY`).
- **Un solo `style.css` compartido** entre las tres páginas (IMPORTANTE usar `../style.css` desde `pages/`).

### JavaScript

- `script.js` (raíz) y `pages/script.js` están **enlazados** desde las páginas pero **actualmente vacíos**. Están preparados para incorporar interactividad (por ejemplo, manejar el envío del formulario con `preventDefault` y validación extra, o efectos de scroll).
- > Observación: los `script.js` dentro de `pages/` se referencian (`./script.js`) pero no existen en esa carpeta, por lo que el navegador podría lanzar un 404. Si se quiere usar JavaScript en `formulario.html` y `proyectos.html`, conviene apuntar a `../script.js` como se hace con el CSS.

---

## Diseño responsive

El proyecto aplica **mobile-first** con Media Queries a partir de `768px` (punto de corte para tablet/escritorio).

Ejemplos del comportamiento responsive:

- **Nav**: en móvil se mantiene apilada/volcada en fila según el tamaño; en escritorio permanece horizontal (`flex-direction: row; justify-content: center; gap: 20px`).
- **Columnas de "Sobre mí"**: en móvil se apilan en columna; a partir de 768px pasan a fila con `gap` y el `border-right` separador.
- **Tarjetas y galerías**: `flex-wrap: wrap` para que las tarjetas de tecnologías y las capturas fluyan a múltiples líneas.
- **Imágenes de proyectos**: en escritorio se restringe su tamaño (p. ej. `width: 200px` para capturas en la galería).
- **Formulario**: se centra y limita a `max-width: 600px` en pantallas ≥ 768px.
- **Tarjetas de proyectos**: `.proy-tarjeta` pasa de columna a fila (`flex-direction: row; flex-wrap: wrap`).

---

## Cómo ejecutar el proyecto

El proyecto es **100% estático**, sin dependencias ni instalación previa. Tienes dos opciones:

### Opción 1 — Abrir directamente

Haz doble clic en `index.html` o ábrelo con el navegador. Las rutas relativas funcionan igualmente.

### Opción 2 — Con Live Server (recomendado)

Desde VS Code, con la extensión **Live Server**:

1. Abre la carpeta `landing_web` en VS Code.
2. Haz clic derecho sobre `index.html` → **"Open with Live Server"**.

El archivo `.vscode/settings.json` ya fija el puerto `5503` para que la recarga en caliente use siempre ese puerto:

```json
{
    "liveServer.settings.port": 5503
}
```

---

## Despliegue en GitHub Pages

El repositorio se encuentra en GitHub:

- Repositorio: [https://github.com/KarinaRojasDev/landing_web](https://github.com/KarinaRojasDev/landing_web)

Se puede publicar como sitio estático mediante **GitHub Pages** apuntando a la rama principal y a la carpeta raíz (`/`), donde se encuentra `index.html`.

---

## Proyectos destacados

Los dos proyectos documentados en el portfolio (repositorios aparte):

| Proyecto | Tech Stack | Enlace |
|----------|-----------|--------|
| **LiterAlura** | Java 17+, Spring Boot 3, Spring Data JPA/Hibernate, PostgreSQL, Gutendex API, Maven | [GitHub](https://github.com/KarinaRojasDev/LiterAlura) |
| **NeoFichaje** | Kotlin, XML, Android Studio, Firebase Auth, Firestore, Cloud Storage, Google Sign-In, MaterialCalendarView | [GitHub](https://github.com/KarinaRojasDev/proyecto-neo-fichaje) |

---

## Estado de avance

- Presentación personal: 100%
- Secciones de la web (sobre mí, tecnologías, proyectos, habilidades): 100%
- Proyectos y enlaces: 100%
- Página de detalle de proyectos: 100%
- Formulario de contacto: 90% (el diseño está, falta conectarlo a un backend/email)
- Diseño responsive: 80%
- JavaScript / interactividad: 10% (archivos creados pero vacíos)

---

## Siguientes pasos

- Añadir lógica real al formulario de contacto (p. ej. `FormSubmit`, `EmailJS` o un backend).
- Completar la interactividad en `script.js` (validaciones, menú móvil hamburguesa, scroll suave).
- Mejorar la estética y añadir animaciones ligeras (CSS keyframes).
- Optimizar y comprimir imágenes para mejorar el rendimiento.
- Añadir el `<source src>` a los vídeos de demostración de `proyectos.html`.
- Añadir más proyectos y enlaces a repositorios.

---

## Autora

- **Nombre:** Karina Rojas
- **LinkedIn:** [Karina Paola Rojas Jorge](https://www.linkedin.com/in/karina-paola-rojas-jorge-812289313/)
- **GitHub:** [KarinaRojasDev](https://github.com/KarinaRojasDev)
- **Email:** karinacodecompetent@gmail.com
