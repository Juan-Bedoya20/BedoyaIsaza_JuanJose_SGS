# Práctica UD3 – Implantación y uso del ERP Odoo  
Autor: Juan José Bedoya Isaza  

---

## 1. Formas de instalación de Odoo  

### • Instalación local (Windows/Linux)
Consiste en instalar Odoo directamente en el equipo para pruebas o desarrollo.

**Windows:**
- Descargar el instalador `.exe`.

**Linux (Ubuntu):**
- Instalar dependencias (PostgreSQL, Python, librerías).
- Instalar paquete `.deb` o desde repositorio.
- Configurar usuario, servicio y archivo `odoo.conf`.

---

### • Instalación en servidor (Ubuntu recomendado)
Se usa un servidor dedicado o virtual.

Pasos:
1. Instalar PostgreSQL, Python y dependencias.
2. Clonar Odoo o instalar paquetes.
3. Configurar servicio, `odoo.conf`, rutas de addons.
4. Configurar Nginx/Apache como proxy inverso.

---

### • Uso en la nube mediante Odoo Online (SaaS)
No requiere instalación local.  
Aporta:
- Base de datos gestionada por Odoo.
- No permite módulos personalizados.

---

### • Instalación mediante Docker
Se despliega Odoo con contenedores (generalmente junto con PostgreSQL).

Pasos:
1. Instalar Docker y Docker Compose.
2. Crear `docker-compose.yml`.
3. Configurar volúmenes y puertos.
4. Ejecutar `docker-compose up -d`.

---

### • Instalación desde código fuente (GitHub)
Ideal para desarrollo avanzado.

Pasos:
1. Clonar repositorio:  
   `git clone https://github.com/odoo/odoo.git`
2. Instalar dependencias Python.
3. Configurar PostgreSQL.
4. Ejecutar `odoo-bin` con parámetros.

---

## 2. Instalación práctica (dos métodos)

### **Instalación en servidor (Miguel y César)**  
- Ubuntu Server  
- RAM: 2048 MB  
- Se actualiza el sistema, se instala Python, PostgreSQL y dependencias.  
- Se configura `odoo.conf`, se crean usuarios y bases de datos.  
- Finalmente se inicia el servicio Odoo y se accede vía navegador.

---

### **Instalación con Docker (David y Juanjo)**
- VM con 4 GB RAM y 2 CPUs.  
- Se instala Docker + Docker Compose.  
- Se crea estructura de directorios.  
- Se genera `docker-compose.yml`.  
- Se lanzan contenedores y se valida su funcionamiento.

---

### **Instalación desde código fuente (Oscar)**
- Instala Python, PostgreSQL y Git.  
- Clona repositorio Odoo.  
- Crea entorno virtual.  
- Instala dependencias con `pip install -r requirements.txt`.  
- Configura PostgreSQL, base de datos y usuario Odoo.  
- Inicia entorno y accede al login.

---

### **Instalación local en Linux (Rubén)**
- Ubuntu Server en VM.  
- Instala Python, pip3, nodejs, PostgreSQL, librerías adicionales.  
- Configura `odoo.conf`.  
- Inicia Odoo, crea usuario admin, instala módulos y prueba mensajería.

---

### **Odoo Online SaaS (varios miembros del grupo)**
Requisitos mínimos:
- CPU 2 núcleos, RAM 4GB, navegador actualizado.

Proceso:
- Entrar en odoo.com  
- Crear base de datos (con prefijo `edu-` para 10 meses free).  
- Seleccionar módulos gratuitos o de prueba.  

---

## 3. Configuración de compañía
Incluye:
- Nombre  
- Dirección  
- CIF/NIF  
- Teléfono  
- Email  
- Logo  

Todo gestionado desde **Ajustes → Compañías → Nuevo**.

---

## 4. Creación e invitación de usuario
Ruta:
**Configuración → Usuarios y empresas → Usuarios → Crear**

Se introduce:
- Nombre  
- Correo  
- Rol  
Odoo envía invitación automática por e-mail.

---

## 5. Comunicación interna
Usando módulo **Conversaciones (Discuss)**:
- Menú → Mensajes directos  
- Chat entre administrador y nuevo usuario  
- Intercambio de varios mensajes  

---

## 6. Creación de canal interno
Se crea el canal “ies_canal”.  
- Se añaden participantes.  
- Se publica un mensaje de bienvenida.

---

## 7. Gestión de empresas y contactos
Crear nueva empresa y asignarla a un contacto desde:
**Usuarios → Permisos de acceso → Compañías**

---

## 8. Instalación de módulos funcionales
Desde Aplicaciones:
- Ventas  
- Compras  
- Almacén  
- TPV  

En SaaS se instalan desde el panel web.

---

## 9. Puerto de escucha de Odoo
- **Puerto por defecto:** `8069`
- Para cambiarlo:  
  `python odoo-bin --http-port=8070`

---

## 10. Cambio de base de datos
Odoo permite gestionar varias BD.

**Gestor de bases de datos:**  
En la pantalla de inicio → “Administrar bases de datos”

Operaciones:  
- Crear  
- Duplicar  
- Eliminar  
- Cambiar entre ellas  

---

## 11. Acceso a BD con herramienta visual
Herramienta usada: **DBeaver**

Pasos:
1. Instalar DBeaver.  
2. Crear conexión → PostgreSQL.  
3. Introducir credenciales de BD Odoo.  
4. Ver tablas y estructura.

---

## 12. Consulta SQL sobre res_partner

```sql
SELECT
    name,
    street,
    zip,
    city,
    phone,
    credit_limit
FROM res_partner;
