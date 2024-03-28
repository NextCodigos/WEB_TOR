# WEB_TOR

# Guía para crear una página web en la Deep Web con Linux Mint

## Pasos

### 1. Preparación

* Crea un directorio para tu página web: `mkdir webtor`
* Introduce tu contenido web, como `index.html` y archivos CSS.
* Como usuario root, crea un servidor Python simple: `python3 -m http.server 80`
* Verifica que la página web se muestra correctamente en tu navegador local (localhost).

### 2. Instalación y configuración de Tor

* Actualiza e instala Tor: `apt update -y && apt install tor`
* Inicia el servicio Tor: `systemctl start tor`
* Verifica el estado del servicio: `systemctl status tor`
* Edita el archivo de configuración de Tor (`/etc/tor/torrc`):
    * Descomenta las siguientes líneas:
        * `#HiddenServiceDir /var/lib/tor/hidden_service/`
        * `#HiddenServicePort 80 127.0.0.1:80`
* Reinicia el servicio Tor: `systemctl restart tor`

### 3. Acceso a la página web en la Deep Web

* La página web estará disponible en la red Tor con una dirección `.onion`.
* Para obtener la dirección `.onion` de tu página web, ve a la carpeta `home` del usuario root y ejecuta: `cat /var/lib/tor/hidden_service/hostname`
* Copia la dirección `.onion` y ábrela en el navegador Tor.

### 4. Solución de problemas

* Si la página web no se muestra correctamente en Tor, asegúrate de que:
    * El servidor Python está funcionando correctamente.
    * La configuración de Tor es correcta.
    * Has copiado la dirección `.onion` correctamente.
* Si experimentas dificultades específicas en Linux Mint, consulta la siguiente información:
    * Asegúrate de tener la última versión de Tor instalada.
    * Revisa los permisos de los archivos y directorios relacionados con Tor.
    * Busca ayuda en foros o comunidades específicas de Linux Mint.
