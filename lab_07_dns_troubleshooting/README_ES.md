# LAB 7 – Configuración y Troubleshooting de DNS

## Descripción
Este laboratorio tiene como objetivo configurar y diagnosticar el funcionamiento del servicio DNS dentro de una red local utilizando Cisco Packet Tracer.

Se trabajó con registros DNS (A y CNAME) y se simuló un escenario de falla para aplicar técnicas de troubleshooting y analizar el comportamiento de la red.

---

## Topología
La red está compuesta por:
- 1 PC (cliente)
- 1 Switch Cisco 2960
- 1 Server (DNS)

Todos los dispositivos se encuentran en la misma red local (LAN).

---

## Configuración DNS

Se configuraron los siguientes registros:

- **A Record**
  - www.test.local → 192.168.1.20

- **CNAME Record**
  - web.test.local → www.test.local

- **Round Robin (concepto)**
  - app.test.local → 192.168.1.20
  - app.test.local → 192.168.1.21

---

## Pruebas realizadas

- Resolución de dominio:
  - ping www.test.local

- Verificación de CNAME:
  - ping web.test.local

- Prueba de conectividad directa:
  - ping 192.168.1.20

---

## Escenario de falla – DNS

- Se configuró una dirección DNS incorrecta en la PC (192.168.1.99)
- El ping al dominio fallaba
- El ping a la IP funcionaba
- Se identificó que el problema era de resolución de nombres
- Se corrigió la configuración DNS en la PC

---

## Análisis

- La red tenía conectividad correcta
- El problema estaba en la resolución DNS
- El dominio no se resolvía correctamente debido a una mala configuración
- La prueba con IP permitió descartar problemas de red

---

## Resultados

- Comprensión del funcionamiento de DNS
- Configuración de registros A y CNAME
- Identificación de fallas en DNS
- Aplicación de troubleshooting básico
- Validación mediante pruebas de conectividad

---

## Conclusión

Este laboratorio permitió comprender cómo funciona el servicio DNS y cómo diagnosticar problemas relacionados con la resolución de nombres.

Se comprobó que una configuración incorrecta del DNS puede impedir el acceso a servicios, incluso cuando la red funciona correctamente.
