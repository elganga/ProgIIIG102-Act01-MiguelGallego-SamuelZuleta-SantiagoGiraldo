# Taller 1 

# Actividad 1 

# Primer punto de la actividad

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

hermano(X, Y) :- padre(Z, X), padre(Z, Y), hombre(X), X \= Y.

hermano(X, Y) :- madre(Z, X), madre(Z, Y), hombre(X), X \= Y.

hermana(X, Y) :- padre(Z, X), padre(Z, Y), mujer(X), X \= Y.

hermana(X, Y) :- madre(Z, X), madre(Z, Y), mujer(X), X \= Y.


# Ti@s

tio(X, Y) :- hermano(X, Z), padre(Z, Y), hombre(X).

tio(X, Y) :- hermano(X, Z), madre(Z, Y), hombre(X).

tia(X, Y) :- hermana(X, Z), padre(Z, Y), mujer(X).    

tia(X, Y) :- hermana(X, Z), madre(Z, Y), mujer(X).

# Abuel@s

abuelo(X, Y) :- hombre(X), padre(X, Z), padre(Z, Y).

abuelo(X, Y) :- hombre(X), madre(X, Z), padre(Z, Y).

abuela(X, Y) :- mujer(X), madre(X, Z), padre(Z, Y).

abuela(X, Y) :- mujer(X), madre(X, Z), madre(Z, Y).


# Sobrinos

sobrino(X, Y) :- padre(Z, X), hermano(Y, Z), hombre(X).

sobrino(X, Y) :- madre(Z, X), hermano(Y, Z), hombre(X).

sobrino(X, Y) :- padre(Z, X), hermana(Y, Z), hombre(X).

sobrino(X, Y) :- madre(Z, X), hermana(Y, Z), hombre(X).


sobrina(X, Y) :- padre(Z, X), hermano(Y, Z), mujer(X).

sobrina(X, Y) :- madre(Z, X), hermano(Y, Z), mujer(X).

sobrina(X, Y) :- padre(Z, X), hermana(Y, Z), mujer(X).

sobrina(X, Y) :- madre(Z, X), hermana(Y, Z), mujer(X).


# Primos

primo(X, Y) :- padre(Z, X), padre(W, Y), hermano(Z, W), hombre(X).

primo(X, Y) :- padre(Z, X), padre(W, Y), hermana(Z, W), hombre(X).

primo(X, Y) :- padre(Z, X), madre(W, Y), hermano(Z, W), hombre(X).

primo(X, Y) :- padre(Z, X), madre(W, Y), hermana(Z, W), hombre(X).

primo(X, Y) :- madre(Z, X), padre(W, Y), hermano(Z, W), hombre(X).

primo(X, Y) :- madre(Z, X), padre(W, Y), hermana(Z, W), hombre(X).

primo(X, Y) :- madre(Z, X), madre(W, Y), hermano(Z, W), hombre(X).

primo(X, Y) :- madre(Z, X), madre(W, Y), hermana(Z, W), hombre(X).


prima(X, Y) :- padre(Z, X), padre(W, Y), hermano(Z, W), mujer(X).

prima(X, Y) :- padre(Z, X), padre(W, Y), hermana(Z, W), mujer(X).

prima(X, Y) :- padre(Z, X), madre(W, Y), hermano(Z, W), mujer(X).

prima(X, Y) :- padre(Z, X), madre(W, Y), hermana(Z, W), mujer(X).

prima(X, Y) :- madre(Z, X), padre(W, Y), hermano(Z, W), mujer(X).

prima(X, Y) :- madre(Z, X), padre(W, Y), hermana(Z, W), mujer(X).

prima(X, Y) :- madre(Z, X), madre(W, Y), hermano(Z, W), mujer(X).

prima(X, Y) :- madre(Z, X), madre(W, Y), hermana(Z, W), mujer(X).


# Segundo punto de la actividad

2. La ley dice que es un crimen para un Estadounidense vender armas a naciones
hostiles. Corea del Sur, enemigo de Estados Unidos, tiene algunos misiles, y todos
sus misiles les fueron vendidos por el Coronel West, quien es Estadounidense.
Pruebe que el Coronel West es un criminal.


# Persona involucrada

persona(coronel_west).

# Nacionalidad

nacionalidad(usa, coronel_west).

# Enemigos

enemigo(usa, corea_sur).

# Vende armas

vende_misil(coronel_west, corea_sur).

# Regla

crimen(X):- nacionalidad(usa, X),vende_misil(X,Y),enemigo(usa, Y).

# Query

crimen(coronel_west).

# Ejecución del programa

![image](https://github.com/user-attachments/assets/a86b8ca1-acc7-4204-8274-fa659ba43962)
