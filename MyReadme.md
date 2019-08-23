# Crear y nutrir SEEDS:
Parece dificil, pero no lo es.
Primero creamos el archivo:
- bin/seeds.js:

En él haremos los siguientes pasos:

1) Creamos un array llamado movies con las películas que luego vamos a meter en la base de datos.
2) Creamos el modelo Movie.js para poder usarlo en la database
3) en seeds.js requerimos a mongoose y a nuestro modelo de película
4) iniciamos conexión con mongo:
   - mongoose.connect(`mongodb://localhost/${dbName}`, { useNewUrlParser: true });
5) Le decimos a mongo que queremos crear peliculas con el array movies:

   - Movie.create(movies)
        .then(movie => { console.log(` ${movie.length} created`),
          mongoose.connection.close();
          })
        .catch(err => { console.log('An error happened:', err) });

6) vamos a la carpeta bin con la terminal y hacemos un node seeds.js
7) En la terminal aparecerá un mensaje diciendo que se han creado 8 películas.

# CREAR .env:

1) creamos un archivo llamado .env
2) npm i dotenv
3) dentro de .env creamos variables de entorno como PORT=3000
4) donde queramos usarlas ponemos:
   - require('dotenv').config()
y luego:
   - process.env.PORT
