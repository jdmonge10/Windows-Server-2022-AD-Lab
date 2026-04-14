# 🚀 Despliegue de Windows Server 2022 y Active Directory

Este manual documenta el proceso técnico integral para crear un entorno de servidor profesional, desde la virtualización hasta la configuración de un Dominio de Active Directory.

---

## 📂 Fase 01: Configuración de la Máquina Virtual (VirtualBox)
El primer paso fundamental es preparar el hardware virtual donde se alojará nuestro servidor. Una asignación correcta de recursos garantiza la estabilidad de los servicios de identidad.

### Paso 1.1: Creación y Ajustes de la VM
Se configura una máquina virtual con los siguientes parámetros técnicos:
* **Sistema Operativo:** Windows 2022 (64-bit).
* **Memoria RAM:** 4 GB (Mínimo recomendado para entorno gráfico y AD DS).
* **Procesador:** 2 núcleos de CPU para evitar latencia en procesos de fondo.
* **Red:** Modo Adaptador Puente para integración en la LAN.

![Configuración de hardware virtual](01-configuracion-virtualbox/01-configuracion-virtualbox.png)
