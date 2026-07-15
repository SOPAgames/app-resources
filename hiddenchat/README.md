# hiddenchat/models.json

Catálogo de modelos descargables de HiddenChat. La app lo lee al abrir (y
con el botón "Actualizar modelos disponibles" en Opciones), lo cachea
localmente, y si no hay red usa un catálogo embebido de respaldo
(`assets/catalog/models_fallback.json` en el repo de la app — mantenerlo
razonablemente al día a mano, no se sincroniza solo).

URL que consume la app:
`https://raw.githubusercontent.com/SOPAgames/app-resources/main/hiddenchat/models.json`

## Editar el catálogo

Solo tocar este archivo y hacer push a `main` — no hace falta build ni
release de la app, los usuarios lo ven la próxima vez que abren HiddenChat
(o tocan "Actualizar modelos disponibles"). `schemaVersion` sube solo si
cambia la ESTRUCTURA del JSON (la app sabría ignorar campos nuevos, pero
rechazaría un cambio de forma incompatible sin bump).

Campos de cada modelo en `models[]`:
- `id`: estable, no cambiar una vez publicado (se usa para persistencia
  local — modelo activo, progreso de descarga, etc.).
- `tier`: uno de los `id` listados en `tiers[]`.
- `downloadUrl` / `fileName`: de dónde se baja y con qué nombre se guarda.
- `sizeBytes` / `sizeVerified`: tamaño informativo — la app siempre
  reconfirma el tamaño real por HTTP antes de descargar.
- `minRamGb`: umbral informativo (hoy solo genera una advertencia, no
  bloquea la descarga — fase de testeo).
