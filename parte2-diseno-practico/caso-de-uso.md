# Parte 2: Caso de Uso

**Nombre del estudiante: Vanesa**  
**Fecha:26/05/2026**

# Parte 2: Caso de Uso

**ID: CU-05**

**Nombre:"Suscripción a Categorías de Artículos" ** 

**Actor Principal: Usuario Registrado**

**Actores Secundarios: Servidor de Correo Electrónico**

## Descripción

El sistema permite que los usuarios registrados sigan categorías  de su interés. Al hacerlo, el sistema el envío de alertas cada vez que un nuevo contenido es publicado en dichas categorías, fomentando la recurrencia del usuario.

## Precondiciones

* El usuario debe haber iniciado sesión exitosamente.
* El usuario debe encontrarse en la sección de "Explorar Categorías" o dentro de una categoría específica.
* El sistema de notificaciones debe estar en línea.

## Flujo Principal

1. El Usuario Registrado selecciona una categoría de su interés.
2. El Usuario Registrado hace clic en el botón **"Suscribirse"** o **"Seguir"**.
3. El sistema valida que el usuario no tenga una suscripción activa previa a esa misma categoría.
4. El sistema registra la relación entre el ID del Usuario y el ID de la Categoría en la base de datos.
5. El sistema muestra un mensaje de confirmación: "Suscripción exitosa. Recibirás alertas de esta categoría".
6. Al publicarse un nuevo artículo, el sistema identifica a todos los usuarios suscritos.
7. El sistema envía las notificaciones correspondientes a través de los actores secundarios.

## Flujos Alternativos

### FA1: Cancelar Suscripción 

1. En el paso 2, si el sistema detecta que el usuario ya sigue la categoría, el botón muestra "Siguiendo".
2. El Usuario Registrado hace clic en "Siguiendo" para darse de baja.
3. El sistema elimina el registro de suscripción de la base de datos.
4. El sistema actualiza la interfaz y muestra: "Ya no sigues esta categoría".

### FA2: Configuración de Preferencias de Alerta

1. Antes del paso 4, el sistema despliega un menú de opciones de notificación.
2. El Usuario Registrado selecciona recibir únicamente notificaciones "Push" y desactiva "Correo Electrónico".
3. El sistema guarda la preferencia específica para esa categoría.
4. El flujo continúa en el paso 5.

## Postcondiciones

* El registro de suscripción queda persistido en la base de datos.
* Se genera un evento de auditoría en el log del sistema sobre la nueva suscripción.

-
