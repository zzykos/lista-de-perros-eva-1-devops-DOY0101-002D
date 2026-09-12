## Evaluación parcial N°1

### Observaciones
- Se utilizó como base el repositorio: https://github.com/Saitraru/Lista-de-perros-eva-ea1. De él se extrajeron los archivos `index.html`, `index.js` y `style.css`.
- Se agregó el directorio `.github/workflows/` para incluir la automatización de flujos usando Github Actions.

### Cómo levantar el proyecto localmente
Sólo se debe abrir en el navegador de preferencia el archivo `index.html`.

### Estrategia de ramificación
Se utilizó la metodologia *Gitflow*, debido a que es una forma de ramificación estructurada que organiza por medio de ramas como main, develop, feature y hotfix. Permite el aislamiento de cambios, lo que evita que hayan errores por código inestable en la rama principal. El trabajo se desarrolló de forma individual, sin embargo, de hacerlo con un equipo, esta metodología facilitaría el desarrollo paralelo de código de manera segura, trabajando en develop y luego pasando todo el código corregido a la rama main.

### Convenciones de commits
Se utilizó el formato de mensajes de commit: `<prefijo>:<descripción>`, usando los prefijos `feat` para nuevas funcionalidades/cambios en el diseño y `fix` para eventuales correcciones. Se optó por esta convención dado que al ser descriptivo, es visible a la perfección el tipo de cambio que se realizó dentro del código, permitiendo revisiones eficientes de este mismo en caso de existir algún fallo. En trabajo grupal, es eficaz ya que da claridad sobre los cambios efectuados, así los otros integrantes están al tanto de las nuevas versiones.

### Convenciones de naming de ramas
Para el naming de las ramas, se utilizó el formato `feature/` y `hotfix/`. De esta forma, es posible la división de trabajo por categorías, enfocando cada rama a un propósito específico, permitiendo el desarrollo de funcionalidades sin afectar el código principal.

### Estrategia de revisión (Pull Requests)
Cualquier tipo de paso de código a las ramas develop o main se realizó mediante *Pull Requests*. Con esto, se asegura que cada Pull Request sea revisado antes de ser fusionado, haciendo que todo sea integrado de manera controlada y manteniendo la estabilidad del proyecto a largo plazo.

### Automatización (CI/CD)
Se diseñó un flujo de trabajo automatizado utilizando *GitHub Actions* llamado **CI/CD**. Este flujo se realizó mediante el archivo `ci.yml` dentro del directorio `.github/workflows/`, el cual levanta un servidor temporal de Ubuntu que activa triggers en dos situaciones:
- Push a `develop`: Cada vez que se sube código nuevo, el sistema ejecuta un script para verificar que los archivos `index.html`, `index.js` y `style.css` existan y no se hayan borrado en el proceso. Si está todo bien, se confirma que pasó la prueba de integridad.
- Pull Request a `main`: Antes de aceptar cualquier cambio definitivo, se vuelve a ejecutar la revisión de archivos para simular una barrera de seguridad, asegurando que no se fusione una versión errónea en la rama principal

### Estructura de carpetas
```text
Lista-de-perros/
├── .github/
|    └──workflows/
|        └── ci.yml
├──index.html
├── index.js
├── style.css
└── readme.md
```
### Autor
- Jairo Moraga (21.793.867-8)