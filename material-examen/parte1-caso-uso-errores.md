# Parte 1 del Examen: Analisis Critico

**Tiempo:** 20 minutos  
**Puntaje:** 20% del examen final

---

## Consigna

A continuacion se presenta un caso de uso con **7 errores intencionales**. Tu tarea es:

1. Identificar minimo 5 errores
2. Explicar por que es un error
3. Proponer la correccion apropiada

Usa este formato:

```text
ERROR #1:
Ubicacion: [Seccion donde esta el error]
Descripcion: [Que esta mal]
Correccion: [Como deberia ser]
```

---

## Caso de Uso con Errores
---

**CU-09: Editar Perfil de Usuario**

**Actor Principal:** Usuario Registrado


**Descripción:** El sistema permite al Usuario Registrado modificar su información personal (nombre, email, biografía) para mantener su perfil actualizado. 

**Precondiciones:**

* El usuario debe haber iniciado sesión en el sistema. 


* El perfil del usuario debe estar activo en la base de datos. 



**Flujo Principal:**

1. El Usuario Registrado ingresa a su sección de "Perfil". 


2. El Usuario Registrado hace clic en el botón "Editar perfil". 


3. El sistema muestra el formulario con los datos actuales cargados. 


4. El Usuario Registrado modifica los campos deseados (nombre, email y/o biografía). 


5. El Usuario Registrado hace clic en "Guardar cambios". 


6. El sistema valida que el formato de los datos sea correcto. 


7. El sistema actualiza la información en la base de datos. 


8. El sistema muestra el mensaje: "Perfil actualizado exitosamente". 


9. Fin del caso de uso. 



**Flujos Alternativos:**
**A1. Cancelar edición**

* En el paso 5, si el usuario decide no guardar:
* 5a. El Usuario selecciona "Cancelar". 

* 5b. El sistema descarta los cambios y cierra el formulario. 

* 5c. Retorna al paso 1. 


**Excepciones:**
**E1. Email con formato inválido**

* En el paso 6, si el sistema detecta un error en el correo:
* 6a. El sistema muestra un mensaje de error: "Formato de email no válido". 


* 6b. El sistema mantiene el formulario abierto para corregir el dato. 





**Postcondiciones:**

* Los datos del usuario han sido actualizados permanentemente en la base de datos. 



---

## Recordatorio

Busca errores en:
- Actores
- Precondiciones
- Flujo principal
- Flujos alternativos
- Postcondiciones
- Excepciones

