## Introducción y Arquitectura
Este manual explica cómo funciona el ERP, cómo se instala, cómo se mantiene y cómo se generan las facturas dentro del sistema de WillmanTech S.L.

El ERP está formado por:

1. **Un servidor donde se ejecuta la aplicación.

2. **Una base de datos donde se guardan clientes, facturas y ventas.

3. **Un sistema de plantillas que genera los informes en PDF.

**Arquitectura general**

El sistema funciona con contenedores Docker, que son como “cajas” separadas:

-Una caja para el ERP.

-Una caja para la base de datos.

-Archivos que se guardan de forma permanente para no perder datos.

Esto hace que el sistema sea fácil de instalar, actualizar y restaurar.

Principalmente nosotros hemos acyivado y utilizado los moduls de clientes, ventas y facturacion.

## Guía de Instalación y Reinstalación

**Requisitos básicos**

-Tener Docker instalado.

-Tener mysql: 

<img width="381" height="336" alt="image" src="https://github.com/user-attachments/assets/c68d6fdf-d317-4705-acb1-63b76c71c1b7" />


-Tener Docker Compose: 

<img width="715" height="731" alt="image" src="https://github.com/user-attachments/assets/92bd9cbe-35ff-4c26-9160-d2e7c511c7ff" />


**Instalación inicial**

-Descargar el proyecto.

-Ejecutar el comando para arrancar el sistema (en la terminal de vscode):

  docker compose up -d

Y para abrir el ERP en el navegador deveremos poner localhost: y el puerto que pona en el mysql

**Reinstalación**

Hay que poner estos dos comandos 

-docker compose down

-docker compose up -d

## Seguridad y Control de Acceso

El ERP utiliza roles para controlar el acceso:

Administrador: acceso total

Contable: facturas y datos económicos

Comercial: clientes y ventas

Contraseñas
Mínimo 10 caracteres

Deben incluir mayúsculas, minúsculas, números y símbolos

Recomendable cambiarlas cada 90 días

Privilegios
Comerciales: no pueden modificar facturas validadas

Contables: no pueden borrar clientes

Administradores: gestionan permisos

