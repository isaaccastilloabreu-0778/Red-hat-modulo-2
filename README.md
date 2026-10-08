# Red-hat-modulo-2
comandos del modulo 2
1. Abrir el editor de tareas cron
crontab -
# 2. Línea para vaciar la carpeta /tmp diariamente a la medianoche (agregar dentro de crontab)
0 0 * * * /usr/bin/rm -rf /tmp/*

# 3. Programar una limpieza inmediata diferida para dentro de 1 minuto usando at
echo "/usr/bin/rm -rf /tmp/*" | at now + 1 minute

# 4. Verificar el estado de la tarea en la cola de ejecución
atq

# 5. Verificar el contenido actual de la carpeta temporal
ls -l /tmp
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
# 1. Mostrar dispositivos de almacenamiento conectados para identificar el nuevo disco (ej: /dev/nvme0n2)
lsblk

# 2. Formatear la partición con el sistema de archivos ext4
sudo mkfs.ext4 /dev/nvme0n2

# 3. Crear una carpeta en el directorio personal como punto de montaje
mkdir ~/mi_disco

# 4. Montar el nuevo disco en la carpeta creada
sudo mount /dev/nvme0n2 ~/mi_disco

# 5. Entrar al directorio del disco montado
cd ~/mi_disco

# 6. Crear un archivo de texto con tu nombre
touch AdrianAlcantara.txt

# 7. Regresar al directorio personal (necesario antes de desmontar)
cd ~

# 8. Desmontar el disco de forma segura
sudo umount ~/mi_disco

# 9. Volver a montar el mismo disco en la ruta del sistema /mnt
sudo mount /dev/nvme0n2 /mnt

# 10. Entrar al directorio /mnt
cd /mnt

# 11. Comprobar que el archivo continúa almacenado correctamente
ls -l
