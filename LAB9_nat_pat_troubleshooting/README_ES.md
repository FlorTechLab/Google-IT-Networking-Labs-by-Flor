# LAB 9 – Troubleshooting de NAT, Routing y ACL

## Objetivo
Diagnosticar y resolver problemas de conectividad en una red que utiliza routing estático, NAT, PAT y listas de control de acceso (ACL), aplicando un enfoque estructurado de troubleshooting.

---

## Descripción
En este laboratorio se simula un entorno real donde múltiples errores de configuración impiden la comunicación entre una red privada y un servidor externo.

El análisis se centra en identificar la causa raíz del problema y aplicar las correcciones necesarias para restablecer la conectividad.

---

## Topología
La red está compuesta por:

- 2 PCs (PC1 y PC2)
- 1 Switch
- 2 Routers (R1 y R2)
- 1 Servidor

Conectividad:

PC1 / PC2 → Switch → R1 → R2 → Servidor

---

## Configuración de red

### PCs
- PC1 → 192.168.1.10 / GW 192.168.1.1
- PC2 → 192.168.1.20 / GW 192.168.1.1

### Servidor
- IP → 200.0.0.2
- Gateway → 200.0.0.1

---

## Routing

- R1:
  - ip route 200.0.0.0 255.255.255.0 10.0.0.2

- R2:
  - ip route 192.168.1.0 255.255.255.0 10.0.0.1

---

## Configuración de NAT / PAT (R1)

### ACL
- access-list 1 permit 192.168.1.0 0.0.0.255

### Interfaces
- g0/0 → ip nat inside
- g0/1 → ip nat outside

### PAT
- ip nat inside source list 1 interface g0/1 overload

---

## Pruebas realizadas

- Ping al servidor  
- Verificación de NAT (`show ip nat translations`)  
- Verificación de routing (`show ip route`)  
- Verificación de ACL (`show access-lists`)  
- Verificación de interfaces (`show ip interface brief`)  

---

## Escenario de falla

- El ping hacia el servidor fallaba  
- No se observaban traducciones NAT  
- El tráfico no lograba salir del router  
- Se detectó falta de rutas estáticas  

---

## Resolución

Se aplicaron las siguientes correcciones:

- Corrección de la máscara en el enlace entre routers (/30)  
- Agregado de rutas faltantes en R1 y R2  
- Verificación de la configuración NAT (inside/outside)  
- Validación de la ACL  
- Verificación del estado de las interfaces  

---

## Verificación final

- Ping exitoso al servidor (con pérdida inicial de paquetes)  
- Traducciones NAT activas  
- Comunicación completa entre todos los dispositivos  

---

## Análisis

El problema principal estaba relacionado con routing, lo que impedía que el tráfico saliera correctamente del router.

Debido a esto, NAT no se aplicaba, ya que no había tráfico saliente que traducir.

Una vez corregidas las rutas, se restableció el flujo completo de comunicación y NAT comenzó a funcionar correctamente.

---

## Habilidades aplicadas

- Troubleshooting de redes  
- Configuración de NAT y PAT  
- Análisis de routing  
- Interpretación de comandos Cisco  
- Diagnóstico de problemas de conectividad  

---

## Resultados

- Comprensión del flujo de tráfico en la red  
- Identificación de problemas de routing  
- Validación del funcionamiento de NAT/PAT  
- Aplicación práctica de troubleshooting  

---

## Conclusión

Este laboratorio permitió aplicar técnicas de troubleshooting en un entorno realista, identificando y resolviendo errores de routing y configuración que impedían la conectividad.

Se reforzaron habilidades clave en diagnóstico, análisis y validación de redes.
