# app-resources

Recursos y configuración remota para las apps de SOPAgames — pensado para
cosas que un app necesita poder actualizar **sin pasar por una revisión de
App Store / Play Store**: catálogos de contenido descargable, flags, listas
de URLs, etc. Repo público a propósito (las apps lo leen sin login); nunca
poner acá nada sensible.

Una carpeta por proyecto. Cada app apunta a su propio archivo vía URL
`raw.githubusercontent.com` y decide su propio esquema — no hay un formato
único impuesto entre proyectos.

## Proyectos

- [`hiddenchat/`](hiddenchat/) — catálogo de modelos LLM descargables de
  [HiddenChat2](https://github.com/SOPAgames/HiddenChat2).
