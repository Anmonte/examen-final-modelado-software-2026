# Guia practica: como trabajar correctamente con Git en este examen

Objetivo: evitar perdida de avances y mantener una entrega clara, trazable y facil de corregir.

---

## 1) Clonar tu fork una sola vez

```bash
git clone https://github.com/TU_USUARIO/examen-final-modelado-software-2026.git
cd examen-final-modelado-software-2026
```

Verifica remotos:

```bash
git remote -v
```

Debes ver `origin` apuntando a tu fork.

---

## 2) Trabajar siempre desde `main` para este examen

Antes de empezar cada bloque:

```bash
git switch main
git pull origin main
```

Esto evita trabajar sobre ramas viejas por error.

---

## 3) Editar solo las carpetas de entrega

Carpetas esperadas:
- `parte1-analisis-critico/`
- `parte2-diseno-practico/`
- `parte3-defensa-oral/`

Evita modificar:
- `material-examen/` (enunciados)
- archivos de configuracion del repo (salvo indicacion docente)

---

## 4) Confirmar que realmente hay cambios

```bash
git status
git diff --name-only
```

Si no aparecen archivos de tus partes, todavia no estas guardando lo correcto.

---

## 5) Commit por bloque de trabajo

Ejemplo Parte 1:

```bash
git add parte1-analisis-critico/
git commit -m "parte 1: analisis critico completo"
```

Ejemplo Parte 2:

```bash
git add parte2-diseno-practico/
git commit -m "parte 2: caso de uso y diagramas"
```

Ejemplo Parte 3:

```bash
git add parte3-defensa-oral/
git commit -m "parte 3: notas defensa oral"
```

Regla: commit corto, claro y ligado a una parte.

---

## 6) Push despues de cada commit

```bash
git push origin main
```

No dejes todo para el final. Si no hay push, el docente no lo ve.

---

## 7) Verificacion rapida de entrega

```bash
git log --oneline --decorate --max-count=10
git status
```

Resultado esperado:
- Commits visibles en `main`
- `working tree clean`

Luego revisa GitHub en el navegador y confirma que los archivos se ven en tu fork.

---

## 8) Si trabajaste en otra rama por error

Ver ramas:

```bash
git branch -vv
```

Si tus cambios quedaron en otra rama, unificarlos a `main`:

```bash
git switch main
git merge NOMBRE_DE_LA_RAMA
git push origin main
```

---

## 9) Si no encontras tus cambios

Primero revisa historial y reflog:

```bash
git log --oneline --graph --decorate --all --max-count=40
git reflog --date=local --all | Select-Object -First 60
```

Si aparece un SHA con tu trabajo:

```bash
git switch -c rescate <SHA>
```

Verifica archivos y luego merge a `main`.

---

## 10) Flujo minimo recomendado para este examen

Usar esta secuencia cada vez:

```bash
git switch main
git pull origin main
# editar archivos
git status
git add .
git commit -m "avance examen"
git push origin main
```

---

## Errores frecuentes y como evitarlos

1. "Tengo dos main":
No. Suele ser `main` + otra rama local con otro nombre.

2. "Veo los archivos en mi PC pero no en GitHub":
Falta `git add/commit/push` en la rama correcta.

3. "Subi cosas que no eran de entrega":
Siempre mirar `git diff --name-only` antes del commit.

4. "Perdi cambios":
No asumir perdida. Revisar `reflog` antes de descartar trabajo.

---

## Checklist final antes de cerrar

- Estoy en `main`.
- Hice `pull` reciente.
- Mis 3 partes estan completas en sus carpetas.
- Hice commit con mensaje claro.
- Hice push a `origin/main`.
- Verifique en GitHub que los archivos se ven.

Si cumplis este checklist, tu entrega queda visible y corregible sin problemas.