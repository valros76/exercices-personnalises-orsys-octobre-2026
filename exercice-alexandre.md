# 🖥️ Exercice JavaScript — Supervision de serveurs

> **Profil : Alexandre — SysAdmin RATP**  
> **Niveau : débutant JavaScript**  
> **Durée estimée : 35 à 45 minutes**

## 🎯 Objectif

Tu vas manipuler des données représentant plusieurs serveurs et construire progressivement un petit outil de **supervision**.

L'objectif est de réutiliser plusieurs notions vues en cours :

- variables et constantes ;
- tableaux ;
- objets ;
- conditions `if / else` ;
- opérateurs `&&` et `||` ;
- boucles `forEach()` ;
- fonctions personnalisées ;
- `filter()` ;
- `find()` ;
- compteurs ;
- retour d'un objet depuis une fonction.

L'exercice est volontairement proche d'une situation de supervision informatique.

---

# 📊 Les données

Commence avec ce tableau :

```js
const serveurs = [
    {
        nom: "SRV-PARIS-01",
        ip: "10.0.1.10",
        cpu: 42,
        ram: 68,
        statut: "online"
    },
    {
        nom: "SRV-PARIS-02",
        ip: "10.0.1.11",
        cpu: 87,
        ram: 91,
        statut: "online"
    },
    {
        nom: "SRV-LILLE-01",
        ip: "10.0.2.10",
        cpu: 23,
        ram: 45,
        statut: "offline"
    },
    {
        nom: "SRV-LYON-01",
        ip: "10.0.3.10",
        cpu: 76,
        ram: 72,
        statut: "online"
    }
];
```

Chaque objet représente un serveur.

Par exemple :

```js
{
    nom: "SRV-PARIS-01",
    ip: "10.0.1.10",
    cpu: 42,
    ram: 68,
    statut: "online"
}
```

signifie :

| Propriété | Signification |
|---|---|
| `nom` | Nom du serveur |
| `ip` | Adresse IP |
| `cpu` | Utilisation du processeur en % |
| `ram` | Utilisation de la mémoire en % |
| `statut` | État du serveur |

---

# 🟢 Mission 1 — Afficher les serveurs

Pour commencer, affiche dans la console le nom et l'adresse IP de chaque serveur.

Tu dois obtenir quelque chose ressemblant à :

```text
SRV-PARIS-01 - 10.0.1.10
SRV-PARIS-02 - 10.0.1.11
SRV-LILLE-01 - 10.0.2.10
SRV-LYON-01 - 10.0.3.10
```

### 💡 Indice

Le tableau contient plusieurs serveurs.

Tu peux utiliser `forEach()` :

```js
serveurs.forEach((serveur) => {
    // Ton code ici
});
```

À l'intérieur de la boucle, tu peux accéder aux propriétés de l'objet :

```js
serveur.nom
serveur.ip
```

---

# 🚨 Mission 2 — Détecter les problèmes

Un serveur doit être considéré comme **en alerte** si au moins une des conditions suivantes est vraie :

- le CPU est supérieur ou égal à `80 %` ;
- la RAM est supérieure ou égale à `80 %` ;
- le serveur est `offline`.

Affiche le nom des serveurs concernés.

Résultat attendu :

```text
ALERTE : SRV-PARIS-02
ALERTE : SRV-LILLE-01
```

### 💡 Indices

Tu peux utiliser une condition :

```js
if (condition) {
    console.log(...);
}
```

Il faut tester plusieurs conditions.

L'opérateur `||` signifie **OU** :

```js
condition1 || condition2
```

Par exemple :

```js
if (serveur.cpu >= 80 || serveur.ram >= 80) {
    // ...
}
```

Il faut également prendre en compte le statut :

```js
serveur.statut === "offline"
```

Tu peux donc combiner les trois conditions.

---

# 🧩 Mission 3 — Créer une fonction d'analyse

Maintenant, transforme la logique précédente en fonction.

Crée une fonction :

```js
analyserServeur(serveur)
```

Cette fonction doit recevoir **un serveur** et retourner :

- `"OK"` si le serveur ne présente aucun problème ;
- `"ALERTE"` s'il présente au moins un problème.

Exemple :

```js
console.log(analyserServeur(serveurs[0]));
```

Résultat :

```text
OK
```

Et :

```js
console.log(analyserServeur(serveurs[1]));
```

doit donner :

```text
ALERTE
```

### 💡 Structure de départ

```js
function analyserServeur(serveur) {

    // Vérifier les conditions

    if (...) {
        return "ALERTE";
    }

    return "OK";
}
```

### ❓ À réfléchir

Pourquoi est-il intéressant de mettre cette logique dans une fonction plutôt que de copier le `if` partout ?

---

# 🔎 Mission 4 — Filtrer les serveurs en alerte

Maintenant que tu possèdes une fonction permettant d'analyser un serveur, utilise-la pour créer un nouveau tableau :

```js
serveursEnAlerte
```

Ce tableau doit uniquement contenir les serveurs dont l'état est `"ALERTE"`.

### 💡 Indice

Utilise la méthode :

```js
filter()
```

Structure :

```js
const resultat = tableau.filter((element) => {
    return condition;
});
```

Dans ton cas, tu peux utiliser :

```js
analyserServeur(serveur) === "ALERTE"
```

### Résultat attendu

Le tableau `serveursEnAlerte` doit contenir :

```text
SRV-PARIS-02
SRV-LILLE-01
```

Tu peux vérifier avec :

```js
console.log(serveursEnAlerte);
```

---

# 📊 Mission 5 — Produire des statistiques

Maintenant, construis quelques statistiques sur ton parc de serveurs.

Tu dois déterminer :

- le nombre total de serveurs ;
- le nombre de serveurs `online` ;
- le nombre de serveurs `offline` ;
- le nombre de serveurs en alerte.

Le résultat attendu est :

```js
{
    total: 4,
    enLigne: 3,
    horsLigne: 1,
    alertes: 2
}
```

---

## 💡 Étape 1 — Compter les serveurs

Le nombre total de serveurs peut être obtenu avec :

```js
serveurs.length
```

---

## 💡 Étape 2 — Créer des compteurs

Tu peux créer des variables :

```js
let enLigne = 0;
let horsLigne = 0;
let alertes = 0;
```

Puis parcourir les serveurs :

```js
serveurs.forEach((serveur) => {

    // Tes conditions ici

});
```

---

## 💡 Étape 3 — Compter les serveurs online/offline

Tu peux tester le statut :

```js
if (serveur.statut === "online") {
    enLigne++;
}
```

Et pour les serveurs hors ligne :

```js
if (serveur.statut === "offline") {
    horsLigne++;
}
```

---

## 💡 Étape 4 — Compter les alertes

Tu peux réutiliser la fonction créée précédemment :

```js
if (analyserServeur(serveur) === "ALERTE") {
    alertes++;
}
```

---

# 🗃️ Mission 6 — Faire le lien avec SQL

Tu travailles régulièrement avec SQL.

Imaginons qu'une requête SQL nous retourne ce tableau :

```js
const resultatsSQL = [
    {
        nom: "SRV-PARIS-01",
        cpu: 42
    },
    {
        nom: "SRV-PARIS-02",
        cpu: 87
    },
    {
        nom: "SRV-LILLE-01",
        cpu: 23
    },
    {
        nom: "SRV-LYON-01",
        cpu: 76
    }
];
```

En SQL, tu pourrais chercher le serveur :

```sql
SELECT *
FROM serveurs
WHERE nom = 'SRV-PARIS-02';
```

En JavaScript, utilise `find()` pour obtenir le même résultat.

Crée une variable :

```js
const serveurRecherche = ...
```

Elle doit contenir le serveur dont le nom est :

```text
SRV-PARIS-02
```

### 💡 Indice

La structure de `find()` est :

```js
const resultat = tableau.find((element) => {
    return condition;
});
```

Dans ton cas, la condition doit comparer :

```js
serveur.nom
```

avec :

```text
"SRV-PARIS-02"
```

Puis affiche le résultat :

```js
console.log(serveurRecherche);
```

---

# 🏆 Mission finale — Générer un rapport

Tu vas maintenant regrouper ton travail dans une fonction :

```js
genererRapport(serveurs)
```

Cette fonction doit retourner un objet contenant :

```js
{
    total: 4,
    enLigne: 3,
    horsLigne: 1,
    alertes: 2
}
```

### Structure de départ

```js
function genererRapport(serveurs) {

    let enLigne = 0;
    let horsLigne = 0;
    let alertes = 0;

    serveurs.forEach((serveur) => {

        // Compter les serveurs online

        // Compter les serveurs offline

        // Compter les alertes

    });

    return {
        total: serveurs.length,
        enLigne: enLigne,
        horsLigne: horsLigne,
        alertes: alertes
    };
}
```

Puis :

```js
const rapport = genererRapport(serveurs);

console.log(rapport);
```

Tu dois obtenir :

```text
{
    total: 4,
    enLigne: 3,
    horsLigne: 1,
    alertes: 2
}
```

---

# ⭐ Bonus — Aller plus loin

Si tu as terminé avant la fin du temps imparti, améliore ton système.

## Bonus 1 — Afficher un rapport lisible

Crée une fonction :

```js
afficherRapport(rapport)
```

Elle pourrait afficher :

```text
===== RAPPORT SERVEURS =====

Serveurs analysés : 4
Serveurs en ligne : 3
Serveurs hors ligne : 1
Serveurs en alerte : 2
```

---

## Bonus 2 — Identifier le serveur avec le CPU le plus élevé

Utilise les données `resultatsSQL` et trouve le serveur ayant le CPU le plus élevé.

Résultat attendu :

```text
SRV-PARIS-02 - 87%
```

> Tu peux utiliser `forEach()` et une variable permettant de conserver le serveur ayant la valeur maximale.

---

# 🧠 À retenir

Dans cet exercice, tu as reproduit une logique assez proche de celle que tu peux rencontrer lorsqu'un script exploite des données provenant d'une base SQL.

Le parallèle est notamment :

| SQL | JavaScript |
|---|---|
| Table | Tableau |
| Ligne | Objet |
| Colonne | Propriété |
| `WHERE` | `filter()` |
| Recherche d'une ligne | `find()` |
| Parcours des résultats | `forEach()` |
| Calculs sur les résultats | Variables + boucles |
| Fonction métier | Fonction JavaScript |

L'objectif n'est donc pas seulement de connaître la syntaxe JavaScript, mais de savoir **transformer un problème en étapes algorithmiques**.

---

## ✅ Concepts travaillés

- [x] Variables
- [x] Constantes
- [x] Tableaux
- [x] Objets
- [x] Propriétés d'un objet
- [x] Conditions
- [x] Opérateurs `||`
- [x] `forEach()`
- [x] Fonctions personnalisées
- [x] `filter()`
- [x] `find()`
- [x] Compteurs
- [x] Retour d'une valeur
- [x] Retour d'un objet
- [x] Manipulation de données
- [x] Raisonnement algorithmique