# 🥩 Exercice JavaScript — Gestion d'un catalogue de produits

> **Profil : Maxime — Bigard**  
> **Contexte : découverte de React dans son poste**  
> **Niveau : bases JavaScript à consolider**  
> **Durée estimée : 35 à 45 minutes**

## 🎯 Objectif

Avant de travailler efficacement avec React, il est important d'être à l'aise avec la manipulation de données en JavaScript.

Dans cet exercice, tu vas travailler sur un catalogue de produits alimentaires.

Tu vas devoir :

- parcourir des données ;
- filtrer des produits ;
- transformer des données ;
- rechercher un élément ;
- effectuer des calculs ;
- créer des fonctions réutilisables ;
- construire un résultat exploitable par une future interface.

> 💡 **Important :** pour cet exercice, aucun HTML ni React n'est nécessaire. Toute l'application sera réalisée dans JavaScript.

---

# 📦 Les données

Commence avec ce tableau :

```js
const produits = [
    {
        nom: "Steak haché",
        categorie: "Boeuf",
        prix: 8.50,
        stock: 25,
        disponible: true
    },
    {
        nom: "Entrecôte",
        categorie: "Boeuf",
        prix: 18.90,
        stock: 8,
        disponible: true
    },
    {
        nom: "Escalope de poulet",
        categorie: "Volaille",
        prix: 11.50,
        stock: 0,
        disponible: false
    },
    {
        nom: "Saucisse",
        categorie: "Porc",
        prix: 7.90,
        stock: 32,
        disponible: true
    },
    {
        nom: "Jambon",
        categorie: "Porc",
        prix: 6.90,
        stock: 4,
        disponible: true
    },
    {
        nom: "Filet de poulet",
        categorie: "Volaille",
        prix: 13.90,
        stock: 12,
        disponible: true
    }
];
```

Chaque produit possède plusieurs propriétés :

| Propriété | Signification |
|---|---|
| `nom` | Nom du produit |
| `categorie` | Catégorie du produit |
| `prix` | Prix |
| `stock` | Quantité disponible |
| `disponible` | Produit disponible ou non |

---

# 🟢 Mission 1 — Afficher le catalogue

Parcours le tableau `produits` et affiche chaque produit sous la forme :

```text
Steak haché - 8.5€
Entrecôte - 18.9€
Escalope de poulet - 11.5€
...
```

### 💡 Indice

Utilise `forEach()` :

```js
produits.forEach((produit) => {
    // Ton code
});
```

Puis accède aux propriétés :

```js
produit.nom
produit.prix
```

---

# 🔎 Mission 2 — Afficher uniquement les produits disponibles

Crée un nouveau tableau :

```js
const produitsDisponibles = ...
```

Il doit contenir uniquement les produits dont :

```js
disponible === true
```

### 💡 Indice

Utilise :

```js
filter()
```

Exemple de structure :

```js
const resultat = produits.filter((produit) => {
    return condition;
});
```

Affiche ensuite le résultat.

---

# 🥩 Mission 3 — Filtrer par catégorie

Crée un tableau contenant uniquement les produits de la catégorie :

```text
Boeuf
```

Le résultat doit contenir :

```text
Steak haché
Entrecôte
```

### 💡 Indice

Tu dois comparer :

```js
produit.categorie
```

avec :

```js
"Boeuf"
```

---

# 💰 Mission 4 — Créer une liste de prix

On souhaite préparer les données pour une future interface React.

Crée un nouveau tableau contenant **uniquement les noms et les prix**.

Le résultat attendu est de cette forme :

```js
[
    {
        nom: "Steak haché",
        prix: 8.50
    },
    {
        nom: "Entrecôte",
        prix: 18.90
    }
    // ...
]
```

### 💡 Indice

Cette fois, `filter()` ne suffit pas.

Tu dois **transformer chaque élément**.

Utilise :

```js
map()
```

Structure :

```js
const resultat = produits.map((produit) => {
    return {
        // nouvelles données
    };
});
```

---

# 🔍 Mission 5 — Rechercher un produit

On souhaite permettre à un utilisateur de rechercher un produit.

Cherche le produit :

```text
Jambon
```

et stocke-le dans :

```js
const produitRecherche
```

### 💡 Indice

Utilise :

```js
find()
```

La condition doit comparer :

```js
produit.nom
```

avec :

```js
"Jambon"
```

Affiche ensuite le produit trouvé.

---

# 📊 Mission 6 — Calculer la valeur du stock

On souhaite connaître la valeur totale du stock.

Pour chaque produit :

```text
valeur = prix × stock
```

Par exemple :

```text
Steak haché
8.50 × 25
= 212.50 €
```

Calcule ensuite la valeur totale de **tous les produits**.

### 💡 Indice

Cette fois, tu dois combiner plusieurs valeurs pour obtenir **une seule valeur finale**.

Utilise :

```js
reduce()
```

Structure :

```js
const total = produits.reduce((total, produit) => {
    return total + ...;
}, 0);
```

---

# ⚠️ Mission 7 — Identifier les produits nécessitant une attention

Un produit nécessite une attention particulière si :

- il n'est plus disponible ;
- **ou** son stock est inférieur ou égal à `5`.

Crée :

```js
const produitsEnAlerte
```

Exemples concernés :

```text
Escalope de poulet
Jambon
```

### 💡 Indice

Utilise `filter()` avec une condition comprenant `||`.

```js
const produitsEnAlerte = produits.filter((produit) => {
    return condition1 || condition2;
});
```

---

# 🧩 Mission 8 — Créer une fonction métier

Tu vas maintenant éviter de mettre cette logique directement dans ton code.

Crée une fonction :

```js
estEnAlerte(produit)
```

Elle doit retourner :

```text
true
```

si le produit est en alerte et :

```text
false
```

sinon.

Exemple :

```js
console.log(estEnAlerte(produits[0]));
```

Résultat :

```text
false
```

Et :

```js
console.log(estEnAlerte(produits[4]));
```

Résultat :

```text
true
```

### 💡 Structure

```js
function estEnAlerte(produit) {

    // Ta condition

}
```

Tu peux ensuite réutiliser cette fonction dans `filter()`.

---

# 🏆 Mission finale — Préparer les données pour une interface

Imagine maintenant que ces données vont être utilisées par un composant React.

Tu dois créer une fonction :

```js
preparerCatalogue(produits)
```

Cette fonction doit retourner un objet contenant :

```js
{
    totalProduits: 6,
    produitsDisponibles: 5,
    produitsEnAlerte: 2,
    valeurStock: ...
}
```

Tu dois donc réutiliser les méthodes et fonctions précédemment découvertes.

### 💡 Tu peux commencer par :

```js
function preparerCatalogue(produits) {

    const produitsDisponibles = produits.filter(...);

    const produitsEnAlerte = produits.filter(...);

    const valeurStock = produits.reduce(...);

    return {
        totalProduits: produits.length,
        produitsDisponibles: produitsDisponibles.length,
        produitsEnAlerte: produitsEnAlerte.length,
        valeurStock: valeurStock
    };
}
```

Puis :

```js
const catalogue = preparerCatalogue(produits);

console.log(catalogue);
```

---

# ⭐ Bonus — Préparer directement les données d'affichage

Pour aller plus loin, crée une fonction :

```js
preparerProduitsDisponibles(produits)
```

Elle doit :

1. conserver uniquement les produits disponibles ;
2. transformer chaque produit ;
3. ne conserver que :
   - `nom`
   - `prix`
   - `categorie`

Le résultat devra ressembler à :

```js
[
    {
        nom: "Steak haché",
        prix: 8.50,
        categorie: "Boeuf"
    },
    // ...
]
```

### 💡 Indice

Tu peux enchaîner plusieurs méthodes :

```js
produits
    .filter(...)
    .map(...);
```

---

# 🧠 Le lien avec React

Dans une application React, les données affichées dans une interface sont souvent issues de tableaux et d'objets.

Par exemple, si React reçoit :

```js
const produitsDisponibles = [...]
```

il pourra ensuite parcourir ces données pour générer l'interface.

L'objectif ici est donc de maîtriser **la préparation des données en JavaScript avant de les afficher dans React**.

Les méthodes `map()`, `filter()`, `reduce()` et `find()` sont particulièrement importantes pour cette logique de traitement des tableaux.

---

# ✅ Concepts travaillés

- [x] Variables
- [x] Constantes
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
- [x] Transformation de données
- [x] Calculs
- [x] Préparation de données pour une interface
- [x] Raisonnement algorithmique