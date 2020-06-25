# REST API (Golang - Chi - MySQL)

## Agenda
1. Crear modelos
2. Acceder a la base de datos (go-sql)
3. Crear conectores (gateways)
4. Crear web server, handdlers y routing (chi)
5. Documentación con Swagger
6. Tests
7. Makefile
8. Dockerrizar el proyecto
9. Deploy en Heroku (gratis)

### Un gateway 
- Es una forma de definir como acceder y como enviar datos a través de nuestros servicios


### Luego de crear un método de validación 
- `reviews/models/review.go`
  ```
  func (cmd *CreateReviewCMD) validate() error {
	if cmd.Stars < 1 || cmd.Stars > 5 {
		return errors.New("stars mus be betwen 1 - 5")
	}

	if len(cmd.Comment) > maxLenghtInComments {
		return errors.New("comment must be less than  400 chars")
	}
	return nil
  }
  ```
- Creamos un Test-File en `reviews/models/review_test.go`

## Correr Test en Go
- Verbose
	```
	$ go test -v ./...
	```
- Common
	```
	$ go test ./...
	```
## Acceso a la Base de datos
- Crear Conexión
   - Crearemos una carpeta `internal/database`
   - Dentro crearemos el archivo `mysql_client.go`

## go mods (modules)
- https://github.com/golang/go/wiki/Modules

- Comandos
  ```
  $ go get -u github.com/google/uuid
  $ go mod init
  $ go mod tidy
  ```


# Crear un módule en Github
1. Crear un repositorio en github
  - Lo llamaremos: `rest_api_go_mysql`
2. Harmos el enlace con github
  ```
  $ go mod init github.com/maalpu/rest_api_go_mysql
  ```
3. Inicializamos el repositorio en la carpeta del proyecto `rest_api_go_mysql`
  ```
  $ git init
  ```
