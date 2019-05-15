# Installación de Raspbian

Este manual describe cómo instalar el Sistema Operativo "Raspbian" en una tarjeta MicroSD desde un Sistema Operativo Linux.

## Material necesario:
  - MicroSD Card
  - Sistema Operativo Raspbian (ver Ref_01)
    - Nota: Verifica la veracidad del archivo bajado con 'sha256sum'.
    
            i.e.: sha256sum <IMAGE_FILE> or sha256sum <ZIP_FILE>


## Pasos a seguir:

  - Insertar la tarjeta MicroSD en el ordenador

  - Verificar el nombre de la tarjeta:

    `lsblk`
    - Nota: Apunta el nombre de la MicroSD Card (Creo que el nombre para MicroSD no puede ser sda o sr0),
            Asumiremos que el nombre es CARD_NAME (i.e. ''mmcblk0')

  - Instalar Sistema Operativo:
  
    Si usas un fichero .zip sin descomprimir:
     
    `unzip -p <ZIP_FILE> | sudo dd of=/dev/<CARD_NAME> bs=4M status=progress conv=fsync`
    i.e.:

    `unzip -p 2018-06-27-raspbian-stretch-lite.zip | sudo dd of=/dev/mmcblk0 bs=4M status=progress conv=fsync`

    Si usas un fichero .img usa el comando:

    `dd bs=4M if=<IMAGE_FILE> of=/dev/<CARD_NAME> status=progress conv=fsync`

    i.e.:
  
    `sudo dd bs=4M if=2018-06-27-raspbian-stretch-lite.img of=/dev/mmcblk0 status=progress conv=fsync`

    - Nota: 'status=progress' muestra el progreso de la instalación. Si no se incluye el comando funcionará también pero no veremos el progreso


Ref_01: https://www.raspberrypi.org/downloads/

Ref_02: https://www.raspberrypi.org/documentation/installation/installing-images/linux.md
