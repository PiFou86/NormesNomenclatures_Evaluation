# Normes de programmation et notation


**Certaines règles pourraient être sorties du documnent et généralisées à toutes les nomenclatures** 


**Document en cours de rédaction**


## Normes C#

### C#000 - Langue

Sauf indication contraire dans l'énoncé, les différents éléments de vos programmes doivent utiliser la langue française. Les fautes de grammaire et d'orthographe sont pénalisées comme décrit dans la [PÉA - 6.1.8](https://www.csfoy.ca/fileadmin/documents/notre_cegep/politiques_et_reglements/5.9_PolitiqueEvaluationApprentissages_2019.pdf).

Le nom des différentes entités ne doit pas contenir de diacritique (accent, cédille, etc.).

**Pénalité de non respect de cette régle :**

- -1/2% par faute jusqu'à concurrence de 10% de la note globale

### C#001 - Nom d'un projet

#### C#001S - Projets standards (exécutable / librairie)

Le nom d'un projet Visual Studio doit débuter par une majuscule, les mots composant le nom sont collés et débutent par une majuscule. En dehors des contractions proposées ci-dessous, les contractions ne sont pas acceptées. Le nom d'un projet doit être descriptif et donc permettre de comprendre ce qu'il contient.

**Contractions acceptées :**

- DAL : Data Access Layer - couche d'accès aux données
- BL : Bussiness Layer - couche affaire
- DTO : Data Transfert Object - objet de transfert de données

**Exemples :**

- ClientConsole
- ClientBL
- ClientDAL

**Attention** :

- Le nom du répertoire contenant le projet **doit** correspondre au nom du projet
- Certains énoncés imposent le nom du projet

**Pénalité de non respect de cette régle :**

- -1% par projet sur la note globale jusqu'à concurrence de 10% de la note globale

#### C#001P - Projets de tests unitaires

Le nom d'un projet Visual Studio de tests unitaires doit porter le nom du projet testé suivi de "Tests".

**Exemples :**

- ClientConsoleTests
- ClientBLTests
- ClientDALTests

**Attention** :

- Le nom du répertoire contenant le projet **doit** correspondre au nom du projet
- Certains énoncés imposent le nom du projet

**Pénalité de non respect de cette régle :**

- -1% par projet sur la note globale jusqu'à concurrence de 10% de la note globale

### C#002 - Nom d'une classe

#### C#002S - Nom d'une classe standard

Le nom d'une classe doit débuter par une majuscule, les mots composant le nom sont collés et débutent par une majuscule. Sauf énoncé explicite, le nom du fichier source doit correspondre exactement au nom de la classe. Le nom d'une classe doit être descriptif et donc permettre de comprendre ce qu'il contient.

**Exemples :**

- Client
- Voiture
- Questionnaire

**Pénalité de non respect de cette régle :**

- -1% par classe sur la note globale jusqu'à concurrence de 10% de la note globale

#### C#002T - Nom d'une classe de tests unitaires

Le nom d'une classe de tests unitaires doit porter le nom de la classe testée suivi de "Tests".

**Exemples :**

- ClientTests
- VoitureTests
- QuestionnaireTests

**Attention** :

- Si vous testez deux classes, vous devez avoir deux classes de tests, une par classe testée
- Certains énoncés imposent les noms de certaines classes

**Pénalité de non respect de cette régle :**

- -1% par classe sur la note globale jusqu'à concurrence de 10% de la note globale

### C#003 - Nom d'une méthode

#### C#003S - Nom d'une méthode standard

Le nom d'une méthode doit débuter par une majuscule, les mots composant le nom sont collés et débutent par une majuscule. Le nom d'une méthode doit être descriptif et donc permettre de comprendre ce que la méthode fait. Le nom doit débuter par un verbe d'action.

**Exemples :**

- ObtenirPrix
- CalculerTaxes
- SaisirLivre

**Attention** :

- Certains énoncés imposent les noms de certaines méthodes

**Pénalité de non respect de cette régle :**

- -20% de la note de la question si le nom imposé n'est pas utilisé
- Jusqu'à concurrence de -20% de la note de la question suivant le nom

#### C#003T - Nom d'une méthode de test

Le nom d'une méthode de test doit respecter la nomenclature suivante : ```NomMethodeTestee_DescriptionDuCas_ResultatAttendu```.

**Exemples :**

- ObtenirPrix_ArticleNExistePas_Exception
- CalculerTaxes_PanierVide_Zero
- CalculerTaxes_MontantTotalNegatif_Exception

**Attention** :

- Certains énoncés imposent les noms de certaines méthodes

**Pénalité de non respect de cette régle :**

- -20% de la note de la question si le nom imposé n'est pas utilisé
- Jusqu'à concurrence de -20% de la note de la question suivant le nom

### C#003+ - Méthode de test

Une méthode est associée à un et un seul cas de test. Plusieurs assertions peuvent cependant être effectuées dans le même test.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant le nom

### C#003+ - Méthode de test - structure

Respecter les 3A et séparer les blocs par un commentaire qui explicite le A. (// Arranger // Agir // Auditer)


Exemple 

```csharp
// Arranger

// Agir

// Auditer - plusieurs asserts
```

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant le nom

### C#004 - Nom des paramètres

p_valeurMinimale

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#005 - Préconditions dans les méthodes

Afin de sécuriser votre code, toutes les méthodes publiques doivent valider :

- Les paramètres d'entrée
- L'état interne de l'objet (Session 2 et +)

Ces validations sont effectuées en début de méthode.

Les constructeurs sont des méthodes particulières ce qui implique que les paramètres doivent aussi être validés au début du code, et cela même si vous utilisez des propriétés qui valident leur paramètre ```value```.

Si vous utilisez des propriétés, la méthode ```set``` doit aussi valider son paramètre d'entrée implicite ```value```.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#006 - Nom des variables locales

Le nom d'une variable locale doit débuter par une minuscule, les mots composant le nom sont collés et débutent par une majuscule. Le nom d'une variable doit être descriptif et donc permettre de comprendre ce qu'elle contient.

**Attention :**

- Il n'est pas accepté d'utiliser ```i```, ```j``` dans les boucles.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#007 - Nom des données membres d'objets

m_asdfasdfLsdfasdfKasdfasdf

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#007 - Nom des données membres de classes

AsdfasdfLsdfasdfKasdfasdf (static)

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#008 - Nom des propriétés

NomPropriete

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#009 - Utilisation des boucles

Les types de boucles ```for```, ```while```, ```do ... while``` et ```foreach``` doivent être utilisé dans les cas suivants :

- ```foreach``` : pour l'énumération de tous les éléments d'une collection ou d'une sous-collection (Session 2 et +)
- ```for``` : pour l'énumération d'un ensemble de valeurs : on connait le nombre d'itérations
- ```while``` : on ne connait pas le nombre d'itération à l'avance ou alors on parcours un itérateur (Itérateur : session 3 et +)
- ```do ... while``` :  on ne connait pas le nombre d'itérations à l'avance et on veut au moins exécuter le code une fois avant de valider la condition

**Attention :**

- L'énoncé peut imposer un type de boucle afin d'évaluer votre agilité dans le code

**Pénalité de non respect de cette régle :**

- -20 % de la note de la question si non respectée

### C#010 - Algorithme des méthodes - Abstraction / Design

Une méthode doit avoir des instructions du même niveau d'abstraction.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#010+ - Algorithme des méthodes - SRP

Une classe, méthode ne doit avoir qu'une raison de changer (i.e. une responsabilité)

Exemple : séparer saisie / traitement / affichage / persistance / etc.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#010++ - Algorithme des méthodes - DRY

Ne pas répéter du code. Utilisez les outils vus en cours (fonctions, méthodes, polymorphisme, desgin patterns, etc.).

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque

### C#011 - Algorithme des méthodes - Complexité

jhghhg

**Pénalité de non respect de cette régle :**

- Jusqu'à 100% de la note de la question si la question porte spécifiquement sur ce point
- Jusqu'à concurrence de -20% de la note de la question suivant ce qu'il manque




### C#012 - Algorithme des méthodes - Mise en page

#### ... - Indentation

Une méthode doit être agréable à lire. L'indentation est réalisée avec des espaces. 4 espaces par niveau.

Séparer les lignes de code par des sauts de lignes.

La dernière de chaque doit être vide et sans espace.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -5% de la note globale si non respectée

#### ... - Style d'accolades

Les accolades doivent débuter en début de ligne. Allman style

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -5% de la note globale si non respectée

#### ... - alternatives / boucles

Il est obligatoire d'utiliser des accolades même si vous n'avez qu'une instruction à exécuter.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -5% de la note globale si non respectée

#### ... - Opérateurs

Pour les opérateurs binaires, toujours laisser un espace avant et après. Pour les opérateurs unaires, toujours laisser un espace avant sauf si prédédé d'une parenthèse.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -5% de la note de la question si non respectée

#### ... - Évaluation d'expressions complexes

Dans le cas des expressions complexes, il est obligatoire d'utiliser des parenthèses afin d'expliciter la priorité des opérations.

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -5% de la note de la question si non respectée

### C#13 - évaluation booléenne

while / if

if (EstOuvert == false) !!

if (EstOuvert)

if (!EstOuvert)

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -1% de la note globale si non respectée

### C#14 - Initialisation des variables et des données

- Initialisez vos variables et données explicitement
- N'allouez pas de mémoire inutilement

List<...> lst... = new List<..>();
lst... = SaisirListe();

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -5% de la note de la question si non respectée pour le new
- Jusqu'à concurrence de -20% de la note de la question si non respectée pour le reste

### C#... - Alternatives

if vs switch

**Pénalité de non respect de cette régle :**

- Jusqu'à concurrence de -20% de la note de la question

### C# ... - Encapsulation

Le principe d'encapsulation doit être respecté. Attention au public / private et à l'utilisation des propriétés.

**Pénalité de non respect de cette régle :**

- Jusqu'à 100% si c'est l'objet de la question
- Jusqu'à concurrence de -20% de la note de la question

### C#... - Requêtes sur des données

À partir de la session 2, il est obligatoire d'utiliser les facilités du C# afin d'effectuer des requêtes sur des données en exploitant LINQ afin de faciliter la lecture du code.

**Pénalité de non respect de cette régle :**

- Jusqu'à 100% si c'est l'objet de la question
- Jusqu'à concurrence de -20% de la note de la question
