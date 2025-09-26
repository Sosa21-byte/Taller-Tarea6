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

# ejemplo de cron y crontab
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