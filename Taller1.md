# Taller 1 

# Actividad 1 

 1. De acuerdo a la siguiente imagen de árbol genealógico, construya una lógica de 
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


# Reglas 

# Hij@s

hijo(X,Y) :- padre(Y,X), hombre(X).
hijo(X,Y) :- madre(Y,X), hombre(X).

hija(X,Y) :- padre(Y,X), mujer(X).
hija(X,Y) :- madre(Y,X), mujer(X).


# Herman@s













# Ti@s

tio(X, Y) :- hermano(X, Z), padre(Z, Y), hombre(X).

tio(X, Y) :- hermano(X, Z), madre(Z, Y), hombre(X).

tio(X, Y) :- hermana(X, Z), padre(Z, Y), mujer(X).

tio(X, Y) :- hermana(X, Z), madre(Z, Y), mujer(X).





# Abuel@s














# Sobrinos











# Primos









2. La ley dice que es un crimen para un Estadounidense vender armas a naciones
hostiles. Corea del Sur, enemigo de Estados Unidos, tiene algunos misiles, y todos
sus misiles les fueron vendidos por el Coronel West, quien es Estadounidense.
Pruebe que el Coronel West es un criminal.


#Persona involucrada

persona(coronel_west).

nacionalidad(usa, corea_sur).





 

