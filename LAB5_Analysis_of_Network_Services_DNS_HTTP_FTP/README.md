# LAB5 – Análisis de Servicios de Red (DNS, HTTP, FTP)

## Descripción
Este laboratorio analiza el funcionamiento de múltiples servicios de red en un mismo servidor dentro de una red local utilizando Cisco Packet Tracer.

Se configuraron y analizaron los siguientes servicios:
- DNS (resolución de nombres)
- HTTP (acceso web)
- FTP (transferencia de archivos)

Mediante Simulation Mode se observaron los paquetes intercambiados entre el cliente y el servidor.

---

## Topología
La red está compuesta por:
- 1 PC (cliente)
- 1 Switch Cisco 2960
- 1 Server

Todos los dispositivos se encuentran en la misma red local (LAN).

---

## Servicios configurados

| Protocolo | Puerto | Transporte |
|----------|-------|-----------|
| DNS      | 53    | UDP       |
| HTTP     | 80    | TCP       |
| FTP      | 21    | TCP       |

---

## Análisis realizado

Se analizaron los siguientes procesos:

### DNS
Resolución del dominio `www.test.local` a dirección IP.

### HTTP
- Three-way handshake (SYN, SYN-ACK, ACK)
- Envío de solicitud HTTP

### FTP
- Autenticación (USER / PASS)
- Comando `LIST` para ver archivos

### Event List
Observación de la secuencia completa:
DNS → TCP → HTTP

---

## Resultados

- Resolución DNS exitosa  
- Conexión HTTP establecida  
- Autenticación FTP correcta  
- Listado de archivos obtenido  
- Identificación de puertos  
- Análisis de paquetes en Simulation Mode  

---

## Conclusión

El laboratorio permitió comprender cómo interactúan los protocolos de aplicación (DNS, HTTP, FTP) con los protocolos de transporte y el uso de puertos en una comunicación cliente-servidor.
