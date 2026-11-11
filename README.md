# NanoSlice 0.7.1

Laminador FDM/FFF para navegador, diseñado para celular y escritorio. Procesa STL y genera G-code localmente con CuraEngine vía Cura WASM. No necesita un servidor de cálculo.

## Abrir en VS Code

1. Instalá Node.js 22 o superior y Git.
2. Extraé este ZIP y abrí la carpeta NanoSlice en VS Code.
3. Abrí Terminal → Nueva terminal y ejecutá:

```sh
npm ci
npm run build
npm test
npm start
```

Abrí http://localhost:8080. No abras index.html con doble clic. Para detener el servidor usá Ctrl+C. El servidor de desarrollo solo escucha en tu computadora.

## Subir a GitHub

Creá un repositorio vacío llamado NanoSlice, sin README ni licencia generados por GitHub. Desde esta carpeta ejecutá estos comandos, reemplazando TU_USUARIO por tu usuario:

```sh
git init
git add .
git commit -m "NanoSlice 0.7.1: versión inicial"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/NanoSlice.git
git push -u origin main
```

También podés usar GitHub Desktop: File → Add local repository, crear el repositorio si lo solicita y luego Publish repository. Elegí privado si querés limitar el acceso al código. El ZIP no incluye credenciales ni el historial Git del alojamiento anterior.

## Contenido

- `src/`: lógica, interfaz, materiales, impresoras y parámetros.
- `dist/`: app compilada y recursos locales, lista para un alojamiento estático.
- `tests/`: pruebas de geometría, G-code, parámetros, impresoras, filamentos y actualización.
- `scripts/`: generación de catálogos y servidor local.
- `source/upstream/`: fuentes y avisos de terceros.
- `.github/workflows/ci.yml`: compilación y pruebas en GitHub; no publica ningún sitio.
- `CHANGELOG.md`: historial técnico y verificaciones de versiones.

## Alcance

Incluye 11 familias genéricas de filamento, perfiles personalizados, catálogo de impresoras, parámetros avanzados, sugerencias de orientación y descarga de G-code. Los perfiles son puntos de partida para calibrar; no certifican compatibilidad física. El motor es una versión antigua de CuraEngine y no equivale al Cura de escritorio actual. Flujo de un extrusor y un material. Validación en teléfonos e impresoras físicos pendiente.

El uso offline requiere HTTPS o localhost, una primera descarga completa y almacenamiento conservado por el navegador. Cambiar de dominio no transfiere perfiles: exportalos a JSON e importalos en el nuevo dominio.

## Alojamiento futuro

Hostinger queda pendiente. La app usa rutas desde la raíz (`/`): está preparada para un dominio o subdominio propio. No está adaptada a GitHub Pages en una subcarpeta `/NanoSlice/`. No contiene la barrera de acceso de ChatGPT del alojamiento anterior; un hosting estático necesitará su propia protección si querés acceso privado.

## Licencias

Código de NanoSlice: AGPL-3.0-or-later. Se conserva el código y los avisos de terceros en `source/upstream/`. CuraEngine usa AGPL; las definiciones usan LGPL y el wrapper incluye partes MIT. Consultá THIRD_PARTY_NOTICES.md. Al distribuir cambios conservá los avisos y ofrecé las fuentes correspondientes.
