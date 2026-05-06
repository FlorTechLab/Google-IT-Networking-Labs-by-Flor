# LAB – Diseño de Red Inalámbrica con DHCP

## 🎯 Objetivo
Diseñar e implementar una red inalámbrica distribuida utilizando múltiples Access Points, aplicando DHCP para asignación automática de direcciones IP y mejorando la cobertura mediante planificación de canales Wi-Fi.

---

## 🧩 Descripción
Este laboratorio simula un entorno de red en un edificio de varios pisos donde se requiere conectividad inalámbrica estable.

Se implementa una red con múltiples Access Points con el mismo SSID y diferentes canales para evitar interferencias, junto con un router que actúa como gateway y servidor DHCP.

---

## 🌐 Topología
- 4 PCs (PC1, PC2, PC3, PC4)
- 1 Switch
- 1 Router
- 4 Access Points (AP1, AP2, AP3, AP4)

**Flujo de red:**

PCs → Access Points → Switch → Router  

---

## 📡 Configuración de Access Points
- SSID: Empresa_WIFI  
- Seguridad: WPA2-PSK  
- Contraseña: Empresa123  

**Canales:**
- AP1 → Canal 1  
- AP2 → Canal 6  
- AP3 → Canal 11  
- AP4 → Canal 1  

---

## 🌍 Configuración del Router
- IP: 192.168.1.1  
- Máscara: 255.255.255.0  

---

## 🧠 DHCP (Router)
```bash
ip dhcp excluded-address 192.168.1.1
ip dhcp pool LAN
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8

```
## 💻 PCs
Configuradas en modo DHCP automático.

---

## 🔍 Pruebas
ping 192.168.1.1

✔ Resultado: conectividad exitosa
✔ Asignación automática de IP confirmada

---

## 📊 Análisis
Las PCs se conectan al Access Point más cercano
El switch centraliza el tráfico
El router actúa como gateway y servidor DHCP
Se valida conectividad completa de la red

___

## 🧪 Resultados
Red inalámbrica funcional
DHCP operativo
Distribución de canales sin interferencias
Comunicación entre todos los dispositivos

---

## 🧠 Conclusión

Este laboratorio permitió comprender el diseño de redes inalámbricas con múltiples Access Points, destacando la importancia de la planificación de canales y el uso de DHCP para automatizar la configuración de red.

El router cumple un rol clave como gateway y servidor de asignación de direcciones IP.

---

## ⚠️ Consideraciones de simulación
El roaming entre Access Points no es completamente realista
La selección del AP no siempre depende de la señal
La intensidad de señal no afecta totalmente la conexión
