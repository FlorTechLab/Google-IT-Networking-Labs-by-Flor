# LAB4 – Web Session Analysis

**Course:** The Bits and Bytes of Computer Networking (Google)

**Author:** Florencia Horita

**Date:** 10/03/2026

---

## Descripción

Este laboratorio analiza el proceso completo de comunicación entre un cliente y un servidor web dentro de una red local utilizando Cisco Packet Tracer.

Se configuró un servidor con servicios DNS y HTTP para permitir que el cliente acceda a un sitio web mediante un nombre de dominio. Utilizando el modo **Simulation** de Cisco Packet Tracer se observaron los paquetes intercambiados entre los dispositivos, permitiendo analizar el funcionamiento de los protocolos **DNS, TCP y HTTP**.

---

## Objetivos

- Comprender el proceso de resolución de nombres mediante **DNS**.

- Analizar el establecimiento de una conexión **TCP** utilizando el **Three Way Handshake**.

- Observar el funcionamiento del protocolo **HTTP** en la solicitud de una página web.

- Identificar los puertos utilizados por cada servicio.

- Utilizar **Simulation Mode** en Cisco Packet Tracer para inspeccionar los paquetes de red.

---

## Topología de red

Red local simple compuesta por:

- 1 PC (Cliente)
- 1 Switch Cisco 2960
- 1 Server (DNS + HTTP)

Todos los dispositivos conectados dentro de la misma red LAN.

---

## Configuraciones principales

- **PC0**
  - Configurada con dirección IP dentro de la red local.
  - Configurado el servidor DNS para resolución de nombres.

- **Server0**
  - Servicio **DNS habilitado**
  - Registro A creado para resolver `www.test.local`
  - Servicio **HTTP habilitado**
  - Página principal modificada para mostrar el mensaje *Servidor Web Funcionando*

- **Switch 2960**
  - Conectividad básica entre los dispositivos de la red.

---

## Proceso observado

Durante la simulación se identificaron las siguientes etapas de comunicación:

1. **ARP Request / Reply**  
   El cliente obtiene la dirección MAC del servidor.

2. **DNS Query / Response**  
   El cliente consulta al servidor DNS para resolver el dominio `www.test.local`.

3. **TCP Three Way Handshake**
   - SYN
   - SYN-ACK
   - ACK

4. **HTTP Request**
   El cliente envía una solicitud HTTP al servidor para obtener la página web.

---

## Resultados

• Resolución de nombre exitosa mediante DNS.  

• Establecimiento correcto de la conexión TCP mediante el Three Way Handshake.  

• Solicitud HTTP enviada correctamente al servidor web.  

• Visualización completa del flujo de comunicación mediante Simulation Mode.

---

## Archivos incluidos

- **LAB4_WEB_SESSION_ANALYSIS_FLOR.pkt** → Proyecto de Cisco Packet Tracer  
- **LAB4_WEB_SESSION_ANALYSIS_FLOR.pdf** → Documentación técnica del laboratorio  
- **LAB4_WEB_SESSION_ANALYSIS_FLOR_EN.pdf** → Versión en inglés del laboratorio  

---

## Observación

Este laboratorio permitió analizar cómo los protocolos de **aplicación (DNS, HTTP)** y **transporte (TCP)** trabajan conjuntamente para permitir el acceso a servicios web en una red.

El uso del **Simulation Mode** en Cisco Packet Tracer permitió observar detalladamente cada paquete intercambiado durante el proceso de comunicación entre el cliente y el servidor.
