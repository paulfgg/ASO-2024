# Actividad 0.4: Opciones de Adaptadores de Red en VirtualBox

Resumen de las principales opciones de adaptadores de red:

## Opciones:
1. **NAT**: Acceso a Internet sin visibilidad en la red local.
2. **Bridged Adapter**: Conexión directa a la red del host, visible en red local.
3. **Internal Network**: Comunicación entre VMs sin acceso a Internet.
4. **Host-Only Adapter**: Conexión solo entre VM y host.
5. **NAT Network**: VMs con acceso a Internet y entre ellas.

## Tabla Comparativa

| **Opción**          | **Internet** | **Visible en Red Local** | **Comunicación entre VMs** | **Aplicación Típica**         |
|---------------------|--------------|--------------------------|----------------------------|-------------------------------|
| **NAT**             | Sí           | No                       | No                         | Acceso a Internet solo         |
| **Bridged Adapter** | Sí           | Sí                       | No                         | Pruebas de red local           |
| **Internal Network** | No           | No                       | Sí                         | Redes locales simuladas        |
| **Host-Only Adapter**| No           | No                       | Sí                         | Conexión VM-host               |
| **NAT Network**     | Sí           | No                       | Sí                         | Laboratorios con múltiples VMs |


## Referencias
- [VirtualBox User Manual](https://www.virtualbox.org/manual/)