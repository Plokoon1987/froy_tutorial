# Configuración Básica de acceso Headless

Este manual describe cómo configurar los sistemas operativos basados en Linux para configurar el acceso a Internet de estos
y habilitar el acceso remoto a ellos. 

## Requisitos:
  - Tarjeta MicroSD con Raspbian (u otra distribución Linux) instalado en ella. 

## Pasos a seguir:
  - Insertar la tarjeta MicroSD en el ordenador
  - Configura acceso a la red local:
  
    Accede al archivo wpa_suplicant con el editor "Nano" usando:

    `sudo nano /media/<USERNAME>/rootfs/etc/wpa_supplicant/wpa_supplicant.conf`

    - Nota: ¡Ojo! Reemplazar en el comando anterior `<USERNAME>` por el nombre del usuario realizando la configuración

    Dirígete a la parte inferior del documento y añade lo siquiente:
     <pre>
     network={
         ssid="Network_SSID"
         psk="Network_Password"
     }
     </pre>

    - Nota: Para guardar y salir de "nano" pulsa <kbd>Ctrl</kbd>+<kbd>x</kbd>. A continuación pulsa <kbd>y</kbd>
            para confirmar y <kbd>Enter</kbd> para guardar

  - Habilita Acceso remoto mediante SSH:
  
    Crea un archivo vacío dentro de la carpeta "boot" llamado "ssh"

    `sudo touch /media/<USERNAME>/boot/ssh`

    - Nota: ¡Ojo! Reemplazar en el comando anterior `<USERNAME>` por el nombre del usuario realizando la configuración

  - Inserta la tarjeta MicroSD en la Raspberry Pi y encidelá. Debería conectarse automáticamente a la Red Local asignada.

## Referencias:
Ref_01: https://www.raspberrypi.org/documentation/configuration/wireless/headless.md

Ref_02: https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md

Ref_03: https://www.raspberrypi.org/documentation/remote-access/ssh/README.md#3-enable-ssh-on-a-headless-raspberry-pi-add-file-to-sd-card-on-another-machine
