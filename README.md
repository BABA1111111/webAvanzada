# webAvanzada

## LABORATORIO 1 - Bárbara Oyarzo Alfaro

### Pregunta 1 (2 pts). 
#### ¿Por qué no se recomienda desarrollar directamente sobre main en este laboratorio?

R: Es una mala práctica ya que dificulta el trabajo en equipo y puede ocasionar errores si se sube un código con errores.

### Pregunta 2 (2 pts). 
#### ¿Qué problema se evita al utilizar --skip-git al crear el proyecto Angular?

R: Al utilizar este comando se evita la creación de un repositorio de Git anidado.

### Pregunta 3 (2 pts). 
#### ¿Qué verifica npm run build en esta etapa del laboratorio?
R: Sirve para verificar que las configuraciones iniciales se isntalaron correctamente.

### Pregunta 4 (2 pts). 
#### ¿Qué utilidad tiene revisar git status o git diff --cached antes de realizar un commit?

R: Sirve para visualizar cuales son es exactamente los archivos modificados y qué es lo que se va a subir.

### Pregunta 5 (2 pts). 
#### ¿Qué evento activa el workflow ci.yml?

R: Un evento `pull_request` hacia la rama `main`

### Pregunta 6 (2 pts).
#### En runs-on: ubuntu-latest, ¿qué representa ubuntu-latest?
R: Significa que el workflow se va a ejecutar con la versión más reciente de Ubuntu.

### Pregunta 7 (2 pts). 

#### Ordene las etapas de validación que ejecuta el job frontend y explique por qué npm ci se ejecuta antes que las pruebas.

R: Obtener código → Configurar Node.js → npm ci → npm test → npm run build

npm ci se ejecuta antes que las pruebas porque estas necesitan de las dependencias del proyecto para poder ejecutarse correctamente.

### Pregunta 8 (3 pts). 

#### Después del push, indique qué etapa del pipeline falla y qué ocurre con las etapas siguientes.

Luego de hacer el push la etapa "Ejecutar pruebas" falla ya que uno de los tests esperaba encontrar el texto "Catálogo de Recursos", pero la aplicación muestra "Título Incorrecto", por lo que se produce una prueba exitosa y una prueba fallida. Como resultado el job se detiene y las etapas siguientes no se ejecutan.

### Pregunta 9 (3 pts). 
#### ¿Debería integrarse este Pull Request a main mientras el pipeline está fallando? Justifique.

El pipeline sirve como una barrera de seguridad antes de implementar cambios, por lo que si este está fallando no es recomendable integrar el Pull Request. Este solo debe hacerse luego de verificar que todas las etapas se ejecutaron correctamente.

### Pregunta 10 (4 pts). 
#### Clasifique cada elemento como “versionable”, “variable/configuración” o “secreto/no versionable”: package.json, API_URL pública, AWS_REGION, DB_PASSWORD, API_TOKEN, terraform.tfstate.

Versionable: `package.json`

Variable/configuración: `API_URL` pública, `AWS_REGION`

Secreto/no versionable: `DB_PASSWORD`, `API_TOKEN`, `terraform.tfstate`  

### Pregunta 11 (2 pts). 
#### ¿Por qué una contraseña o token no debe escribirse directamente dentro de ci.yml, cd.yml o un archivo TypeScript del frontend?
Porque ci.yml, cd.yml y el código TypeScript pueden terminar guardados en Git/GitHub, y cualquier persona con acceso al repositorio podría ver esas credenciales.

### Pregunta 12 (2 pts). 
#### Si un secreto real fue incluido en un commit y luego se agrega su archivo a .gitignore, ¿queda solucionado el problema? Explique qué acción adicional debe realizarse.

Agregar el archivo a .gitignore no soluciona el problema si el secreto ya fue incluido en un commit. Se debe revocar el secreto y generar uno nuevo.
### Pregunta 13 (2 pts). 
#### ¿Qué diferencia existe entre terraform validate, terraform plan y terraform apply?

### Pregunta 14 (2 pts). 
#### ¿Por qué ci.yml se activa con pull_request y cd.yml se activa con push sobre main?

### Pregunta 15 (2 pts).
#### ¿Qué función cumple Terraform dentro de este flujo de CD?

### Pregunta 16 (2 pts). 
#### ¿Por qué el workflow usa ${{ secrets.DEMO_TOKEN }} en lugar de escribir el valor directamente?



