# Notion RPM Builder

Construye un paquete rpm para Redhat, utilizando los archivos desde el instalador de Notion para Windows o del paquete para macOS.

## Note: Probado en Fedora 32

## Paquete preconstruído

Ver [Releases](https://github.com/enmanuelmoreira/notion-rpm-builder/releases)

## Requerimientos

1. Instalar Node.js, e.g. con dnf:

   ```sh
   sudo dnf install nodejs
   ```

2. Instalar los paquetes `asar`, `electron-packager` and `electron-installer-redhat` y `electron-installer-debian` con npm:

   ```sh
   sudo npm -g install asar electron-packager electron-installer-redhat electron-installer-debian
   ```

3. Instalar `7z`, `convert`, `fakeroot` y `dpkg`.

   Redhat:

   ```sh
   sudo dnf install p7zip-plugins ImageMagick fakeroot
   ```

   macOS:

   ```sh
   brew install p7zip imagemagick fakeroot dpkg
   ```

4. Descargar la versión más reciente del instalador de Notion en Windows o macOS, como `notion.exe` o `notion.dmg` respectivamente, e.j. con wget:

   ```sh
   wget 'https://desktop-release.notion-static.com/Notion%20Setup%202.0.8.exe' -O notion.exe
   ```

# Build

Ejecutar el script:

```sh
./build.sh <platform>
```

reemplazar `<platform>` con `windows` o `mac`, dependiendo del instalador que se descargó previamente.

Una vez que haya finalizado la construcción, el paquete rpm debería encontrarse en el directorio `dist/installers`.
