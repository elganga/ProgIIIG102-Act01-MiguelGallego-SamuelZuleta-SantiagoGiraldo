# Taller 1 

# Actividad 1 


 De acuerdo a la siguiente imagen de árbol genealógico, construya una lógica de 
 predicados donde las relaciones directas se generen por hechos y las relacion de 
 mas de una generación se obtengan mediante reglas.
 
 Ejemplo: padre(homero, bart) el anterior es un hecho y corresponde a una relación directa, mientras que 
 abuelo(X, bart) puede ser una consulta hecha al programa, donde la relación abuelo 
 (que es de más de 1 generación) debe ser obtenida por reglas, no por hechos. 

# Hechos 

# Padre De:

padre(abraham, herbert).

padre(abraham, homero).

padre(clancy, marge).

padre(clancy, patty).

padre(clancy, selma).

padre(homero, bart).

padre(homero, lisa).

padre(homero, maggie).

# Madre De:

madre(mona, herbert).

madre(mona, homero).

madre(jacqueline, marge).

madre(jacqueline, patty).

madre(jacqueline, selma).

madre(marge, bart).

madre(marge, lisa).

madre(marge, maggie).

madre(selma, ling).

# Asignación de género:

hombre(abraham).

hombre(clancy).

hombre(herbert).

hombre(homero).

hombre(bart).

mujer(mona).

mujer(jacqueline).

mujer(marge).

mujer(patty).

mujer(selma).

mujer(lisa).

mujer(maggie).

mujer(ling).

 

