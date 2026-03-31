# LAB6 – Troubleshooting de Servicios de Red (DNS, HTTP, FTP)

## Descripción
Este laboratorio tiene como objetivo identificar y solucionar fallas en distintos servicios de red dentro de una red local utilizando Cisco Packet Tracer.

Se trabajó con los servicios DNS, HTTP y FTP configurados en un mismo servidor. A diferencia del laboratorio anterior, en este laboratorio se provocaron fallas intencionales para aplicar técnicas de troubleshooting y analizar el comportamiento de la red utilizando Simulation Mode.

---

## Topología
La red está compuesta por:
- 1 PC (cliente)
- 1 Switch Cisco 2960
- 1 Server

Todos los dispositivos se encuentran en la misma red local (LAN).

---

## Servicios analizados

| Protocolo | Puerto | Transporte |
|----------|-------|-----------|
| DNS      | 53    | UDP       |
| HTTP     | 80    | TCP       |
| FTP      | 21    | TCP       |

---

## Escenarios de falla

### Escenario 1 – DNS Fail
- Error en la configuración del servidor DNS en la PC.
- El ping a la IP funcionaba.
- El ping al dominio fallaba.
- Se corrigió la dirección DNS y el problema se solucionó.
- En Simulation Mode se observó el proceso de resolución DNS.

### Escenario 2 – HTTP Fail
- El servicio HTTP estaba desactivado en el servidor.
- Había conectividad (ping correcto) pero la página web no cargaba.
- Se activó el servicio HTTP y el acceso web volvió a funcionar.
- En Simulation Mode se observó la conexión TCP y el intento de acceso HTTP.

### Escenario 3 – FTP Fail
- El usuario podía iniciar sesión pero no listar archivos.
- Error: 550 Permission denied.
- El permiso LIST estaba desactivado.
- Se activó el permiso LIST y el problema se solucionó.
- En Simulation Mode se observó el comando FTP LIST y la respuesta del servidor.

---

## Análisis en Simulation Mode
Se analizaron los siguientes procesos:
- Resolución DNS
- Conexión TCP (Three-way handshake)
- Solicitud HTTP
- Autenticación FTP
- Comando FTP LIST
- Respuestas del servidor ante errores

---

## Resultados

- Identificación de fallas de DNS, HTTP y FTP
- Diagnóstico de problemas de red
- Solución de errores de configuración
- Análisis de paquetes en Simulation Mode
- Uso de técnicas de troubleshooting

---

## Conclusión

Este laboratorio permitió comprender cómo detectar y solucionar fallas en servicios de red. Se comprobó que los errores pueden estar relacionados con la configuración DNS, el estado de los servicios o los permisos de usuario.

El uso de Simulation Mode permitió analizar el tráfico de red y entender el funcionamiento de los protocolos DNS, HTTP y FTP durante el proceso de troubleshooting.
