# 🏭 Exercice JavaScript — Analyse de production industrielle

> **Profil : Benoît — Bigard**  
> **Contexte : montée en compétence après 3 ans d'expérience**  
> **Niveau : intermédiaire**  
> **Durée estimée : 35 à 45 minutes**

## 🎯 Objectif

Tu vas développer un petit système d'analyse de données de production.

L'objectif n'est pas uniquement d'obtenir le bon résultat : tu dois être capable de **décomposer le problème**, choisir les bonnes méthodes JavaScript et créer des fonctions réutilisables.

Tu vas notamment travailler avec :

- tableaux ;
- objets ;
- conditions ;
- fonctions ;
- `forEach()` ;
- `filter()` ;
- `map()` ;
- `find()` ;
- `reduce()` ;
- `some()` ;
- `every()` ;
- composition de plusieurs traitements.

> ⚠️ Les solutions ne sont pas données étape par étape. Essaie d'abord de déterminer toi-même quelle méthode est la plus adaptée à chaque problème.

---

# 📊 Données de production

```js
const productions = [
    {
        ligne: "Ligne A",
        produit: "Steak haché",
        quantite: 1250,
        objectif: 1200,
        tauxDefaut: 1.2,
        active: true
    },
    {
        ligne: "Ligne B",
        produit: "Entrecôte",
        quantite: 980,
        objectif: 1000,
        tauxDefaut: 0.8,
        active: true
    },
    {
        ligne: "Ligne C",
        produit: "Saucisse",
        quantite: 1500,
        objectif: 1400,
        tauxDefaut: 2.8,
        active: true
    },
    {
        ligne: "Ligne D",
        produit: "Jambon",
        quantite: 0,
        objectif: 900,
        tauxDefaut: 0,
        active: false
    },
    {
        ligne: "Ligne E",
        produit: "Filet de poulet",
        quantite: 1100,
        objectif: 1100,
        tauxDefaut: 1.5,
        active: true
    }
];
```

---

# 🟢 Mission 1 — Analyser les performances

Une ligne est considérée comme **performante** lorsque :

- elle est active ;
- sa quantité produite est supérieure ou égale à son objectif ;
- son taux de défaut est inférieur ou égal à `2 %`.

Crée une fonction :

```js
estPerformante(production)
```

Elle doit retourner :

```js
true
```

ou :

```js
false
```

Teste-la sur plusieurs éléments du tableau.

---

# 🔎 Mission 2 — Identifier les lignes performantes

À partir de `productions`, crée :

```js
const lignesPerformantes
```

Ce tableau doit contenir uniquement les productions répondant aux critères précédents.

Affiche ensuite le nom des lignes concernées.

### 🎯 Résultat attendu

Les lignes performantes doivent être :

```text
Ligne A
Ligne E
```

---

# ⚠️ Mission 3 — Identifier les lignes nécessitant une intervention

Une ligne nécessite une intervention si :

- elle est inactive ;
- ou sa production est inférieure à son objectif ;
- ou son taux de défaut est supérieur à `2 %`.

Crée :

```js
const lignesEnAlerte
```

Utilise ta fonction métier lorsque cela est pertinent.

### Résultat attendu

```text
Ligne B
Ligne C
Ligne D
```

---

# 📈 Mission 4 — Calculer les écarts de production

Pour chaque ligne, calcule son écart par rapport à l'objectif :

```text
écart = quantité produite - objectif
```

Crée un nouveau tableau contenant :

```js
[
    {
        ligne: "Ligne A",
        ecart: 50
    },
    ...
]
```

### Contrainte

Utilise `map()`.

Tu ne dois pas modifier le tableau `productions` original.

---

# 📊 Mission 5 — Calculer les statistiques globales

Calcule :

- la quantité totale produite ;
- la quantité totale prévue ;
- le nombre de lignes actives ;
- le nombre de lignes performantes ;
- le nombre de lignes en alerte.

Tu dois obtenir un objet de ce type :

```js
{
    productionTotale: ...,
    objectifTotal: ...,
    lignesActives: ...,
    lignesPerformantes: ...,
    lignesEnAlerte: ...
}
```

### 💡 Conseil

Tu peux utiliser plusieurs méthodes différentes.

Il n'est pas obligatoire de tout faire avec `forEach()`.

Réfléchis à la méthode la plus adaptée à chaque calcul.

---

# 🧮 Mission 6 — Calculer le taux de réalisation global

Calcule le taux de réalisation global :

```text
production totale / objectif total × 100
```

Par exemple, si :

```text
production = 4 000
objectif = 4 200
```

alors :

```text
taux = 95,23 %
```

Arrondis le résultat à deux décimales.

### 🎯 Exemple

```js
{
    tauxRealisation: 95.23
}
```

---

# 🔍 Mission 7 — Rechercher une ligne

Crée une fonction :

```js
trouverProduction(productions, nomLigne)
```

Elle doit retourner la production correspondant au nom fourni.

Exemple :

```js
trouverProduction(productions, "Ligne C");
```

doit retourner :

```js
{
    ligne: "Ligne C",
    produit: "Saucisse",
    quantite: 1500,
    objectif: 1400,
    tauxDefaut: 2.8,
    active: true
}
```

Que doit retourner ta fonction si la ligne n'existe pas ?

Teste également :

```js
trouverProduction(productions, "Ligne Z");
```

---

# 🧠 Mission 8 — Tester l'état global de la production

Utilise `every()` pour déterminer si **toutes les lignes actives** respectent un taux de défaut inférieur ou égal à `3 %`.

Crée :

```js
const productionSousControle
```

Le résultat doit être un booléen.

---

# 🔬 Mission 9 — Détecter un problème global

Utilise `some()` pour déterminer s'il existe **au moins une ligne** :

- inactive ;
- ou avec un taux de défaut supérieur à `3 %`.

Crée :

```js
const problemeProduction
```

Le résultat doit être :

```js
true
```

ou :

```js
false
```

---

# 🏆 Mission finale — Générer un rapport complet

Tu dois maintenant créer une fonction :

```js
genererRapportProduction(productions)
```

Elle doit retourner un objet contenant les informations principales :

```js
{
    productionTotale: ...,
    objectifTotal: ...,
    tauxRealisation: ...,
    lignesActives: ...,
    lignesPerformantes: ...,
    lignesEnAlerte: ...,
    productionSousControle: ...,
    problemeProduction: ...
}
```

### Exemple d'utilisation

```js
const rapport = genererRapportProduction(productions);

console.log(rapport);
```

Le résultat doit être exploitable directement par une autre partie de l'application.

---

# ⭐ Bonus — Tableau de bord

Crée une fonction :

```js
genererTableauDeBord(productions)
```

Elle doit retourner un tableau contenant uniquement les informations utiles à l'affichage :

```js
[
    {
        ligne: "Ligne A",
        produit: "Steak haché",
        performance: "OK"
    },
    {
        ligne: "Ligne B",
        produit: "Entrecôte",
        performance: "ALERTE"
    }
]
```

### Contraintes

- utiliser une fonction métier pour déterminer le statut ;
- utiliser `map()` pour produire le nouveau tableau ;
- ne pas modifier `productions`.

---

# 🚀 Défi supplémentaire

Sans modifier les données initiales, ajoute une fonction :

```js
trouverMeilleureLigne(productions)
```

Elle doit retourner la ligne ayant le **meilleur taux de réalisation par rapport à son objectif**.

Formule :

```text
taux de réalisation =
quantité produite / objectif × 100
```

### Attention

La ligne inactive ne doit pas être retenue.

---

# 🧠 Questions de réflexion

À la fin de l'exercice, sois capable d'expliquer :

### 1. Pourquoi utiliser `filter()` plutôt que `map()` pour trouver les lignes en alerte ?

### 2. Pourquoi utiliser `map()` pour construire le tableau des écarts ?

### 3. Dans quel cas `find()` est-il plus adapté que `filter()` ?

### 4. Quelle différence fais-tu entre :

```js
some()
```

et :

```js
every()
```

### 5. Pourquoi est-il intéressant d'avoir une fonction :

```js
estPerformante(production)
```

plutôt que de répéter la condition dans plusieurs endroits du programme ?

---

# ✅ Concepts travaillés

- [x] Variables et constantes
- [x] Tableaux
- [x] Objets
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
- [x] Composition de traitements
- [x] Logique métier
- [x] Raisonnement algorithmique