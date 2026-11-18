# Tarjeta digital · Dr. Gervi, Ginecólogo

Página tipo tarjeta de presentación digital. Se abre al escanear un QR (tarjeta física o digital) y funciona en celular como una pantalla de iPhone: foto, datos de contacto, redes y un botón grande de **Agendar cita** a la altura del pulgar.

Es un sitio estático (HTML + CSS, sin librerías ni fuentes externas), pensado para publicarse gratis con **GitHub Pages**.

## Estructura

```
index.html            Página principal (aquí se editan los enlaces)
css/styles.css        Estilos
contacto.vcf          Contacto que se descarga con el botón "Guardar"
assets/doctor.webp    Foto del doctor (PROVISIONAL, cambiar por la real)
assets/logo.webp      Logo (G + útero + corazón)
assets/favicon.png    Ícono de la pestaña
assets/apple-touch-icon.png  Ícono al agregar a pantalla de inicio
.nojekyll             Le dice a GitHub Pages que no procese el sitio
```

## Qué falta editar

Busca `TODO` en `index.html`.

| Qué | Dónde |
|---|---|
| Número de WhatsApp (`52` + 10 dígitos, sin espacios) | `index.html`: botones **Escríbeme** y **Agendar cita** |
| Usuario de TikTok | `index.html`: reemplazar `USUARIO_TIKTOK` |
| Ubicación del consultorio | `index.html`: botón **Ubicación**. En Google Maps: Compartir → Copiar enlace |
| Cédula profesional | `index.html`: al final del panel |
| Teléfono y datos del contacto | `contacto.vcf` |
| Foto real del doctor | Reemplazar `assets/doctor.webp` |
| Flujo real de **Agendar cita** | `index.html`: por ahora abre WhatsApp con un mensaje listo |

### Sobre la foto

La foto actual es provisional. La que se ponga debe estar **recortada sin fondo** (PNG o WebP con transparencia), vertical, con la cara en la parte de arriba. El panel blanco tapa de la cintura para abajo. Si se cambia el tamaño o la proporción, ajustar `.hero__doctor` en `css/styles.css`.

### Sobre el logo

`assets/logo.webp` es pequeño (344 px). Para una versión final conviene reemplazarlo por el PNG grande o el SVG original.

## Publicar en GitHub Pages

1. Crear un repositorio nuevo en GitHub (por ejemplo `tarjeta-dr-gervi`).
2. Subir **el contenido** de esta carpeta a la raíz del repositorio, de modo que `index.html` quede en la raíz.
3. En el repositorio: **Settings → Pages**.
4. En **Build and deployment**, elegir **Deploy from a branch**, rama `main` y carpeta `/ (root)`. Guardar.
5. Esperar uno o dos minutos. La página queda en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.

Para usar un dominio propio, se configura en la misma pantalla de Pages (**Custom domain**).

## QR y NFC

- **QR:** generarlo con la URL final de la página. Conviene hacerlo después de tener la dirección definitiva (si cambia el repo o el dominio, el QR deja de servir).
- **NFC (fase posterior):** el chip se programa con esa misma URL, así que esta página no necesita cambios.

## Pruebas rápidas

Abrir `index.html` directamente en el navegador sirve para ver el diseño. Para probar como en producción:

```
python3 -m http.server 8000
```

y abrir `http://localhost:8000`.
