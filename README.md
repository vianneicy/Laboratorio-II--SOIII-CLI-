# Laboratorio-II--SOIII-CLI-
CLI Laboratorio 2.1; Gestión de Paquetes y Directorios, Rocky Linux.txt
Comandos utilizados, práctica laboratorio 2.1: Gestión de Paquetes y Directorios, Rocky Linux.

============================================



*/ Actualizar los paquetes y directorios, y descargar nuevas versiones:

sudo dnf update && upgrade

*/ Ver la lista de repositorios existentes:

dnf repolist

*/ Buscar una herramienta dentro de los repositorios y paquetes del sistema (Bashtop):

dnf search bashtop

*/ Instalar las herramientas EPEL (Extra Packages for Enterprise Linux)

sudo dnf install epel-release -y

*/ Instalar la herramienta Bashtop, si se encuentra en los paquetes EPEL;

sudo dnf install bashtop -y

*/ Si Bashtop no se encuentra, clonamos los repositorios de Git:

sudo git clone https://github.com/aristocratos/bashtop.git

*/ Nos posicionamos en el archivo clonado:

cd bashtop 

*/ Descargamos la herramienta:

sudo make install

*/ Si no tenemos la herramienta correspondiente para el comando "make install", la descargamos:

sudo dnf groupinstall "Development Tools" -y

*/ Luego de instalar, ejecutamos Bashtop:

bashtop

*/ Eliminamos la herramienta utilizando el administrador de paquetes (en caso de haberla instalado con el mismo):

sudo dnf remove bashtop -y

*/ Removemos archivos de configuración de la herramienta:

rm -rf ~/.config/bashtop

*/ Eliminando archivos residuales:

sudo dnf autoremove -y

*/ Eliminamos el binario principal de Bashtop si lo descargamos manualmente:

sudo rm -f /usr/local/bin/bashtop

*/ Buscamos más restos de la herramienta:

sudo find /usr/local -iname 'bashtop'

*/ Eliminamos los archivos residuales encontrados:

sudo rm -rf /usr/local/share/doc/bashtop
