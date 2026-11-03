# README – Tasca 2: Exposició oral de l’anàlisi de dades (AC4)

## 1. Presentació del conjunt de dades

### A quin sector pertany?
El conjunt de dades `Botigues_esport` pertany al sector del comerç esportiu. 

### Què representa cada registre?
article, la botiga, les unitats, la distància i la data.

### Quines són les columnes principals i què signifiquen?
- **article:** nom del producte.
- **familia_esportiva:** categoria o família esportiva del producte.
- **botiga:** ubicació o nom de la botiga.
- **unitats:** quantitat d'unitats venudes.
- **distancia_km:** distància expressada en quilòmetres.
- **data:** data del registre.

## 2. Relació entre l'AC3 i l'AC4

### Quines fases de l'anàlisi de l'AC3 has reutilitzat?
He reutilitzat les principals fases de l'AC3:
- Lectura del fitxer CSV.
- Revisió dels registres.
- Detecció d'errors.
- Neteja de les dades.
- Validació dels registres.
- Anàlisi de les dades correctes.

### Quines parts del codi has pogut mantenir?
Funcions de conversió amb gestió d'errors casi completo 
Y los demas con un poco de modificacion

### Quines parts has hagut d'adaptar i per què?
He modificat la lectura dels registres per eliminar els espais innecessaris dels noms de les columnes i dels valors.

També he utilitzat `encoding="utf-8-sig"` per llegir correctament els caràcters especials del fitxer CSV.

En exercici 3 no habia preu , he cambiado por distancia

## 3. Característiques específiques de les dades

### Quines diferències hi ha entre les variables de l'AC3 i les de l'AC4?
Ac3 tiene precio y ac4 en vez tenia distancia 

### Quins tipus de dades numèriques hi ha en el nou conjunt?
Unitats (enters) i distanica(decimal)

### Com han condicionat aquestes diferències les operacions d'anàlisi?
A l'AC3 es podien analitzar els preus i calcular la facturació.

En canvi, a l'AC4 l'anàlisi se centra en les unitats venudes i les distàncies. Per això he adaptat les operacions i he calculat indicadors com la distància mitjana, mediana, màxima i mínima.

## 4. Problemes de qualitat detectats

### Quines incidències has identificat?
He detectat diferents problemes de qualitat:
- Camps buits.
- Nombres invàlids.
- Dates inexistents o amb formats incorrectes.
- Valors amb formats no esperats.

### Com les has detectat amb Python?
He utilitzat diferents funcions i mètodes:
- `strip()`: elimina els espais inicials i finals.
- `replace()`: substitueix determinats caràcters.
- `float()`: converteix els valors en nombres decimals.
- `strptime()`: comprova i converteix les dates.
- `None`: permet identificar valors sense informació.

### Pots mostrar exemples representatius?
He identificat aquests exemples:

- **Fila 2:** `unitats = 1O`. 
- **Fila 9:** `distancia_km = gratis`. 
- **Fila 5:** `data = 2025-11-31`.

## 5. Decisions de neteja i validació

### Quines transformacions has aplicat?
He aplicat les transformacions següents:
- Eliminació d'espais innecessaris amb `strip()`.
- Neteja de valors i formats incorrectes.
- Conversió de les unitats a nombres enters.
- Conversió de les distàncies a nombres decimals.
- Conversió i validació de les dates.
- Identificació dels camps buits.

### Quins criteris has utilitzat per acceptar o rebutjar registres?
He establert els criteris següents:
- Els camps obligatoris han de contenir informació.
- Les unitats han de ser nombres enters positius.
- La distància ha de ser un valor numèric vàlid.
- La data ha de tenir un format correcte i correspondre a una data real.

Si un registre no compleix els criteris establerts, es rebutja.

### Quines decisions has hagut de modificar respecte de l'AC3?
La principal modificació ha estat substituir les operacions relacionades amb el preu per operacions relacionades amb la distància en quilòmetres.

### Com has evitat fer correccions arbitràries?
He mantingut els valors originals quan no podia determinar amb seguretat quin era el valor correcte.

Només he aplicat transformacions justificades, com eliminar espais o convertir valors que tenien un format correcte. Quan no podia garantir que una dada fos correcta, he marcat el registre com a incorrecte en lloc d'inventar-ne el valor.

## 6. Resultats del procés de neteja

### Quants registres hi havia inicialment?
Inicialment hi havia **120 registres**.

### Quants s'han acceptat i quants s'han rebutjat?
- Registres inicials: 120.
- Registres vàlids: 90.
- Registres rebutjats: 30.

### Quines incidències han estat més freqüents?
La incidència més freqüent ha estat la relacionada amb les dates, amb 
**19 casos** de dates amb formats incorrectes o no vàlides.

### Què indiquen aquests resultats sobre la qualitat de les dades?
Dels 120 registres inicials, se n'han rebutjat 30, que representen un 30%.

Això significa que el 75% dels registres s'han pogut acceptar i que el 30% presentaven problemes de qualitat.

Per tant, el conjunt de dades tenia alguns problemes importants que feien necessari un procés de neteja i validació abans de poder fer l'anàlisi.

## 7. Anàlisi de les dades netes

### Quins indicadors has calculat i per què?
He calculat diferents indicadors:
- **Total d'unitats:** per conèixer el volum total de productes venuts.
- **Distància mediana:** per conèixer el valor central de les distàncies.
- **Distància màxima:** per identificar la distància més elevada.
- **Distància mínima:** per identificar la distància més baixa.

Aquests indicadors permeten tenir una visió general del conjunt de dades.

### Quines agrupacions o comparacions has fet?
He agrupat les unitats venudes per:
- Família esportiva.
- Botiga.
- Article.

Això permet comparar quines famílies, botigues i articles tenen més unitats venudes.

### Quins resultats consideres més rellevants?
El resultat més destacat és que la botiga de **Girona és la que té més unitats venudes, amb un total de 892 unitats**.

Aquest resultat permet identificar quina botiga té el volum de vendes més elevat.

## 8. Conclusions i possibles millores

### Què has après sobre el conjunt de dades?
He après que el conjunt de dades permet analitzar les vendes de productes esportius segons la botiga, la família esportiva i l'article.

També he comprovat que abans de fer qualsevol anàlisi és molt important revisar i netejar les dades, perquè els errors poden afectar els resultats.

A més, he après a adaptar el codi de l'AC3 a un conjunt de dades diferent, modificant les variables i les operacions necessàries.

### Quines limitacions té l'anàlisi?
L'anàlisi té algunes limitacions:
- S'han rebutjat 30 registres per problemes de qualitat.
- Els resultats només representen les dades disponibles.
- No es pot garantir que tots els registres originals siguin correctes.
- L'anàlisi de les unitats no permet conèixer directament els beneficis econòmics perquè no disposem del preu.

### Quines mesures proposaries per millorar la qualitat de les dades en origen?
Proposaria les mesures següents:
- Utilitzar camps obligatoris als formularis d'introducció de dades.
- Validar els nombres perquè només acceptin valors numèrics.
- Comprovar que les dates siguin reals i tinguin un format correcte.
- Evitar espais innecessaris als camps de text.
- Utilitzar formats estandarditzats per a totes les botigues.
- Fer comprovacions automàtiques abans de guardar els registres.

## CONCLUSIÓ FINAL

En conclusió, aquesta pràctica m'ha permès aplicar els coneixements de l'AC3 a un conjunt de dades diferent.

He reutilitzat gran part del codi anterior, però he adaptat les variables, les conversions i les operacions d'anàlisi a les noves necessitats.

El procés de neteja ha estat fonamental per passar de 120 registres inicials a 90 registres vàlids.

Finalment, he pogut analitzar les vendes per botiga, família esportiva i article, i identificar que Girona és la botiga amb més unitats venudes, amb 892 unitats.

Aquesta experiència m'ha ajudat a entendre la importància de la qualitat de les dades i de la validació abans de fer qualsevol anàlisi.