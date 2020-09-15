# TP 1

## 1. ¿Podrías buscar un ejemplo de macromoléculas que almacenen información sobre la ‘identidad’ de un organismo dado? 

El ADN, o ácido desoxirribonucleico, es la molécula que contiene la información genética de todos los seres vivos, incluso algunos virus.
[Fuente](https://www.genome.gov/es/genetics-glossary/ADN-acido-Desoxirribonucleico#:~:text=%E2%80%8BADN%20(%C3%81cido%20Desoxirribonucleico)&text=ADN%20es%20el%20nombre%20qu%C3%ADmico,una%20estructura%20de%20doble%20h%C3%A9lice.)

## 2. Proponé una forma de expresar la información contenida en la estructura primaria de las proteínas usando tipos de datos de los lenguajes de programación que conocés.

Como primera aproximación propondría

* Proteina
 `List<String>` donde String es una secuencia de aminoacidos. Ejemplo: "CYTVP" (Usualmente entre 80 y 300 elementos)

 Pero si la idea es generar un sistema un poco mas complejo, sugeriría usar objetos

 * `List<Aminoacido>` donde cada `Aminoacido` sabe cual es su estructura secundaria,por ejemplo

## 3. ¿En que tipos de datos podes expresar la informacion de la estructura terciaria proteica?

Se podrian representar como un tipo float o double (1.49,1.32)

## 4. Rosalin Franklin es una cientifica muy relevante, que tuvo menos reconocimiento del merecido. ¿Cuales fueron sus contribuciones en este campo?¿Que nos cuenta su historia acerca del mundo de la ciencia?

Rosalin contribuyo con una propuesta de estructura del ADN que se basaba en la difraccion de rayos X que tenia una alta calidad de imagen.
Tambien colaboro con importantes trabajos sobre virus como el del mosaico del tabalo y la polio.
Su historia academica nos cuenta acerca del aberrante mundo machista en el que vivimos, que en este caso se ve en la ciencia.
Sufrió muchas veces esta deficiencia cultural,pero de alguna forma fortaleció aun mas su figura ejemplar en el mundo actual.

## 5. Proponer en psudocodigo un programa que prediga la estructura secundaria que adoptará cada residuo de la secuencia proteica dada, especificandola como H(helice) B(beta plegada) y L(bucle o Loop)

En un paradigma de objetos, delegaria esa responsabilidad en el residuo, es decir cuando creas el residuo, 
ya sabe cual va a ser su estructura. Por ejemplo `Glu().getEstructuraSecundaria()` -> retorna una instancia de `A`
En un paradigma mas imperativo seria algo asi: 

```
estSecundariaResiduo(aminoacido) {
       #Preciondicion: El aminoacido esta en alguna de estas tres listas
       Hlist = ([G,A,L,M...],H) # Defino los residuos por extension en una lista correspondiente similar a la tabla
       Blist = ([V,I,T,C...]B)
       Llist = ([...], L)
       for l in [Hlist,Blist,Llist]:
              if(l.fst.pertence(aminoacido)):
                     return l.snd

}
```

## 6. ¿Que hace distintos a dos individuos de una especie? Propone una forma de corroborar tu respuestautilizando un diagrama de un posible metodo computacional para dicho fin.

Entiendo que dentro de cada ADN hay genes base (Los que se comparten entre los de la misma especie) y genes variables (Cambian dentro de la misma especie, se me ocurre por ejemplo el/los del color de ojos). Teniendo en cuenta esto, propongo lo siguiente
```
diferenciarMismaEspecie(adn):
       genesBase = genesBaseDe(especie)

       return adn.allMatch(gen => adn.pertenece(gen) )
#Quiza se pueda tener algun margen de error, como uno o dos genes por las dudas.
              
```