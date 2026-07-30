# litex.es

Sitio web de **litex.es**, asociación cultural sin ánimo de lucro constituida al amparo
de la Ley Orgánica 1/2002, de 22 de marzo, reguladora del derecho de asociación.

Publicado con GitHub Pages en <https://litex.es>.

## Estructura

```text
index.html
    Portada: la asociación, sus fines y el catálogo
el-pueblo-que-vuelve-en-agosto.html
    Ficha del libro (Iván García Cobo, 14-08-2026)
aviso-legal.html  Aviso legal (art. 10 LSSI), privacidad y cookies
404.html          Página de error
CNAME             Dominio propio: litex.es
.nojekyll         Se sirven los ficheros tal cual, sin procesar con Jekyll
robots.txt sitemap.xml

assets/
  css/fonts.css   @font-face de las tipografías autoalojadas
  css/style.css   Sistema de diseño: tokens, tipografía, botones, cabecera, pie
  css/home.css    Estilos propios de index.html
  css/legal.css   Estilos propios de aviso-legal.html
  css/el-pueblo-que-vuelve-en-agosto.css
                  Estilos propios de la ficha del libro
  js/site.js      Cabecera pegajosa y aparición al hacer scroll
  fonts/          EB Garamond y Playfair Display (WOFF2, subconjuntos latin)
  img/            Logotipos, cubierta del libro, ornamentos e imagen social
```

## Decisiones técnicas

- **HTML y CSS estáticos**, sin generador de sitios, sin dependencias y sin ninguna
  petición a dominios de terceros. Las tipografías van autoalojadas (nada de Google
  Fonts en tiempo de ejecución), de modo que el sitio no cede datos de las personas
  que lo visitan.
- **Sistema de diseño** en `assets/css/style.css`. La paleta procede de la cubierta de
  *El pueblo que vuelve en agosto*: papel ahuesado `#F7F2E8`, carbón `#171A16` y
  sanguina `#8A4B32` como único acento.
- **Tipografías:** Playfair Display para titulares, EB Garamond para el texto.
  Ambas bajo licencia SIL Open Font License 1.1.

## Desarrollo

No hay nada que compilar. Para verlo en local:

```sh
python3 -m http.server 8000
# http://localhost:8000
```

Para publicar, basta con hacer `push` a `main`.

## Cookies

El sitio **no usa cookies ni almacenamiento local**, y por eso no lleva banner
de consentimiento: el art. 22.2 de la Ley 34/2002 sólo obliga a pedirlo cuando
se guarda o se recupera información del dispositivo de quien visita la página.
Comprobado en navegador: `document.cookie` vacío, `localStorage` y
`sessionStorage` a cero.

Esto depende de que no se añadan terceros. Incorporar analítica, un vídeo
incrustado, un botón social o tipografías servidas desde un CDN cambiaría la
situación y obligaría a rehacer esta parte.

## Contacto

<litex@litex.es>
