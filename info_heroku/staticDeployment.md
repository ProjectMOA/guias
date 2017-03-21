# Desplegar aplicaciones estáticas en Heroku
Para poder integrar de una forma fácil y rápida los proyectos de GitHub
con Heroku hay que seguir los siguientes pasos:

## Prerequisitos
1. Tener una cuenta gratuita en [Heroku](https://signup.heroku.com/dc).
1. Tener instalado [Ruby](http://jruby.org/files/downloads/9.1.5.0/index.html) y
[Bundler](http://bundler.io/) (`gem install bundler`).
## Pasos a seguir
1. Hay que crear una estructura de proyectos para *Rack*, para ello ejecutar
los siguientes comandos:
```shell
 mkdir -p site/public/{images,js,css}
touch site/{config.ru,public/index.html}
cd site && bundle init
```
Esto debería crear la siguiente estructura de ficheros:
```
- site
  |- config.ru
  |- Gemfile
  |- public
     |- index.html
     |- images
     |- js
     |- css
```
2. Hay que añadir en el fichero *Gemfile* el siguiente contenido para que se
descargue las dependencias de *Rack*:
```
source 'https://rubygems.org'
gem 'rack'
```
3. A continuación hay que ejecutar el siguiente comando para descargar las dependencias:
`$ bundle install`
4. Por último, hay que editar y añadir la siguiente información al fichero *config.ru*:
```
use Rack::Static,
  :urls => ["/images", "/js", "/css"],
  :root => "public"

run lambda { |env|
  [
    200,
    {
      'Content-Type'  => 'text/html',
      'Cache-Control' => 'public, max-age=86400'
    },
    File.open('public/index.html', File::RDONLY)
  ]
}
```
Es importante que cada vez que se quiera añadir una nueva carpeta, se añada en la línea 2 del fichero.
5. Por último, para poder ejecutarlo si se desea, se ha de lanzar el comando `rackup`, el cual
despliega la aplicación en la dirección `http://localhost:9292`.