# EQIDIS AI — distribución interna

Repositorio privado de instaladores para empleados autorizados. El código está en el fork público CarlosVP120/deepseek-harness. No se incluyen claves de OpenRouter ni perfiles de desarrollo.

## Instalación

Descarga el instalador de Releases. En Mac, abre el DMG y copia EQIDIS AI a Aplicaciones. Si macOS bloquea la primera apertura por no estar notarizada, usa Ajustes del Sistema → Privacidad y seguridad → Abrir igualmente para esta aplicación de confianza. En Windows, ejecuta el instalador; puede aparecer un aviso de editor desconocido. Las políticas de cada equipo pueden impedir la instalación y deben revisarse con su administrador.

Configura tu clave en Ajustes → Modelos → OpenRouter. Los proyectos y archivos se guardan localmente. Para actualizar, cierra la aplicación e instala la nueva versión desde Releases. Los instaladores internos no consultan los servidores de DeepSeek ni incorporan un token compartido para GitHub. Las descargas privadas requieren una cuenta de GitHub con acceso concedido a este repositorio.

## Construcción

En Actions → Instaladores internos → Run workflow, introduce el commit validado del fork y selecciona win-x64, mac-arm64 o mac-x64. Los instaladores se conservan como artefactos privados durante 30 días; publícalos en Releases para conservarlos. Los corredores están sujetos a la cuota de Actions de la cuenta.

Mac se firma ad hoc sin certificado de pago. También se puede seleccionar una identidad de certificado autofirmado instalada mediante DSH_DESKTOP_MACOS_LOCAL_SIGNING_IDENTITY; conserva ese certificado entre versiones. La firma local no constituye notarización de Apple.
