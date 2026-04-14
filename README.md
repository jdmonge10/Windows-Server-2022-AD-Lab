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

---

## 📂 Fase 02: Instalación del Sistema Operativo
En esta etapa se realiza la instalación limpia de Windows Server 2022. Es el proceso donde se define la edición del servidor y se prepara el almacenamiento.

### Paso 2.1: Selección de Idioma y Comienzo
Se inicia el asistente de instalación configurando el idioma y el método de entrada del teclado.
![Idioma y Teclado](02-instalacion-sistema-operativo/01-idioma-teclado.png)

### Paso 2.2: Edición del Sistema
Se selecciona la versión **Windows Server 2022 Standard (Experiencia de escritorio)**. Esta versión es fundamental para este laboratorio ya que incluye la interfaz gráfica (GUI) necesaria para la administración visual.
![Selección de Edición](02-instalacion-sistema-operativo/03-seleccion-sistema-operativo.png)

### Paso 2.3: Configuración de Almacenamiento
Se realiza una instalación de tipo "Personalizada" para gestionar las particiones. Se asigna la totalidad del espacio del disco duro virtual creado previamente.
![Particionado de Disco](02-instalacion-sistema-operativo/06-particion-disco-duro.png)

### Paso 2.4: Configuración de Seguridad Inicial
Tras el primer arranque, se establece la contraseña de la cuenta de **Administrador**. Esta cuenta será, posteriormente, la que tenga privilegios totales sobre el dominio.
![Password Administrador](02-instalacion-sistema-operativo/10-password-administrador.png)

### Paso 2.5: Primer Inicio de Sesión
Verificación del escritorio de Windows Server 2022 y apertura automática del Administrador del Servidor para comenzar las tareas de configuración.
![Primer Inicio](02-instalacion-sistema-operativo/12-primer-inicio-sesion.png)


---

## 📂 Fase 03: Instalación de Guest Additions
Las *Guest Additions* de VirtualBox son esenciales para optimizar el rendimiento del servidor virtual, permitiendo una mejor resolución de pantalla y el uso de funciones compartidas.

### Paso 3.1: Montaje de la imagen de CD
Se utiliza la opción del menú de VirtualBox para insertar el disco virtual de las Guest Additions en la unidad óptica del servidor.
![Insertar Imagen](03-instalacion-guest-additions/01-insertar-imagen-guest-additions.png)

### Paso 3.2: Ejecución del instalador
Se accede a la unidad de CD montada y se ejecuta el asistente de instalación para los drivers de Windows.
![Asistente Inicio](03-instalacion-guest-additions/04-asistente-instalacion-inicio.png)

### Paso 3.3: Instalación de controladores
El asistente instala los controladores de vídeo, ratón y sistema necesarios para la integración con el host.
![Progreso Instalación](03-instalacion-guest-additions/07-progreso-instalacion-drivers.png)

### Paso 3.4: Finalización y Reinicio
Una vez completada la instalación, se requiere un reinicio del servidor para que los nuevos controladores se carguen correctamente.
![Reinicio Finalización](03-instalacion-guest-additions/08-finalizacion-y-reinicio.png)
