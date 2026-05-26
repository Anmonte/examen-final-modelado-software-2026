# Parte 3: Notas para Defensa Oral

## Presentacion del Proyecto

- Nombre del proyecto:
- Feature principal:
- Arquitectura general:

## Decisiones de Diseno

- Estructura de clases:
- Uso de MVC:
- Patrones identificados:

## Defensa del Caso de Uso

- Que funcionalidad modele:
- Que clases agregue:
- Como se relacionan:

## Conceptos a Repasar

- Actor primario y secundario
- Precondicion y postcondicion
- Diferencia entre diagrama de clases y secuencia
- Principios SOLID basicos



¿Qué objeto cambia de estado exactamente?
El objeto que cambia de estado es la instancia de la clase Suscripción.

Es importante notar que el Usuario y la Categoría no cambian sus datos internos; solo cambia el vínculo que los une.

¿Qué relación se mantiene y cuál se desactiva?
Se mantiene: La relación de Agregación entre Categoría y Artículo.
Se desactiva: La relación de Asociación Suscripción entre el Usuario y la Categoría.

¿Por qué los artículos siguen existiendo?
El Artículo tiene una relación de vida con la Categoría -si borras la categoría, podrías borrar los artículos, lo cual se llama composición.

Cómo se refleja esto en tu secuencia (qué mensaje dispara la cancelación y quién confirma el resultado).
En el diagrama de secuencia su proceso sería el siguiente:

1.Mensaje que dispara la acción:
2. El Controlador envía un mensaje a la Base de Datos
3. Quién confirma: La Base de Datos devuelve un mensaje de éxito o error.