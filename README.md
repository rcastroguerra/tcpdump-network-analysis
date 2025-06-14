# tcpdump Network Analysis
Summary and Examples of tcpdump and Network Traffic Analysis for Cybersecurity



## ¿Qué es tcpdump?

`tcpdump` es un analizador de protocolos de red de línea de comandos que captura y analiza el tráfico en una red. Es ligero, rápido y ampliamente usado en Linux y macOS.

## Funciones principales

- Captura paquetes de red en tiempo real.
- Muestra IP de origen y destino, puertos y protocolo.
- Ayuda a identificar tráfico sospechoso y ataques como DoS.

## Ejemplo de salida de tcpdump


```
12:45:03.456789 IP 192.168.0.5.53420 > 172.217.3.110.443: Flags [S], seq 0, win 65535, length 0
```


Explicación detallada:

1. 12:45:03.456789
- Marca de tiempo que indica el momento exacto en que se capturó el paquete.
- Formato: horas:minutos:segundos.microsegundos.
- En este caso, el paquete fue capturado a las 12 horas, 45 minutos, 3 segundos y 456,789 microsegundos.

2. IP
- Indica que el paquete es del protocolo IP (Internet Protocol).
- Esto significa que el paquete se está transmitiendo en una red basada en IP.

3. 192.168.0.5.53420
- Dirección IP de origen y puerto de origen del paquete.
- 192.168.0.5 es la IP del dispositivo que envía el paquete.
- 53420 es el puerto de origen desde donde se origina la conexión.
- Los puertos identifican aplicaciones o servicios en el dispositivo.

4. >
- El símbolo "mayor que" indica la dirección del tráfico.
- El paquete se envía desde la IP y puerto origen hacia la IP y puerto destino.

5. 172.217.3.110.443
- Dirección IP de destino y puerto de destino.
- 172.217.3.110 es la IP del dispositivo receptor.
- 443 es el puerto de destino, en este caso el puerto estándar para HTTPS (navegación web segura).

6. Flags [S]
- Muestra las banderas TCP activadas en el paquete.
- [S] significa SYN, usado para iniciar una conexión TCP.
- Este paquete intenta establecer una nueva conexión (inicio del "three-way handshake").

7. seq 0
- Número de secuencia del paquete TCP.
- 0 indica que es el primer paquete en la conexión.

8. win 65535
- Tamaño de la ventana TCP, que controla el flujo de datos.
- 65535 es un tamaño común que indica la cantidad máxima de datos que se pueden recibir sin confirmación.

9. length 0
- Longitud del segmento de datos en bytes.
- En este paquete no hay datos, solo señales para iniciar la conexión TCP.

## Resumen del paquete
Este paquete es un paquete TCP SYN enviado desde 192.168.0.5:53420 hacia 172.217.3.110:443. Es el primer paquete que intenta iniciar una conexión TCP entre estos dos hosts. No contiene datos, solo las señales necesarias para establecer la comunicación.


## Usos comunes

- Establecer patrones normales de tráfico.
- Detectar tráfico malicioso.
- Configurar alertas de seguridad.
- Localizar accesos no autorizados.

## Seguridad y consideraciones

- Herramienta para defensores y potencialmente para atacantes.
- Se debe usar con autorización para evitar problemas legales.

---


## Comandos útiles

- Capturar paquetes en la interfaz principal:
  ```bash
  sudo tcpdump -i eth0
  ```

- Capturar solo tráfico HTTP:
  ```bash
  sudo tcpdump -i eth0 port 80
  ```

- Guardar la captura en un archivo:
  ```bash
  sudo tcpdump -i eth0 -w captura.pcap
  ```

- Leer un archivo de captura:
  ```bash
  tcpdump -r captura.pcap
  ```

- Mostrar paquetes sin resolver nombres:
  ```bash
  tcpdump -n
  ```







