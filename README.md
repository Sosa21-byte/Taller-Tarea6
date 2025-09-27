# Taller-Tarea6
## 🍓 Primer acercamiento a la raspberry pi 3 
 
🧷Instalación y manejo de Raspbian            
Descargar Raspberry Pi OS (Raspbian).

🧷Instalar en microSD usando Raspberry Pi Imager.
Primer arranque: configuración básica (Wi-Fi, idioma, actualización).
Manejo: se usa como un mini-computador con escritorio Linux; también puede accederse por SSH o VNC.
Dashboard sencillo en Streamlit

🧷Instalar Python y streamlit.
Crear un archivo .py con código básico para visualizar datos (ej: tabla, gráfico simple).
Ejecutar con streamlit run archivo.py y ver el dashboard en el navegador.
Exploración con Grafana

🧷Instalar Grafana en la Raspberry.
Conectar Grafana a una fuente de datos simple 
Crear un dashboard básico con un gráfico .
 
 # espacio codigo de instalacion 

 # espacio pantallazos de la instalacion 


 # 🤖 ¿Qué es cron?
  

Es un servicio de Linux que ejecuta procesos de forma automática en horarios o intervalos definidos.

Funciona en segundo plano y revisa constantemente si hay tareas programadas para ejecutarlas.


# 👾 ¿Qué es crontab?

Es el archivo de configuración donde se guardan las tareas (jobs) que cron debe ejecutar.


# Seccion de los ejemplos =

🔹 Ejemplo 1: Usando Cron

⏰ Idea: ejecutar un script cada minuto que guarde la hora en un archivo (como un mini-log de reloj).
```bash
Crear script hora.sh:

#!/bin/bash
date >> /home/pi/hora.log


Abrir Cron con:

crontab -e


Agregar al final:

* * * * * /home/pi/hora.sh

```

🧠 Explicacion de lo que se hace :

[* * * * *] = cada minuto

Ejecuta el script → escribe la hora en hora.log.

Sirve para llevar registro automático de eventos sin que uno esté pendiente.


🔹 Ejemplo 2: Usando crontab para un comando directo

📴 Idea: apagar el PC todos los días a las 11:00 p.m.

```bash
Editar cron:

crontab -e


Agregar:

0 23 * * * /sbin/shutdown now
```

🧠 Explicacion de lo que se hace :

0 23 * * * = a las 23:00 todos los días.

Ejecuta shutdown now.

Sirve para automatizar rutinas diarias (apagar, respaldar, limpiar, etc.).

# 📊 Diferencias cron y crontab

| Aspecto | Ejemplo 1 (Script con cron)              | Ejemplo 2 (Comando directo en crontab)       |
| ------- | ---------------------------------------- | -------------------------------------------- |
| Forma   | Llama un **script** externo              | Ejecuta un **comando directo**               |
| Uso     | Cuando la tarea es más larga o compleja  | Cuando la tarea es corta y simple            |
| Ejemplo | Guardar logs, hacer respaldos, monitoreo | Apagar PC, enviar alerta, limpiar temporales |
| Ventaja | Reutilizas el script en otros lugares    | Más rápido y directo, sin archivos extra     |


💬 En conclusión:

cron = el sistema que ejecuta cosas en segundo plano.

crontab = la agenda donde apuntas qué ejecutar (sea un script o un comando directo).

# Visualizar el entorno de red del pc, explorando la IP, vecinos cercanos, exploración de puertos y visión de una posible auditoría de red.

Comandos imprescindibles 

```bash IP y interfaces:
 ip addr show — o hostname -I
```
```bash Puerta de enlace/ruta:
ip route show
```
```bash Vecinos/ARP:  
ip neigh show — o arp -a
```
```bash Hosts activos (ping-scan): 
nmap -sn 192.168.1.0/24
```
```bash Puertos locales que escuchan:
 ss -tuln — o sudo lsof -i -P -n
```
```bash Escaneo de puertos :
 nmap --top-ports 100 192.168.1.37
```

```bash Captura de paquetes: 
sudo tcpdump -i eth0 -w captura.pcap 
```
