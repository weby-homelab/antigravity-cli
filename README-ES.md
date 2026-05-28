<p align="center">
  <a href="README.md">English</a> | <a href="README-ZH.md">中文</a> | <b>Español</b> | <a href="README-FR.md">Français</a> | <a href="README-PT.md">Português</a> | <a href="README-UA.md">Українська</a> | <a href="README-DE.md">Deutsch</a>
</p>

# Antigravity CLI

Antigravity CLI comprende su código base, realiza ediciones con su permiso y ejecuta comandos, directamente desde su terminal.

- **Documentación oficial**: [antigravity.google/docs/cli-overview](https://antigravity.google/docs/cli-overview)
- **Sitio web oficial**: [antigravity.google/product/antigravity-cli](https://antigravity.google/product/antigravity-cli)

![Antigravity CLI Demo](agy-cli-demo.gif)

---

Antigravity CLI lleva las capacidades principales de Antigravity 2.0 (razonamiento de múltiples pasos, edición de múltiples archivos, llamadas a herramientas e historial persistente) directamente a su terminal. Está optimizado para flujos de trabajo basados en teclado y sesiones SSH remotas con una sobrecarga mínima de recursos.

---

## Características principales

| Característica | Antigravity CLI | Antigravity 2.0 |
| :--- | :--- | :--- |
| **Enfoque principal** | Velocidad, eficiencia de teclado, baja sobrecarga | Integridad, orquestación visual, gestión de proyectos |
| **Interfaz** | Interfaz de usuario de terminal (TUI) | Aplicación GUI completa y enriquecida |
| **Flujos de trabajo** | Sesiones SSH/remotas, primero el teclado | Espacios de trabajo locales, orquestación pesada |
| **Motor de agente** | Motor de agente central compartido | Motor de agente central compartido |

---

## Integración

- **Motor de agente compartido**: Ambas interfaces se ejecutan en el mismo motor de agente central. Las mejoras se aplican automáticamente a ambas.
- **Configuraciones compartidas**: Las preferencias y los permisos se sincronizan bidireccionalmente.
- **Exportación de sesiones**: Exporte sesiones de terminal a la interfaz gráfica de usuario de Antigravity 2.0 para seguir trabajando.

---

## Instalación

### macOS / Linux
```bash
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

### Windows PowerShell
```powershell
irm https://antigravity.google/cli/install.ps1 | iex
```

### Windows CMD
```cmd
curl -fsSL https://antigravity.google/cli/install.cmd -o install.cmd && install.cmd && del install.cmd
```

---

## Autenticación

La CLI se autentica a través del llavero del sistema, recurriendo al inicio de sesión de Google si no existe una sesión activa.

- **Local**: Abre automáticamente su navegador predeterminado.
- **Remoto / SSH**: Detecta sesiones SSH e imprime una URL de autorización para completar el inicio de sesión localmente.
- **Cerrar sesión**: Ejecute `/logout` para borrar las credenciales guardadas.

> [!NOTE]
> Para acceso empresarial, conecte su proyecto de GCP durante el proceso de incorporación. Consulte la página de Enterprise para obtener más detalles.

---

## Términos de servicio y uso de datos

> [!WARNING]
> Se sabe que los agentes de codificación de IA conllevan ciertos riesgos de seguridad, incluida la ejecución autónoma de código, la filtración de datos, la inyección de directivas (prompts) y riesgos en la cadena de suministro. Asegúrese de supervisar y verificar todas las acciones realizadas por el agente.

Al utilizar Antigravity CLI, acepta ayudar a mejorar el producto permitiendo que Google recopile y utilice sus datos de interacciones, de conformidad con los Términos de servicio de Google y la Política de privacidad de Google. Puede optar por no participar en cualquier momento a través de su configuración.

### Enlaces legales y de privacidad

- **Términos de servicio**: [antigravity.google/terms](https://antigravity.google/terms)
- **Política de privacidad**: [policies.google.com/privacy](https://policies.google.com/privacy)
