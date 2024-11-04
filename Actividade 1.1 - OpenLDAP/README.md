# Guía para la Instalación y Configuración de OpenLDAP en Ubuntu

## Pasos Previos

1. **Configuración de Máquinas Virtuales:**
   - Antes de empezar, crea dos máquinas virtuales: una funcionará como servidor y la otra como cliente.
   - En el servidor, instala dos tarjetas de red:
     - Una en "Adaptador en puente" para la conexión a Internet.
     - Otra en "Red interna", ya que el servidor se configurará como un router Linux para la red interna.

## Instalación de OpenLDAP en el Servidor

1. **Instalación de Paquetes LDAP:**
   - Actualiza la lista de paquetes e instala el servidor OpenLDAP junto con las herramientas:
    
2. **Configuración Inicial de OpenLDAP:**
   - Durante la instalación de `slapd`, se te pedirá establecer una contraseña de administrador para LDAP.
   - Puedes reconfigurar el paquete en caso de error con:
 img

## Creación de Estructura LDAP

1. **Creación del archivo LDIF para Unidades Organizativas (OU):**
   - Genera un archivo `.ldif` para definir las Unidades Organizativas (OU) necesarias. Este archivo puede tener el siguiente contenido de 
2. **Creación de Grupos:**
   - Basándote en la plantilla anterior, crea los grupos necesarios en un archivo LDIF. Un ejemplo para un grupo puede ser:
  
   - Añade los grupos con:
    

3. **Creación de Usuarios:**
   - Define cada usuario en un archivo LDIF. Aquí un ejemplo:
    
   - Añade cada usuario con:
   

## Verificación de Usuarios

1. **Comprobación con `ldapsearch`:**
   - Para verificar que un usuario se ha añadido correctamente, utiliza:
   
## Configuración en el Cliente

1. **Instalación de Paquetes LDAP en el Cliente:**
 

2. **Prueba de Conexión al Servidor LDAP:**
   - Desde el cliente, intenta buscar usuarios para asegurar que la conexión es correcta:
     ```bash
     ldapsearch -x -LLL -H ldap://<IP_DEL_SERVIDOR> -b "dc=example,dc=com"
     ```

