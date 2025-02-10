Parte 1: Configuración Inicial
Antes de empezar a trabajar con Git y GitHub, lo primero que tenemos que hacer es configurar Git en nuestro ordenador y crear un repositorio en GitHub para subir ahí todo nuestro proyecto.

Configurar Git en tu ordenador
Primero le vamos a decir a Git quién eres, para que cada vez que guardes un cambio (un commit) quede registrado con tu nombre y correo. Esto se hace con estos dos comandos:

git config --global user.name "Tu Nombre" → Aquí pones tu nombre.
git config --global user.email tuemail@example.com → Aquí tu correo, que debería ser el mismo que usas en GitHub.
Crear un repositorio en GitHub
Entramos en GitHub, hacemos clic en el botón "New Repository" y le damos un nombre al proyecto.
Es importante marcar la opción "Initialize this repository with a README", porque así ya tendremos un archivo README.md creado para empezar.

Clonar el repositorio en tu equipo
Ahora vamos a descargar el repositorio en nuestro ordenador para trabajar en él.

git clone URL_DEL_REPOSITORIO Este comando copia el repositorio. La URL la encuentras en GitHub, en el botón Code.
cd NOMBRE_DEL_REPOSITORIO  Nos movemos a la carpeta del proyecto con este comando.
Parte 2: Trabajo Individual con Git
Aquí ya empezamos a trabajar en el proyecto desde nuestro ordenador, haciendo cambios y subiéndolos a GitHub.

Crear un archivo y hacer el primer commit
Vamos a crear un archivo index.html como prueba. Lo hacemos así:

echo "# Proyecto Web" > index.html  Esto crea el archivo index.html con el texto # Proyecto Web.
Después lo añadimos al área de preparación con:
git add index.html
Y finalmente hacemos un commit para guardar el cambio:
git commit -m "Añadir archivo index.html"
Subir los cambios a GitHub
Para que los cambios se vean en GitHub, los subimos con:

git push origin main
Actualizar el repositorio local
Si alguien más ha subido cambios a GitHub, debemos actualizar nuestro repositorio local con:

git pull origin main
Parte 3: Trabajo Colaborativo
En este apartado trabajaremos en equipo. Vamos a usar ramas para desarrollar nuevas funcionalidades sin tocar directamente el código de main. Luego, pediremos que nos revisen los cambios con un Pull Request (PR).

Crear una nueva rama
Primero, creamos una rama llamada nueva-funcionalidad con:

git branch nueva-funcionalidad
Después cambiamos a esa rama con:
git checkout nueva-funcionalidad
(O podemos hacerlo todo junto con git checkout -b nueva-funcionalidad).
Hacer cambios en la nueva rama y guardarlos
Modificamos el archivo index.html añadiendo un título:

echo "<h1>Hola mundo</h1>" > index.html
Luego añadimos y guardamos los cambios con:
git add index.html
git commit -m "Añadir título en index.html"
Subir la rama a GitHub
Para que los demás puedan ver esta nueva rama, la subimos con:

git push origin nueva-funcionalidad
Crear un Pull Request (PR)
En GitHub, vamos a la pestaña Pull Requests y hacemos clic en New Pull Request.
Seleccionamos la rama nueva-funcionalidad para compararla con main. Revisamos los cambios y escribimos una descripción explicando lo que hemos hecho. Luego hacemos clic en Create Pull Request.

Revisar y fusionar cambios
Otro compañero revisa el PR. Si todo está bien, se aprueba y se fusiona con main. Si hay que corregir algo, lo hacemos antes de aprobar. Cuando todo está listo, hacemos clic en Merge Pull Request.

Actualizar el repositorio local
Después de que se fusione el PR, volvemos a la rama principal y actualizamos con:

git checkout main
git pull origin main
Parte 4: Resolución de Conflictos
A veces, dos personas editan la misma línea en un archivo, y cuando intentan fusionar sus cambios, Git no sabe cuál elegir. Eso genera un conflicto.

Generar un conflicto
Por ejemplo, imagina que tú y otro compañero editáis la misma línea en index.html en ramas diferentes. Cuando ambos intentéis fusionar vuestros cambios con main, Git os avisará del conflicto.

Resolver el conflicto
Git marcará el archivo con líneas como <<<<<<, ====== y >>>>>>.
Editamos el archivo manualmente, eliminando esas marcas y manteniendo los cambios correctos. Después hacemos:

git add index.html
git commit -m "Resolver conflicto en index.html"
git push origin main
Parte 5: Entrega Final
Antes de entregar el repositorio, asegúrate de que cumpla con los siguientes requisitos:

Un archivo README.md bien documentado.
Un historial de commits organizado, con mensajes claros.
Uso de ramas y al menos un Pull Request creado.
Que hayas resuelto al menos un conflicto correctamente.
