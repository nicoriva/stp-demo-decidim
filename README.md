# STP Demo

Este repositorio contiene una versión personalizada de [Decidim](https://github.com/decidim/decidim) (Repositorio Oficial) adaptada para su uso por la Secretaría Técnica de Planificación (STP) para trabajar con el Plan de Ordenamiento Urbano Territorial (POUT).

[Decidim](https://decidim.org/) es un framework de participación ciudadana de código abierto escrito en Ruby on Rails, que permite a las organizaciones y comunidades tomar decisiones colectivas de manera colaborativa.
[Demo oficial en linea](https://try.decidim.org/).

## Requisitos del sistema

Antes de instalar y utilizar esta versión personalizada de Decidim, asegúrese de que su sistema cumpla con los siguientes requisitos:

-    **Git**  2.34+
-   **PostgreSQL**  14.5+
-   **Ruby**  3.0.2
-   **NodeJS**  16.18.x
-   **Npm**  8.19.x
-   **ImageMagick**

Todos las herramientas necesarias y el paso a paso de como instalar Decidim en la versión utilizada en este proyecto se encuentran en el [Manual de Instalacion](https://docs.decidim.org/en/develop/install/manual).


## Uso

  Se recomienda el uso en Ubuntu 22.04.1 LTS
  Termine la instalación con el [Manual de Instalacion](https://docs.decidim.org/en/develop/install/manual). Y clone este repositorio:
```
git clone https://github.com/nicoriva/stp-demo-decidim.git
cd stp-demo-decidim
```
### Base de datos
Para asegurarse de tener los datos correctos para esta demo ejecute lo siguiente:

*Crear usuario*
```
sudo -u postgres psql -c "CREATE USER pasantia1 WITH SUPERUSER CREATEDB NOCREATEROLE PASSWORD 'pasantia1'"
```
*Variables de entorno correctas para el caso en archivo .rbenv-vars:*
```
cat << EOF > .rbenv-vars
DATABASE_HOST=localhost
DATABASE_USERNAME=pasantia1
DATABASE_PASSWORD=pasantia1
MAPS_API_KEY=nPbAj2n484a66P9UFAFkDHvquy6DPyVKzIakcWU-unE
EOF
```
*Crear la base de datos:*
```
bin/rails db:create db:migrate
```
*Importar base de datos de la demo:*
```
psql -U pasantia1 -d pasantia1_development -f backup.sql
```
### Iniciar Servidor
Para iniciar el servidor localmente ejecute:
```
bin/rails s
```
Por defecto el servidor estará ejecutándose en http://localhost:3000/ puede visitarlo en su navegador para ver.

*Empezara a compilar por lo puede tardar un poco en cargar la primera vez*

Luego se encontrara en la pagina principal.
Puede ingresar como usuario administrador para poder acceder al panel de administrador.

 - Correo administrador: admin@stp.gov.py 
 - Contraseña: decidim_pout123456789


