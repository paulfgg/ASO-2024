# Guía para la Instalación y Configuración de OpenLDAP en Ubuntu

## Pasos Previos

1. **Configuración de Máquinas Virtuales:**
   - Antes de empezar, crea dos máquinas virtuales: una funcionará como servidor y la otra como cliente.
   - En el servidor, instala dos tarjetas de red:
     - Una en "Adaptador en puente" para la conexión a Internet.
     - Otra en "Red interna", ya que el servidor se configurará como un router Linux para la red interna.
![1](img/1.png)
![2](img/2.png)
![3](img/3.png)
   Este comando configura iptables para que todos los paquetes salientes a través de la interfaz enp0s3 usen la IP pública       de esa interfaz, permitiendo que una red local comparta una conexión a Internet mediante NAT.
      - t nat: Usa la tabla nat para traducción de direcciones de red.
      - A POSTROUTING: Añade la regla en la cadena POSTROUTING, aplicándose a paquetes salientes.
      - o enp0s3: La regla se aplica a la interfaz de salida enp0s3.
      - j MASQUERADE: Realiza enmascaramiento, reemplazando la IP de origen con la IP de la interfaz de salida.
![4](img/4.png)
![5](img/5.png)
## Instalación de OpenLDAP en el Servidor

1. **Instalación de Paquetes LDAP:**
   - Actualiza la lista de paquetes e instala el servidor OpenLDAP junto con las herramientas:
 
2. **Configuración Inicial de OpenLDAP:**
   - Durante la instalación de `slapd`, se te pedirá establecer una contraseña de administrador para LDAP.
   - Puedes reconfigurar el paquete en caso de error con:
   ![6](img/6.png)
   ![7](img/7.png)
   ![8](img/8.png)
   ![9](img/9.png)
   ![10](img/10.png)
## Creación de Estructura LDAP

1. **Creación del archivo LDIF para Unidades Organizativas (OU):**
   - Genera un archivo `.ldif` para definir las Unidades Organizativas (OU) necesarias. Este archivo puede tener el siguiente contenido de
   ![11](img/11.png)
   ![12](img/12.png)
   ![13](img/13.png)
2. **Creación de Grupos:**
   - Basándote en la plantilla anterior, crea los grupos necesarios en un archivo LDIF. Un ejemplo para un grupo puede ser:
  ![14](img/14.png)
  
   - Añade los grupos con:
    
   ![15](img/15.png)
   Este comando ldapadd se usa para agregar entradas al directorio LDAP
      
      - x: Usa autenticación simple en lugar de SASL (Simple Authentication and Security Layer).
      - D cn=admin,dc=pfgLDAP,dc=local: Especifica el DN (Distinguished Name) del usuario administrador, en este caso               - cn=admin,dc=pfgLDAP,dc=local, quien realiza la operación.
      - W: Solicita la contraseña del usuario especificado para autenticación.
      - f: Indica el archivo que contiene las entradas LDAP a agregar.
   
4. **Creación de Usuarios:**
   - Define cada usuario en un archivo LDIF. Aquí un ejemplo:
   ![16](img/16.png)
   ![17](img/17.png)
   ![18](img/18.png)
   - Añade cada usuario con:
   ![19](img/19.png)

## Verificación de Usuarios

1. **Comprobación con `ldapsearch`:**
   - Para verificar que un usuario se ha añadido correctamente, utiliza:
   ![20](img/20.png)
## Configuración en el Cliente

1. **Instalación LDAP en el Cliente:**
 
![21](img/21.png)
![22](img/22.png)
2. **Ahora configuraremos dos archivos de esta forma:**
Ahora configuraremos dos archivos de esta forma:

![23](img/23.png)
![24](img/24.png)
