# Laboratorio de Troubleshooting DNS

## Descripción General

Este laboratorio demuestra técnicas básicas de troubleshooting de redes utilizando Cisco Packet Tracer.

El entorno incluye una PC cliente, un router configurado como servidor DHCP y un servidor DNS/Web. El laboratorio se enfoca en validar conectividad IP, resolución DNS y troubleshooting de problemas relacionados con DNS utilizando herramientas comunes de diagnóstico de red.

---

## Objetivos

- Configurar DHCP en un router
- Configurar servicios DNS y HTTP en un servidor
- Verificar conectividad de red utilizando ICMP
- Probar resolución de nombres DNS
- Simular y solucionar fallos DNS
- Analizar el comportamiento de la red utilizando herramientas de diagnóstico

---

## Tecnologías Utilizadas

- Cisco Packet Tracer
- DHCP
- DNS
- ICMP
- IPv4
- HTTP
- ping
- nslookup
- tracert

---

## Topología de Red

```text
PC1 → SW1 → R1 → Server1
```

<img width="1126" height="720" alt="image" src="https://github.com/user-attachments/assets/e9e0982c-5929-44fb-a762-3958225abe74" />

### Dispositivos

| Dispositivo | Función |
|---|---|
| PC1 | Dispositivo cliente |
| SW1 | Switch capa 2 |
| R1 | Router / Servidor DHCP |
| Server1 | Servidor DNS y HTTP |

---

## Esquema de Direccionamiento IP

| Dispositivo | Dirección IP |
|---|---|
| R1 | 192.168.10.1 |
| Server1 | 192.168.10.10 |
| PC1 | Asignada por DHCP |

---

## Configuración del Router

### Configuración de la Interfaz

```bash
enable
configure terminal

interface g0/0
ip address 192.168.10.1 255.255.255.0
no shutdown
exit
```

### Configuración DHCP

```bash
ip dhcp excluded-address 192.168.10.1

ip dhcp pool LAN
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 192.168.10.10
```

---

## Configuración del Servidor

### Configuración IP Estática

| Configuración | Valor |
|---|---|
| Dirección IP | 192.168.10.10 |
| Máscara de Subred | 255.255.255.0 |
| Gateway Predeterminado | 192.168.10.1 |
| Servidor DNS | 192.168.10.10 |

### Servicios Habilitados

- DNS
- HTTP

### Registro DNS

| Dominio | Dirección IP |
|---|---|
| empresa.com | 192.168.10.10 |

---

## Configuración del Cliente

La PC1 fue configurada en modo DHCP para recibir automáticamente:

- Dirección IP
- Máscara de subred
- Gateway predeterminado
- Servidor DNS

### Comando de Verificación

```bash
ipconfig
```

---

## Pruebas de Conectividad

### Prueba de Conectividad ICMP

```bash
ping 192.168.10.10
```

### Prueba de Resolución DNS

```bash
nslookup empresa.com
```

### Conectividad Utilizando Nombre de Dominio

```bash
ping empresa.com
```

### Trazado de Ruta

```bash
tracert empresa.com
```

---

## Simulación de Fallo DNS

Se simuló un problema DNS configurando manualmente un servidor DNS incorrecto en la PC cliente.

### Ejemplo de DNS Incorrecto

```text
1.1.1.1
```

### Resultado

```bash
nslookup empresa.com
```

Resultado:
- Timeout en la solicitud DNS
- Fallo en la resolución de nombres

Sin embargo:

```bash
ping 192.168.10.10
```

continuó funcionando correctamente.

Esto demuestra la diferencia entre:
- Problemas de conectividad IP
- Problemas de resolución DNS

---

## Proceso de Troubleshooting

### Problema

El cliente no podía acceder a recursos internos utilizando nombres de dominio.

### Causa Raíz

Configuración incorrecta del servidor DNS.

### Solución

La configuración DNS fue restaurada a:

```text
192.168.10.10
```

Luego de corregir la configuración DNS:

```bash
nslookup empresa.com
ping empresa.com
```

volvieron a funcionar correctamente.

---

## Conceptos Clave Aprendidos

- Asignación automática mediante DHCP
- Resolución de nombres DNS
- Pruebas de conectividad ICMP
- Metodología de troubleshooting de red
- Diferencia entre problemas de conectividad y DNS
- Trazado básico de rutas

---

## Habilidades Demostradas

- Configuración de routers
- Implementación de DHCP
- Configuración de servidores DNS
- Diagnóstico de redes
- Técnicas de troubleshooting
- Implementación de topologías en Cisco Packet Tracer

---

## Archivos del Proyecto

```text
dns-troubleshooting-lab/
│
├── README_EN.md
├── README_ES.md
│
├── dns-troubleshooting-lab_EN.pdf
├── dns-troubleshooting-lab_ES.pdf
│
├── dns-troubleshooting-lab.pkt
│
└── images/
```

---

## Notas

Cisco Packet Tracer posee ciertas limitaciones en comparación con entornos reales.

Algunas herramientas avanzadas y comportamientos de red pueden diferir respecto a sistemas operativos y redes empresariales reales. Sin embargo, el simulador proporciona un excelente entorno para aprender fundamentos de redes y conceptos de troubleshooting.
