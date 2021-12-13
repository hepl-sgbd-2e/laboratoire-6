# Exercices sur les contraintes et déclencheurs

Les exercices de ce laboratoire sont à réaliser dans la base de données Hôpital.

## Contrainte 1

Ajouter, dans la table Patients, les contraintes applicatives suivantes :

* Le sexe doit toujours être connu et doit être égal a `F` ou `M`
* L'état civil doit toujours être connu et doit être égal à `C`, `M`, `D` ou `V`
* Le groupe sanguin doit être égal à `A`, `B`, `O` ou `AB` 
* Les deux derniers caractères du compte bancaire sont le reste
  de la division des dix premiers caractères par 97
* Construire un jeu de commandes permettant de tester ces contraintes.

Afficher toutes les contraintes spécifiées sur la table Patients.

```sql
-- Afficher les contraintes définies sur la table Patients


-- Ajouter les nouvelles contraintes : 

-- Réexécuter la requête pour afficher les contraintes définies sur la table Patients et voir ce qui a été ajouté.

```

## Déclencheur 1

Écrire et tester un déclencheur `PatientsInsertNrSis` qui permet d'initialiser automatiquement le NrSis d'un patient.
Le `NrSis` est constitué de la date de naissance du patient `YYMMDD` suivi d'un numéro de 5 chiffres. Soit, par
exemple `75123000001`. Ce numéro de 5 chiffres est le dernier numéro enregistré dans la table Patients + 1. Cette
contrainte sera vérifiée lors de l'insertion d'un patient.

```sql

```

> Faire un test avec toutes valeurs correctes, sans préciser de `NrSis` :
>
> ```sql
> 
> ```
>
> Faire un test avec toutes valeurs correctes en précisant un NrSis bidon, vérifier résultat :
>
> ```sql
> 
> ```
>
> Faire un test avec date de naissance nulle :
>
> ```sqlite
> 
> ```

## Déclencheur 2

Écrire et tester un déclencheur `HopitauxServicesNbreMed` qui va permettre de mettre à jour automatiquement la
colonne `NbreMedecins` de la table `HopitauxServices` à chaque insertion, modification ou suppression sur la
table `MedecinsServices`. Construire un jeu de commandes permettant de tester ce déclencheur.

```sql

```

Ajouter un enregistrement dans `MedecinsServices`, voir changement dans `HopitauxServices`

```sql

```

Supprimer un enregistrement de `MedecinsServices` et voir changement dans `HopitauxServices` (Rollback)

```sql

```

Modifier un enregistrement de `MedecinsServices` (NrHopital et/ou NrService) et voir changements
dans `HopitauxServices` (Rollback)

```sql

```

## Déclencheur 3

Écrire et tester un déclencheur `PatientsUpdateNrSis` qui va permettre de gérer la mise à jour du numéro de SIS du patient
sachant que l'option `ON UPDATE CASCADE` n'existe pas en Oracle. Cette mise à jour du numéro de SIS sera exécutée lors
de la modification de la date de naissance du patient. Construire un jeu de commandes permettant de tester ce
déclencheur.

```sql

```

Modifier la date de naissance d'un patient et constater les modifications dans les tables `Patients`,  `PatientsMedecins` et `Allergies`.
Mettre la date de naissance d'un patient à `NULL` et vérifier que l'on récupère bien le message d'erreur et qu'aucune
modification n'est effectuée dans les 3 tables.

```sql

```

## Déclencheur 4

Écrire et tester un déclencheur `PatientsDelNrSIS` qui va permettre de gérer l'option `ON DELETE CASCADE` lors de la
suppression d'un patient. Construire un jeu de commandes permettant de tester ce déclencheur.

```sql

```

> 

```sql

```

## Synthèse

Afficher le nom, le type, la date de création et le statut de tous les objets et de toutes les contraintes que vous avez
créés dans votre schéma hôpital.

```sql

```
