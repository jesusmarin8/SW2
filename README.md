# SW2
# Soluciones al problema 2

## Apartado 1: indique el titulo y el numero de premios de la pelicula con mas premios
### db.movies.find({}, {title: 1, awards: 1}).sort({awards: -1}).limit(1)  


## Apartado 2: muestre un listado con las diferentes clasificaciones de datos que existen, para cada uno de ellos muestre el numero de documentos que tiene esa clasificacion
### db.movies.aggregate([{ $group:{ _id:"$rated", count: {$sum:1}}}]);



## Apartado 3: muestre un listado con los diferentes generos de pelicula que existen
### db.movies.distinct( "genres"  );



## Apartado 4: indique el numero de peliculas que hay entre 1970 y 1975 incluidos
### db.movies.find({ year: { $gte: 1970, $lte: 1975 } }).count()
