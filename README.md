# TP - Computacion Aplicada

## Universidad de Palermo

---

### Integrantes

- Emiliano Figueroa
- Luis Martin Moltrasio
- Sofia Pilar del Pino
- Giuliano Adriel Demarchi
- Sosa Katelina

### De que trata

Trabajo practico grupal de Computacion Aplicada. Basicamente configuramos un servidor Debian desde cero en una maquina virtual: blanqueamos la contraseña de root, actualizamos de Debian 11 a 12, instalamos SSH con claves, levantamos Apache con PHP y MariaDB para servir una pagina con datos de alumnos, configuramos la red con IP estatica, particionamos un disco nuevo de 10GB para montar /www_dir y /backup_dir, armamos un script de backup automatizado con cron, y aca esta todo comprimido como pide la consigna.

### Contenido del repositorio

- root.tar.gz - directorio /root (home del superusuario, tiene las claves SSH y el material adicional)
- etc.tar.gz - directorio /etc (archivos de configuracion: red, apache, ssh, fstab, etc)
- opt.tar.gz - directorio /opt (script de backup y archivo de particiones)
- www_dir.tar.gz - directorio /www_dir (index.php y logo.png, montado sobre /dev/sdc1)
- backup_dir.tar.gz - directorio /backup_dir (backups generados, montado sobre /dev/sdc2)
- var.tar.gz.part\_\* - directorio /var (spliteado en partes de 25MB porque era muy pesado para subirlo entero)

### Como reconstruir /var

Si necesitan juntar las partes de /var de nuevo:
cat var.tar.gz.part\_\* > var.tar.gz
tar -xzf var.tar.gz

### Datos de la VM

- Hostname: TPServer
- SO: Debian 12 (Bookworm)
- IP estatica
- Contraseña root: palermo
- Servicios: SSH, Apache2, PHP 8.2, MariaDB
- Base de datos: ingenieria (con tablas alumnos, modulos, notas)
