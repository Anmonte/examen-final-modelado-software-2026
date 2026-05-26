# Parte 1: Analisis Critico - Respuestas

**Nombre del estudiante: Vanesa**  
**Fecha:26/05/2026**



## Error 1

**Ubicación:** Descripción.

**Descripción:** **servidor**" para describir quién permite la acción del usuario.
**Corrección:** Cambiar la redacción a: "El **sistema** permite que el usuario cambie los datos de su perfil...".

---

## Error 2

**Ubicación:** Precondiciones.

**Descripción:** Se exige que el usuario tenga "al menos 50 seguidores" para editar su perfil. Esta es una restricción de negocio arbitraria que no tiene sentido funcional, ya que un usuario debe poder gestionar su información desde el momento del registro.

**Corrección:** Eliminar esta restricción. La precondición real debe ser que el usuario haya iniciado sesión y su perfil esté activo.

---

## Error 3

**Ubicación:** Flujo Principal - Paso 6.

**Descripción:** El sistema guarda la información de manera inmediata sin realizar una **validación previa** de los datos (como el formato del email) ni confirmar si el usuario realmente desea aplicar los cambios.

**Corrección:** Insertar un paso de validación: "El sistema valida que el formato de los datos sea correcto" antes de proceder con el guardado en la base de datos.

---

## Error 4

**Ubicación:** Postcondiciones.

**Descripción:** Se indica que se envía un email a **todos los seguidores** y se abre una **nueva sesión** en otro navegador. Esto representa una falla de diseño (spam innecesario) y un riesgo crítico de seguridad y comportamiento errático del sistema.

**Corrección:** Eliminar estas acciones. Las postcondiciones deben limitarse a la actualización exitosa de la base de datos y la confirmación al usuario.

---

## Error 5

**Ubicación:** Excepciones.

**Descripción:** La excepción indica que si el usuario no tiene permisos, el sistema "**no hace nada**". Esto deja al usuario en un estado de incertidumbre (bloqueado) sin retroalimentación sobre por qué falló la acción.

**Corrección:** Definir un mensaje de error claro y un punto de retorno: "El sistema muestra un mensaje de error y permite al usuario corregir los datos o volver a la pantalla anterior".

