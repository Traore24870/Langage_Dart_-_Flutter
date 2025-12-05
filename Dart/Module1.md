
-----

# 🚀 Cours Express de Programmation Dart (2 Heures)

## I. Introduction à Dart

Le Dart est un langage polyvalent, essentiel pour **Flutter** (applications mobiles/web/bureau).

-----

## II. Les Fondamentaux du Langage

### 1\. Variables et Types de Données

Les variables stockent les informations.

| Type de Donnée | Description | Exemple de Déclaration en Dart |
| :--- | :--- | :--- |
| **`int`** | Nombres entiers. | `int age = 27;` |
| **`double`** | Nombres décimaux. | `double prix = 19.99;` |
| **`String`** | Texte. | `String nom = "Driss";` |
| **`bool`** | Vrai/Faux. | `bool estMajeur = true;` |

#### 📝 Code d'Exploitation et Explication :

```dart
// Déclaration d'une variable entière (int) et affectation d'une valeur.
int age = 27; 

// Déclaration d'une variable de type chaîne de caractères (String).
String nom = "Driss";

// Affiche une chaîne de caractères en utilisant l'interpolation ($) pour inclure les variables.
print("Bonjour, je m'appelle $nom et j'ai $age ans.");
```

-----

### 2\. Structures de Contrôle

Elles dirigent le flux d'exécution.

#### A. Conditionnelles (`if`, `else`)

```dart
// Déclaration d'une variable booléenne.
bool estMajeur = true;

// Début de la structure conditionnelle. La condition est testée.
if (estMajeur) {
    // Ce bloc est exécuté si la condition (estMajeur est vrai) est vraie.
    print("Je suis majeur(e) !");
} else {
    // Ce bloc est exécuté si la condition est fausse.
    print("Je ne suis pas encore majeur(e).");
}
```

#### B. Boucles (`for`, `while`)

```dart
// Exemple de boucle for : idéal quand on sait combien de fois on doit itérer.
for (int i = 0; i < 3; i++) {
    // i=0, puis i=1, puis i=2. Le bloc s'exécute 3 fois.
    print("Itération $i");
}

// Exemple de boucle while : idéal quand on itère tant qu'une condition reste vraie.
int compteur = 0;
// La boucle continue tant que 'compteur' est strictement inférieur à 2.
while (compteur < 2) {
    print("Compteur: $compteur");
    // Incrémente le compteur pour éviter une boucle infinie.
    compteur++;
}
```

-----

### 3\. Les Fonctions

Blocs de code réutilisables.

#### 📝 Code d'Exploitation et Explication :

```dart
// Fonction nommée 'somme' qui prend deux entiers (a et b) et renvoie un entier (int).
int somme(int a, int b) {
    // Le mot-clé 'return' indique la valeur que la fonction renvoie.
    return a + b;
}

// Fonction qui ne renvoie rien (void) et a un paramètre obligatoire (nom) 
// et un paramètre optionnel nommé (age) avec une valeur par défaut (0).
void afficherDetails(String nom, {int age = 0}) {
    print("Nom: $nom, Age: $age");
}


// Appel de la fonction 'somme' et stockage du résultat dans une variable.
int resultat = somme(5, 3);
print("La somme est : $resultat");

// Appel de la fonction 'afficherDetails' en spécifiant le paramètre optionnel 'age:'.
afficherDetails("Driss", age: 27); 
// Appel sans spécifier l'âge; la valeur par défaut (0) est utilisée.
afficherDetails("Alice");          
```

-----

## III. Gestion des Données et POO

### 4\. Collections de Données

Structures pour gérer des groupes de données.

#### A. Listes (Tableaux Ordonnés)

```dart
// Création d'une liste d'entiers explicite.
List<int> nombres = [1, 2, 3];
// Ajout d'un nouvel élément à la fin de la liste.
nombres.add(4); 

print("La liste : $nombres");
// Accès à un élément par son index (les index commencent à 0).
print("Élément à l'index 0 : ${nombres[0]}"); 
```

#### B. Maps (Paires Clé-Valeur)

```dart
// Création d'une Map où les clés et les valeurs sont des Strings.
Map<String, String> capitales = {
    "France": "Paris",
    "Espagne": "Madrid"
};

// Ajout d'une nouvelle paire Clé-Valeur ou mise à jour si la clé existe.
capitales["Italie"] = "Rome";

// Accès à la valeur en utilisant la clé.
print("Capitale de l'Italie : ${capitales["Italie"]}");
```

### 5\. Classes et Objets (POO)

Un modèle pour créer des objets concrets.

#### 📝 Code d'Exploitation et Explication :

```dart
// 1. Définition de la classe 'Personne'.
class Personne {
    // Propriétés (Attributs) de la classe.
    String nom;
    int age;

    // Constructeur : Méthode spéciale utilisée lors de la création de l'objet.
    // 'this.nom' et 'this.age' sont des "initializing formals" pour initialiser
    // les propriétés de la classe avec les valeurs passées.
    Personne(this.nom, this.age);

    // Méthode (Comportement) associée à cette classe.
    void sePresenter() {
        print("Bonjour, je m'appelle $nom et j'ai $age ans.");
    }
}

// 2. Création d'un objet (instance de la classe Personne) en appelant le constructeur.
Personne personne1 = Personne("Driss", 27);

// 3. Utilisation des propriétés et méthodes.
// Accès direct à la propriété 'nom' de l'objet.
print(personne1.nom); 
// Appel de la méthode 'sePresenter' de l'objet.
personne1.sePresenter(); 
```

-----

## IV. Avancé : Stabilité et Performance

### 6\. Gestion des Erreurs

Utilisation des blocs `try-catch` pour capturer les exceptions.

#### 📝 Code d'Exploitation et Explication :

```dart
try {
    // Le code à l'intérieur de 'try' est surveillé pour les erreurs (exceptions).
    // L'opérateur ~/ effectue une division entière. La division par zéro génère une exception.
    var resultat = 10 ~/ 0; 
    print("Ce message ne s'affichera pas.");
} catch (e) {
    // Si une exception est levée dans 'try', le flux saute ici. 
    // 'e' contient l'objet exception.
    print("Une erreur s'est produite : $e");
}
```

### 7\. Programmation Asynchrone

Gère les opérations qui prennent du temps avec **`Future`** et **`async/await`**.

#### 📝 Code d'Exploitation et Explication :

```dart
// Fonction qui renvoie un 'Future<String>', indiquant qu'elle produira une chaîne de caractères plus tard.
Future<String> obtenirDonnees() {
    // Future.delayed simule une opération qui prend du temps (ici, 2 secondes).
    return Future.delayed(Duration(seconds: 2), () => "Données reçues");
}

// Fonction marquée 'async' : elle peut contenir des appels 'await'.
Future<void> exempleAsynchrone() async {
    print("Début de l'opération...");

    // 'await' suspend la fonction à ce point jusqu'à ce que le Future 'obtenirDonnees()' soit terminé.
    // L'exécution du programme principal (main thread) n'est PAS bloquée pendant ce temps.
    var resultat = await obtenirDonnees();

    print("Fin de l'opération.");
    print("Résultat : $resultat");
}

// Le programme démarre l'exécution de la fonction asynchrone.
exempleAsynchrone();
// Le reste du code du programme principal peut s'exécuter immédiatement après cet appel.
print("Ce message s'affiche avant le résultat des données.");
```

-----


