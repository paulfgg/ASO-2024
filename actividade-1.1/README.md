# Actividad 1.1 - Administración básica de WS 2022

En esta actividad deberás realizar las siguientes tareas:

## 1. Instale Windows Server 2022 en una máquina virtual VirtualBox

Intenta seguir las convenciones comentadas en clase basadas en el documento "Gestión de VM con VirtualBox".

## 2. Elimina la necesidad de utilizar CTRL+ALT+DEL para ingresar credenciales y acceder al sistema.

1. Ve a **Herramientas administrativas**.
2. Abre el **Editor de directivas de seguridad local**.
3. Navega hasta **Políticas locales > Opciones de seguridad**.
4. Busca la opción **Inicio de sesión interactivo: no requerir CTRL+ALT+DEL** y habilítala.

#



## 3. Modificar las directivas de contraseñas

1. Abre el **Editor de directivas de grupo**.
2. Ve a **Configuración del equipo > Configuración de Windows > Configuración de seguridad > Directivas de cuenta > Directiva de contraseñas**.
3. Modifica la **vigencia mínima** a 15 días y la **vigencia máxima** a 60 días.

#



## 4. Agregue 3 nuevos usuarios al sistema: Larisa Shepitko, Bibi Andersson y Monica Vitti

1. Abre el **Administrador de usuarios y grupos locales**.
2. Crea 3 nuevos usuarios:
    - Larisa Shepitko
    - Bibi Andersson
    - Monica Vitti
3. Establece una contraseña para cada uno.
4. Verifica que puedan iniciar sesión.

#