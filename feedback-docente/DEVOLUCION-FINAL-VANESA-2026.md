# Devolucion Final - Examen de Modelado de Software 2026

Estudiante: Vanesa
Resultado final: Aprobada
Nota final: 6/10

## Aciertos

1. Identificaste varios errores importantes en la Parte 1 (precondiciones arbitrarias, validaciones faltantes y excepciones mal definidas).
2. En la defensa final explicaste correctamente que quien cambia de estado es la suscripcion.
3. Lograste proponer una Parte 2 funcional con una idea de dominio coherente:
   - Usuario
   - Suscripcion
   - Categoria
   - Articulo
4. Mostraste comprension general de flujo de suscripcion/cancelacion y confirmacion al usuario.

## Fallas y aspectos a mejorar

1. En Parte 1, el Error 1 quedo debil en lo conceptual: el foco principal era actor incorrecto en caso de uso.
2. En UML de casos de uso, evita usar elementos internos del sistema como actores.
3. En tu explicacion de cancelacion, conviene reforzar siempre diferencia entre:
   - eliminar entidades
   - cambiar estado de una relacion (por ejemplo, estaActiva=false)
4. Faltaron evidencias prolijas de parte de la entrega en los archivos esperados del repositorio.

## Recomendaciones concretas

1. Antes de cerrar un caso de uso, revisar esta lista:
   - Actor externo correcto
   - Precondiciones realistas
   - Flujo principal claro
   - Flujos alternativos consistentes
   - Postcondiciones verificables
2. En diagrama de clases, explicitar cardinalidades y responsabilidades por clase.
3. En diagrama de secuencia, dejar claro quien dispara accion, quien valida y quien confirma resultado.
4. Mantener consistencia entre lo que escribis en texto y lo que dibujas en diagramas.

## Cierre

Tu aprobacion se sostiene por mejora conceptual y por la defensa final de modelado.
El siguiente objetivo academico es subir precision formal y trazabilidad entre caso de uso, clases y secuencia.