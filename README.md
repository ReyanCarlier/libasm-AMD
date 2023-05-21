# libasm-AMD
L'objectif de ce projet est de se familiariser avec le langage assembleur (ARM).

# Registres :
L'ARM a 16 registres, étiquetés R0 à R15.
Ils sont tous des registres généraux, à l'exception de R13 qui est généralement utilisé comme pointeur de pile (SP), R14 qui est le registre de lien (LR) utilisé pour stocker l'adresse de retour lors d'un appel de fonction, et R15 qui est le compteur de programme (PC).

# Instructions :

## Instructions de mouvement de données

- `MOV`: Move. Copie une valeur dans un registre.
- `MVN`: Move Negative. Copie l'inverse d'une valeur dans un registre.

## Instructions de chargement et de stockage

- `LDR`: Load. Charge une valeur de la mémoire dans un registre.
- `STR`: Store. Stocke une valeur d'un registre dans la mémoire.
- `PUSH`: Push. Pousse un ou plusieurs registres sur la pile.
- `POP`: Pop. Enlève un ou plusieurs registres de la pile.

## Instructions arithmétiques

- `ADD`: Add. Ajoute deux valeurs.
- `SUB`: Subtract. Soustrait deux valeurs.
- `MUL`: Multiply. Multiplie deux valeurs.
- `DIV`: Divide. Divise deux valeurs.

## Instructions logiques

- `AND`: And. Effectue une opération logique AND entre deux valeurs.
- `ORR`: Or. Effectue une opération logique OR entre deux valeurs.
- `EOR`: Exclusive Or. Effectue une opération logique XOR entre deux valeurs.
- `BIC`: Bit Clear. Efface certains bits d'une valeur.

## Instructions de comparaison

- `CMP`: Compare. Compare deux valeurs et met à jour les indicateurs de l'état.
- `TST`: Test. Teste certains bits d'une valeur.

## Instructions de branchement

- `B`: Branch. Saute à un nouvel emplacement dans le code.
- `BL`: Branch with Link. Appelle une fonction.
- `BX`: Branch and Exchange. Saute à un nouvel emplacement et change le mode d'exécution.
- `BLX`: Branch with Link and Exchange. Appelle une fonction et change le mode d'exécution.

## Autres instructions

- `SWI`: Software Interrupt. Déclenche une interruption logicielle.
- `NOP`: No Operation. Ne fait rien.

## Instructions Conditionnelles
De nombreuses instructions ARM peuvent être conditionnelles, en ajoutant des suffixes à l'instruction. Par exemple, `ADDNE R3, R1, R2` ajoutera R1 et R2 seulement si la dernière condition de comparaison était non égale (NE).
Il existe de nombreux autres suffixes pour différentes conditions.
La plupart des instructions peuvent être conditionnellement exécutées en ajoutant un suffixe conditionnel à l'instruction.
Ce suffixe est déterminé par l'état des quatre drapeaux dans le registre d'état du processeur : Z (zéro), N (négatif), C (retenue) et V (débordement).

Voici les principaux suffixes de condition ARM et leurs significations :

- `EQ` : Égal (Z flag set)
- `NE` : Non égal (Z flag clear)
- `CS / HS` : Retenue / supérieur ou égal sans signe (C flag set)
- `CC / LO` : Pas de retenue / inférieur sans signe (C flag clear)
- `MI` : Négatif (N flag set)
- `PL` : Positif ou zéro (N flag clear)
- `VS` : Débordement (V flag set)
- `VC` : Pas de débordement (V flag clear)
- `HI` : Supérieur sans signe (C flag set and Z flag clear)
- `LS` : Inférieur ou égal sans signe (C flag clear or Z flag set)
- `GE` : Supérieur ou égal (N flag equals V flag)
- `LT` : Inférieur (N flag not equal to V flag)
- `GT` : Supérieur (Z flag clear and N flag equals V flag)
- `LE` : Inférieur ou égal (Z flag set or N flag not equal to V flag)
- `AL` : Toujours (aucun test, cette instruction est toujours exécutée)

Il est important de noter que le suffixe conditionnel est basé sur le résultat de la dernière opération qui a affecté les drapeaux. Par exemple, si vous effectuez une opération de soustraction avec `SUBS`, puis une instruction avec le suffixe `EQ`, cette instruction sera exécutée si le résultat de la soustraction était zéro.
