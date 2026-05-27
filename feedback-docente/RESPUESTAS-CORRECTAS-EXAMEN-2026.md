# Respuestas Correctas de Referencia - Examen Final 2026

Documento de estudio posterior al examen.
Las respuestas son un modelo de referencia. Se aceptan variantes correctas y bien justificadas.

---

## Parte 1 - Analisis critico del caso de uso con errores

### Error 1 - Actor/descripcion incorrecta
Problema:
Se mezcla lenguaje de actor con elemento interno del sistema (por ejemplo, servidor/sistema como actor).

Respuesta correcta esperada:
- Actor principal: Usuario Registrado.
- El sistema no es actor; el sistema ejecuta comportamiento interno.
- La descripcion debe expresar una necesidad del actor externo y no una decision tecnica interna.

### Error 2 - Precondicion arbitraria
Problema:
Condiciones sin sentido funcional (por ejemplo, cantidad de seguidores).

Respuesta correcta esperada:
- Precondiciones realistas:
  - Usuario autenticado.
  - Cuenta activa.
- No usar restricciones arbitrarias no justificadas por negocio.

### Error 3 - Falta de validacion previa
Problema:
Guardar directamente sin validar datos.

Respuesta correcta esperada:
- Antes de persistir, validar formato y reglas de negocio.
- Si la validacion falla, mostrar error y mantener contexto de correccion.

### Error 4 - Postcondiciones incorrectas
Problema:
Acciones no relacionadas con el objetivo del caso o de riesgo (spam, sesiones inesperadas).

Respuesta correcta esperada:
- Postcondicion principal: datos actualizados correctamente.
- Confirmacion visible al usuario.
- Evitar efectos laterales no requeridos.

### Error 5 - Excepcion mal definida
Problema:
Ante error, el sistema no informa ni permite recuperacion.

Respuesta correcta esperada:
- Mensaje de error claro.
- Punto de retorno para corregir datos o reintentar.
- Registro del incidente cuando corresponda.

---

## Parte 2 - Diseno practico (modelo correcto de referencia)

### Caso de uso (estructura correcta)
- ID: CU-05
- Nombre: Suscripcion a categorias de articulos
- Actor principal: Usuario Registrado
- Actor secundario (opcional y segun alcance): Servicio de Notificaciones

Descripcion correcta:
El usuario se suscribe a categorias para recibir alertas de nuevas publicaciones.

Precondiciones correctas:
- Usuario autenticado.
- Categoria existente y visible.
- Sistema operativo de notificaciones disponible (si aplica).

Flujo principal correcto:
1. Usuario selecciona categoria.
2. Usuario confirma suscripcion.
3. Sistema verifica que no exista suscripcion activa previa.
4. Sistema crea o activa suscripcion.
5. Sistema confirma resultado.

Flujos alternativos correctos:
- A1: Ya estaba suscripto -> informar estado y permitir cancelar.
- A2: Error de validacion/infraestructura -> informar error y no confirmar alta.

Postcondiciones correctas:
- Suscripcion activa persistida.
- Evento de auditoria/log opcional.

### Diagrama de clases (modelo correcto)
Clases nucleares:
- Usuario
- Suscripcion
- Categoria
- Articulo

Relaciones correctas:
- Usuario 1..* Suscripcion
- Suscripcion *..1 Categoria
- Categoria 1..* Articulo

Regla clave:
- La cancelacion cambia estado de Suscripcion (por ejemplo, estaActiva=false), no elimina Usuario/Categoria/Articulo.

### Diagrama de secuencia (flujo correcto)
Participantes recomendados:
- Usuario
- Interfaz
- Controlador de Suscripcion
- Persistencia/Repositorio

Secuencia correcta:
1. Usuario inicia accion de suscribirse/cancelar.
2. Interfaz delega al controlador.
3. Controlador consulta estado actual de suscripcion.
4. Controlador aplica regla de negocio (crear, activar, desactivar).
5. Persistencia confirma.
6. Controlador responde a interfaz con exito o error.

---

## Parte 3 - Defensa oral (respuestas correctas esperadas)

### 1) Por que Sistema no debe ser actor
Porque actor es entidad externa que interactua con el sistema. El sistema no puede ser actor de si mismo.

### 2) Diferencia entre precondicion, flujo alternativo y postcondicion
- Precondicion: lo que debe cumplirse antes de ejecutar.
- Flujo alternativo: variante o excepcion durante ejecucion.
- Postcondicion: estado del sistema al finalizar.

### 3) Justificacion de relaciones
Las relaciones se justifican por reglas del dominio y cardinalidad real. Si la relacion tiene datos propios, se modela entidad intermedia.

### 4) Aplicacion de MVC
- Modelo: datos y logica de negocio.
- Vista: interfaz.
- Controlador: coordinacion entre vista y modelo.

### 5) Uso de Observer en notificaciones
Permite que un cambio en una entidad publique eventos a varios suscriptores sin acoplamiento fuerte.

---

## Criterio de calidad que se espera en proximos trabajos

1. Coherencia entre caso de uso, clases y secuencia.
2. Terminologia UML correcta.
3. Justificacion breve pero tecnica de cada decision.
4. Entrega completa y trazable en los archivos esperados.