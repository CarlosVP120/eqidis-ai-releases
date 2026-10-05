# EQIDIS AI — descargas para la empresa

Instaladores de EQIDIS AI para Mac y Windows. Las descargas son públicas, como en FiscalCFDI, para que el canal de actualización funcione sin iniciar sesión en GitHub. No se incluyen claves de OpenRouter, archivos de la empresa ni perfiles de desarrollo. El código está en CarlosVP120/deepseek-harness.

## Instalación

Descarga el instalador correspondiente a tu equipo desde Releases. En Mac, abre el DMG y copia EQIDIS AI a Aplicaciones. Si macOS bloquea la primera apertura por no estar notarizada, usa Ajustes del Sistema → Privacidad y seguridad → Abrir igualmente para esta aplicación de confianza. En Windows, ejecuta el instalador; puede aparecer un aviso de editor desconocido. Las políticas de cada equipo pueden impedir la instalación y deben revisarse con su administrador.

Configura tu clave en Ajustes → Modelos → OpenRouter. Los proyectos y archivos se guardan localmente. La aplicación consulta el canal de actualización de este repositorio y presenta las actualizaciones disponibles; también puedes instalar una nueva versión manualmente desde Releases. No utiliza el canal de actualización de DeepSeek ni incorpora un token compartido de GitHub.

## Publicar una actualización

En Actions → Instaladores internos → Run workflow, introduce el identificador completo (40 caracteres) del commit validado del fork, activa `enable_updates` y selecciona win-x64, mac-arm64 o mac-x64. Repite para los tres destinos. Los artefactos se conservan durante 30 días.

Después de que todas las comprobaciones pasen, publica una Release normal (no marcada como prerelease) con versión mayor que la instalada. Incluye los instaladores, ZIP de Mac, blockmaps y metadatos `nightly.yml` y `nightly-mac.yml`. Combina en este último las entradas ZIP de ambas arquitecturas, conservando sus nombres, tamaños y SHA-512 exactos. No renombres los archivos referenciados en estos metadatos. El canal usa `releases/latest/download`, por lo que la Release debe ser la última publicación normal.

Mac usa el certificado autofirmado «EQIDIS AI Self-Signed», guardado como secretos de este repositorio e importado en un llavero temporal del corredor. Conserva este certificado entre versiones; no publiques su clave privada. Las compilaciones locales también admiten firma ad hoc. Ninguna de estas opciones necesita un certificado de pago ni constituye notarización de Apple.
