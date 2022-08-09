# Qu'est ce que Merise ?

## Merise ( qui se prononce _meurise_ non pas _mérise_ ) est une methode d'analyse, de conception de gestion de projet informatiques.

## Quel est la définition de l'acronyme MERISE:

- <span style="color:#1582B8">_M_</span>éthode
- <span style="color:#1582B8">_É_</span>tude
- <span style="color:#1582B8">_R_</span>éalisation
- <span style="color:#1582B8">_I_</span>nformatique
- <span style="color:#1582B8">_S_</span>ystème
- <span style="color:#1582B8">_E_</span>ntreprise

---

## Le dictionnaire des donnèes qu'est ce que c'est ?

### C'est une étape intermédiaire qui peut avoir son importance surtout si on travaille en groupe sur la même base de données. C'est un document qui regroupe toutes les données qu'on aura à conserver dans notre base de données ( qui figuereront donc dans le _MCD_).

#### Un exemple de dictionnaire des données:

<figure>
  <img src="Dico.png" alt="" width="500" />
</figure>

### Merise repose sur plusieurs modèle ou schéma parmi eux nous avons:

le **_MCD_** (modèle de conception de donnée):

<figure>
  <img src="MCD.png" alt="" width="500" />
</figure>

le **_MLD_** (modèle logique de donnée):

<figure>
  <img src="MLD.png" alt="" width="500" />
</figure>

le **_MPD_** (modèle physique de donnée):

<figure>
  <img src="MPD.png" alt="" width="500" />
</figure>

et bien d'autres schèmas.

---

Voici le script que nous a générer notre MLD:

```
CREATE TABLE Formations(
   unique_number VARCHAR(50),
   name_formation VARCHAR(50) NOT NULL,
   PRIMARY KEY(unique_number)
);

CREATE TABLE Apprenant(
   unique_number VARCHAR(50),
   name VARCHAR(50),
   prenom VARCHAR(50),
   address VARCHAR(50) NOT NULL,
   date_of_birth DATE,
   unique_number_1 VARCHAR(50) NOT NULL,
   PRIMARY KEY(unique_number),
   FOREIGN KEY(unique_number_1) REFERENCES Formations(unique_number)
);

CREATE TABLE Formateur(
   unique_number VARCHAR(50),
   name VARCHAR(50),
   prenom VARCHAR(50),
   PRIMARY KEY(unique_number)
);

CREATE TABLE Validation_module(
   unique_number VARCHAR(50),
   validate_module LOGICAL,
   PRIMARY KEY(unique_number)
);

CREATE TABLE Finished_formation(
   unique_number VARCHAR(50),
   finished LOGICAL,
   PRIMARY KEY(unique_number)
);

CREATE TABLE Cours_module(
   unique_number VARCHAR(50),
   author VARCHAR(50),
   name VARCHAR(50),
   Content VARCHAR(50),
   objectif VARCHAR(50),
   during VARCHAR(50),
   tag VARCHAR(50),
   unique_number_1 VARCHAR(50) NOT NULL,
   unique_number_2 VARCHAR(50) NOT NULL,
   PRIMARY KEY(unique_number, author),
   FOREIGN KEY(unique_number_1) REFERENCES Formations(unique_number),
   FOREIGN KEY(unique_number_2) REFERENCES Formateur(unique_number)
);
```
