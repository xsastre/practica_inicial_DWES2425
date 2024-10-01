# Pràctica de benvinguda a DWES i DAW 2024-2025

- [Pràctica de benvinguda a DWES i DAW 2024-2025](#práctica-de-bienvenida-a-dwes-y-daw-2024-2025)
    - [Quant a](#acerca-de)
    - [Declaració](#enunciado)
    - [Restriccions](#restricciones)
    - [Lliurament](#entrega)
    - [Característiques](#recursos)

## **Quant a**

Aquesta pràctica té com a objectiu ser una avaluació inicial sobre continguts de 1r DAW.

Com bé saps, per programar en l'entorn de servidor hem de tenir uns conceptes mínims ben presents.

Podeu utilitzar apunts de cursos anteriors sense problema però sense perdre-hi gaire temps..

## **Enunciat**

Com a futurs desenvolupadors de backend, te convid a que facis una petita pràctica de benvinguda a DWES i DAW. Per això hem de fer una aplicació amb la següent funcionalitat i tingui les següents restriccions:

- És una aplicació en consola, que s'anomeni `torneig_tenis.jar`

- Aquesta aplicació accepta com a màxim dos paràmetres: fitxer\_entrada.csv i fitxer\_sortida.xxx

    - `fitxer_entrada.csv` contindrà les dades dels jugadors de tennis que participaran a la competició i sempre és obligatori. La seva extensió vàlida és .csv. El path ha de ser vàlid en sistemes de fitxers tant de Linux com de Windows.
    - `fitxer_sortida.xxx` només podeu tenir extensió .csv, .json o .xml. El path ha de ser vàlid com en el punt anterior. Si no escrius un path, el fitxer es desarà al directori actual, amb json com a format per defecte i amb el nom torneig\_tenis.json.

```bash
java \-jar torneig\_tennis.jar fitxer\_entrada.csv fitxer\_sortida.json
``` 

- El programa ha de contenir una base de dades en fitxers del tipus SQLite per emmagatzemar la informació, per això tindrem una taula anomenada tennistes amb la següent informació (et recomano analitzar bé els tipus de dades):

    - id (autonumèric)
    - nom: nom del tennista complet
    - país: nom del país
    - alçada: altura del tennista en cm
    - pes: pes del tennista en kg
    - punts: punts totals del tennista
    - mà: mà del tennista, DRETÀ o ESQUERRÀ
    - data\_naixement: data de naixement del tennista, en format AAAA-MM-DD (ISO 8601\)
    - created\_at: data de creació del tennista, en format AAAA-MM-DDTHH:MM:SS.SSSSSSS (ISO 8601\)
    - updated\_at: data d'actualització del tennista, en format AAAA-MM-DDTHH:MM:SS.SSSSSSS (ISO 8601\)


- El programa ha de llegir el fitxer d'entrada i inserir les dades a la base de dades. El fitxer d'entrada ha de ser obert en mode lectura i has d'analitzar que totes les dades són vàlides i estan en format correcte abans de ser inserides.

- A més, tindrem una memòria cau FIFO de la base de dades amb mida de 5 elements.

- El programa ha de generar un fitxer de sortida amb la informació de la base de dades.

- Abans d'oferir la sortida heu de mostrar a la consola les següents consultes usant api de col·leccions:

    - tennistes ordenats amb rànquing, és a dir, per punts de major a menor
    - mitjana d'alçada dels tennistes
    - mitjana de pes dels tennistes
    - tennista més alt
    - tennistes d'Espanya
    - tennistes agrupats per país
    - nombre de tennistes agrupats per país i ordenats per punts descendent
    - nombre de tennistes agrupats per mà dominant i puntuació mitjana d'ells
    - puntuació total dels tennistes agrupats per país
    - país amb més puntuació total
    - tennista amb millor rànquing d´Espanya.

## **Restriccions**

- En tot moment hi ha d'haver un validador de dades que verifiqui que les dades abans de ser introduïdes a la base de dades siguin correctes.
- S'ha d'implementar el repositori d'emmagatzematge amb les operacions de selecció completa, selecció per ID, selecció per país, selecció per rànquing, inserció, actualització i esborrament. Les sortides de llista han d'estar ordenades per rànquing ascendent. El rànquing es calcula sobre la base de punts, tindrà més rànquing quan tinguin més punts.
- S'han de testejar tots els elements realitzats i assegurar un 90% de cobertura dels elements funcionals ja sigui usant test unitaris i test d'integració. Recolza't d'una llibreria de test amb dobles o mocks quan sigui necessari.
- Cal utilitzar un mètode manual o automatitzat d'injecció de dependències.
- La base de dades s'ha de buidar en iniciar l'aplicació.
- Els paràmetres de configuració i ús de la base de dades han d'estar en un fitxer de `.propietats`.
- El desplegament de l'aplicació ha de ser a un executable .jar amb el nom torneig\_tennis.jar.
- S'ha de comentar el teu codi i obtenir aquesta documentació en html (pots fer servir eines com Dokka o JavaDoc).
- Cal treballar amb Git i Github seguint GitFlow.
- El llenguatge de programació ha de ser Java i utilitzar JDK 17 o superior (recomanable 21LTS).
- S'ha d'usar log, però els log per pantalla per a DEBUG, els nivells INFO o superiors han d'anar a un fitxer al directori /log de l'aplicació.
- S'han d'implementar les operacions de col·leccions usant l'API de col·leccions funcional de Java.
- La consola en la vostra execució ha de tenir colors.
- Fes-nos un favor a tots i fes servir `.gitignore` de manera correcta.

## **Lliurament**

- Projecte mitjançant `Pull Request` a aquest directori al directori lliuraments. El subdirectori que has de fer és cognom\_cognom\_nom.
- A l'esmentat directori hi ha d'estar el projecte i un fitxer README.md.
- Al fitxer README.md ha de tenir:
    - Descripció del projecte.
    - Arquitectura utilitzada.
    - Enumerar els 5 principis SOLID i posar 2 exemples amb captures del teu codi on els facis servir.
    - Justificació de les llibreries usades.
    - Primer lliurament divendres, 13 de setembre de 2024 a les 18:00.
    - Segona entrega dilluns, 16 de setembre de 2024 a les 19:00.

```bash
/lliuraments/cognom\_cognom\_nom/
```

## **Característiques**

- Documentació dels llenguatges i llibreries que vulguis fer servir.
- Pots fer servir ChatGPT, CoPilot, Tabnine, Codeium o similar per ajudar-te, consultar o fer-te els teus apunts, però recorda que als exàmens no tindrà sense internet, així que: aprèn i comprèn el perquè de les coses.
