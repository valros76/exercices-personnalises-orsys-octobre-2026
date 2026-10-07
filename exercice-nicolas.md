# 🌐 Exercice JavaScript — Supervision d'un parc réseau

> **Profil : Nicolas — Technicien systèmes / réseaux**  
> **Contexte : utilisation quotidienne de NetShot**  
> **Niveau : débutant JavaScript**  
> **Durée estimée : 35 à 45 minutes**

## 🎯 Objectif

Tu vas créer un petit script JavaScript permettant d'analyser l'état d'un parc d'équipements réseau.

Le contexte technique devrait être familier : switches, routeurs, équipements joignables, latence, version logicielle, etc.

L'objectif est cependant de travailler **la logique JavaScript**, sans utiliser de bibliothèque externe.

Tu vas notamment manipuler :

- tableaux ;
- objets ;
- propriétés ;
- conditions ;
- `forEach()` ;
- fonctions ;
- `filter()` ;
- `find()` ;
- `map()` ;
- `reduce()` ;
- `some()` ;
- `every()`.

---

# 📡 Les équipements

Commence avec les données suivantes :

```js
const equipements = [
    {
        nom: "SW-PARIS-01",
        type: "switch",
        ip: "10.10.1.10",
        latence: 12,
        version: "15.2",
        joignable: true
    },
    {
        nom: "SW-PARIS-02",
        type: "switch",
        ip: "10.10.1.11",
        latence: 85,
        version: "15.2",
        joignable: true
    },
    {
        nom: "RTR-LILLE-01",
        type: "routeur",
        ip: "10.10.2.10",
        latence: 24,
        version: "16.1",
        joignable: true
    },
    {
        nom: "SW-LILLE-01",
        type: "switch",
        ip: "10.10.2.11",
        latence: 0,
        version: "14.8",
        joignable: false
    },
    {
        nom: "RTR-LYON-01",
        type: "routeur",
        ip: "10.10.3.10",
        latence: 42,
        version: "16.1",
        joignable: true
    }
];
```

---

# 🟢 Mission 1 — Afficher les équipements

Affiche pour chaque équipement :

```text
SW-PARIS-01 - 10.10.1.10
SW-PARIS-02 - 10.10.1.11
RTR-LILLE-01 - 10.10.2.10
...
```

Utilise `forEach()`.

---

# 🚨 Mission 2 — Détecter les équipements problématiques

Un équipement doit être considéré comme **problématique** si :

- il n'est pas joignable ;
- ou sa latence est supérieure à `50 ms`.

Affiche les équipements concernés.

Résultat attendu :

```text
ALERTE : SW-PARIS-02
ALERTE : SW-LILLE-01
```

---

# 🧩 Mission 3 — Créer une fonction de diagnostic

Crée :

```js
diagnostiquerEquipement(equipement)
```

La fonction doit retourner :

```text
"OK"
```

si l'équipement fonctionne normalement et :

```text
"ALERTE"
```

dans le cas contraire.

Exemple :

```js
console.log(diagnostiquerEquipement(equipements[0]));
```

doit retourner :

```text
OK
```

---

# 🔎 Mission 4 — Construire la liste des alertes

Crée :

```js
const equipementsEnAlerte
```

en utilisant `filter()`.

Le tableau doit contenir uniquement les équipements pour lesquels :

```js
diagnostiquerEquipement(equipement) === "ALERTE"
```

Affiche ensuite leurs noms.

---

# 🔍 Mission 5 — Rechercher un équipement

Imagine qu'un technicien recherche un équipement précis.

Crée une fonction :

```js
trouverEquipement(equipements, nom)
```

Elle doit permettre de rechercher un équipement à partir de son nom.

Par exemple :

```js
trouverEquipement(equipements, "RTR-LILLE-01");
```

doit retourner l'objet correspondant.

Teste également une recherche qui n'existe pas :

```js
trouverEquipement(equipements, "SW-MARSEILLE-01");
```

Observe le résultat.

---

# 📊 Mission 6 — Statistiques du parc

Construis un objet contenant :

```js
{
    total: ...,
    joignables: ...,
    nonJoignables: ...,
    alertes: ...
}
```

Tu dois déterminer les quatre valeurs à partir du tableau `equipements`.

### Résultat attendu

```js
{
    total: 5,
    joignables: 4,
    nonJoignables: 1,
    alertes: 2
}
```

Tu peux utiliser `forEach()`, `filter()` ou une combinaison de plusieurs méthodes.

---

# ⚡ Mission 7 — Calculer la latence moyenne

Calcule la latence moyenne des équipements **joignables uniquement**.

La formule est :

```text
somme des latences / nombre d'équipements
```

Les équipements non joignables ne doivent pas être pris en compte.

Le résultat doit être arrondi à deux décimales.

### 💡 Réflexion

Tu peux avoir besoin de deux étapes :

1. conserver uniquement les équipements joignables ;
2. additionner leurs latences.

Tu peux donc combiner plusieurs méthodes JavaScript.

---

# 🏷️ Mission 8 — Préparer les données pour un affichage

Imagine qu'une future interface doit afficher uniquement :

- le nom ;
- le type ;
- la latence ;
- l'état.

Crée :

```js
const tableauDeBord
```

Le résultat doit ressembler à :

```js
[
    {
        nom: "SW-PARIS-01",
        type: "switch",
        latence: 12,
        etat: "OK"
    },
    ...
]
```

Utilise `map()`.

Pour déterminer `etat`, réutilise :

```js
diagnostiquerEquipement(equipement)
```

---

# 🧪 Mission 9 — Vérifier le parc

Utilise `some()` pour déterminer s'il existe au moins un équipement :

- non joignable ;
- ou présentant une latence supérieure à `100 ms`.

Stocke le résultat dans :

```js
const problemeCritique
```

Le résultat doit être un booléen.

---

# ✅ Mission 10 — Vérifier si le parc est conforme

Utilise `every()` pour vérifier que **tous les équipements joignables** ont une latence inférieure ou égale à `100 ms`.

Stocke le résultat dans :

```js
const parcConforme
```

---

# 🏆 Mission finale — Générer un rapport réseau

Regroupe maintenant ton travail dans une fonction :

```js
genererRapportReseau(equipements)
```

Elle doit retourner :

```js
{
    total: ...,
    joignables: ...,
    nonJoignables: ...,
    alertes: ...,
    latenceMoyenne: ...,
    problemeCritique: ...,
    parcConforme: ...
}
```

Exemple :

```js
const rapport = genererRapportReseau(equipements);

console.log(rapport);
```

L'objectif est d'obtenir un **objet unique contenant toutes les informations importantes du parc**.

---

# ⭐ Bonus — Identifier les équipements obsolètes

On considère qu'un équipement utilisant une version :

```text
14.8
```

est obsolète.

Crée :

```js
const equipementsObsoletes
```

qui contient uniquement les équipements concernés.

---

# 🚀 Bonus 2 — Trouver l'équipement ayant la plus forte latence

Crée :

```js
trouverPlusForteLatence(equipements)
```

La fonction doit retourner l'équipement ayant la latence la plus élevée.

Résultat attendu :

```text
SW-PARIS-02 - 85 ms
```

---

# 🧠 Questions de réflexion

À la fin de l'exercice, sois capable d'expliquer :

### 1. Pourquoi utiliser `filter()` pour construire la liste des alertes ?

### 2. Pourquoi utiliser `find()` pour rechercher un équipement ?

### 3. Pourquoi `map()` est-il adapté à la création de `tableauDeBord` ?

### 4. Quelle différence entre :

```js
some()
```

et :

```js
every()
```

### 5. Pourquoi créer une fonction :

```js
diagnostiquerEquipement()
```

plutôt que de répéter les conditions dans plusieurs endroits ?

---

# 🎯 Défi supplémentaire — Sans `if`

Pour terminer, reprends la création de :

```js
tableauDeBord
```

et essaie de produire le même résultat **sans écrire de boucle `for` ni de `if`**.

Utilise uniquement les méthodes de tableaux vues pendant le cours.

---

# ✅ Concepts travaillés

- [x] Variables
- [x] Constantes
- [x] Tableaux
- [x] Objets
- [x] Propriétés
- [x] Conditions
- [x] Opérateurs logiques
- [x] `forEach()`
- [x] Fonctions personnalisées
- [x] `filter()`
- [x] `map()`
- [x] `find()`
- [x] `reduce()`
- [x] `some()`
- [x] `every()`
- [x] Calculs
- [x] Transformation de données
- [x] Analyse de données
- [x] Raisonnement algorithmique