🤖 Exercice JavaScript — Gestion d'une liste de tâches avec une IA comme pair de programmation

Profil : Thomas — Débutant JavaScript
Contexte : initiation au scripting JavaScript avec une IA comme pair de programmation
Niveau : débutant JavaScript
Durée estimée : 45 à 60 minutes

🎯 Objectif

Tu vas créer un petit script JavaScript permettant de gérer et d'analyser une liste de tâches.

L'objectif est cependant double : travailler les bases de JavaScript tout en découvrant comment utiliser une IA comme pair de programmation.

Tu ne dois donc pas simplement demander à l'IA :

Fais-moi le code.


Tu vas apprendre à :

décrire un problème ;

formuler un prompt clair ;

demander des explications ;

générer progressivement du code ;

comprendre le code proposé ;

tester le résultat ;

identifier les erreurs ;

demander de l'aide pour les corriger ;

améliorer progressivement ton script ;

modifier toi-même le code généré.

L'objectif final est d'être capable de comprendre et d'expliquer le code que l'IA t'a aidé à produire.

Tu vas notamment manipuler :

variables ;

constantes ;

tableaux ;

objets ;

propriétés ;

types de données ;

conditions ;

fonctions ;

forEach() ;

filter() ;

find() ;

map() ;

some() ;

every() ;

length.

📋 Les tâches

Commence avec les données suivantes :

const taches = [
    {
        titre: "Installer Node.js",
        priorite: "haute",
        terminee: true
    },
    {
        titre: "Créer mon premier script",
        priorite: "haute",
        terminee: false
    },
    {
        titre: "Comprendre les tableaux",
        priorite: "moyenne",
        terminee: false
    },
    {
        titre: "Tester mon script avec une IA",
        priorite: "basse",
        terminee: true
    }
];

🤖 Mission 1 — Faire connaissance avec l'IA

Avant d'écrire du code, demande à l'IA de t'aider à comprendre les données.

Utilise un prompt similaire à :

Tu es mon pair de programmation JavaScript.

Je suis débutant en JavaScript.

Explique-moi simplement la structure de ce tableau d'objets.
Je veux comprendre les notions utilisées avant d'écrire du code.

Ne me donne pas de solution pour l'instant.


Observe sa réponse.

Questions

Sois capable d'expliquer :

qu'est-ce qu'un tableau ?

qu'est-ce qu'un objet ?

que représente titre ?

que représente priorite ?

que représente terminee ?

quel est le type de terminee ?

🟢 Mission 2 — Afficher les tâches

Affiche pour chaque tâche :

Installer Node.js - haute - terminée
Créer mon premier script - haute - à faire
Comprendre les tableaux - moyenne - à faire
Tester mon script avec une IA - basse - terminée


Utilise forEach().

💡 Utilisation de l'IA

Ne demande pas directement la solution.

Demande plutôt :

Je dois parcourir un tableau d'objets JavaScript
et afficher certaines propriétés de chaque objet.

Je suis débutant.

Quelle méthode JavaScript devrais-je utiliser ?
Explique-moi pourquoi avant de me montrer du code.


Identifie la méthode proposée.

Puis demande à l'IA de t'expliquer un exemple adapté à ton tableau.

🎯 Objectif

Comprendre ce que fait :

taches.forEach(...)


et ne pas simplement copier le code généré.

🚨 Mission 3 — Afficher uniquement les tâches à faire

Tu souhaites maintenant afficher uniquement les tâches qui ne sont pas terminées.

Résultat attendu :

À faire : Créer mon premier script
À faire : Comprendre les tableaux


Utilise filter().

💡 Utilisation de l'IA

Demande :

Je veux récupérer uniquement les objets d'un tableau
dont la propriété terminee vaut false.

Quelle méthode JavaScript dois-je utiliser ?
Explique-moi pourquoi et quelle est la différence
avec forEach().


Identifie :

filter()


Puis utilise cette méthode pour construire ton résultat.

🧩 Mission 4 — Créer une fonction de recherche

Imagine qu'un utilisateur souhaite rechercher une tâche précise.

Crée :

trouverTache(taches, titre)


La fonction doit permettre de rechercher une tâche à partir de son titre.

Par exemple :

trouverTache(taches, "Créer mon premier script");


doit retourner l'objet correspondant.

Teste également :

trouverTache(taches, "Apprendre Python");


Observe le résultat.

💡 Utilisation de l'IA

Demande :

Je veux rechercher un seul objet dans un tableau JavaScript
à partir de la valeur d'une de ses propriétés.

Quelle méthode dois-je utiliser ?

Explique-moi également la différence entre
filter() et cette méthode.


Tu devrais découvrir :

find()

📊 Mission 5 — Construire les statistiques

Construis un objet contenant :

{
    total: ...,
    terminees: ...,
    aFaire: ...
}

Résultat attendu
{
    total: 4,
    terminees: 2,
    aFaire: 2
}


Tu peux utiliser :

length ;

filter() ;

plusieurs méthodes combinées.

💡 Utilisation de l'IA

Commence par chercher toi-même une solution.

Si tu bloques, demande :

Je dois compter le nombre total d'éléments
dans un tableau JavaScript.

Quelle propriété puis-je utiliser ?
Explique-moi simplement son fonctionnement.


Puis :

Je veux maintenant compter uniquement
les objets dont terminee vaut true.

Quelle approche me conseilles-tu ?
Ne me donne pas immédiatement la solution complète.

🏷️ Mission 6 — Transformer les données

Imagine qu'une future interface souhaite afficher uniquement :

le titre ;

la priorité ;

l'état.

Crée :

const tableauDeBord


Le résultat doit ressembler à :

[
    {
        titre: "Installer Node.js",
        priorite: "haute",
        etat: "terminée"
    },
    {
        titre: "Créer mon premier script",
        priorite: "haute",
        etat: "à faire"
    },
    ...
]


Utilise map().

💡 Utilisation de l'IA

Demande :

Je veux transformer chaque objet d'un tableau
en un nouvel objet contenant uniquement certaines informations.

Quelle méthode JavaScript dois-je utiliser ?

Explique-moi le principe avant de me donner du code.


Puis essaie d'écrire toi-même la première version.

Compare ensuite ta solution avec celle proposée par l'IA.

🎯 Objectif

L'IA devient progressivement un outil de comparaison et de feedback, et pas uniquement un générateur de code.

🧪 Mission 7 — Introduire volontairement une erreur

Modifie volontairement ton code afin de provoquer une erreur.

Par exemple, utilise une variable qui n'existe pas :

console.log(tache.titre);


alors que la variable disponible possède un autre nom.

Exécute ton programme.

Observe le message d'erreur.

🤖 Demander de l'aide à l'IA

Copie ton code et le message d'erreur.

Demande :

Voici mon code :

[ton code]

Voici l'erreur obtenue :

[message d'erreur]

Je suis débutant en JavaScript.

Aide-moi à identifier l'origine du problème.

Ne corrige pas immédiatement mon code.
Explique-moi d'abord ce qui ne va pas
et indique-moi où chercher.

🎯 Objectif

Apprendre à utiliser l'IA comme outil de diagnostic.

🛠️ Mission 8 — Créer une fonction de rapport

Crée maintenant :

genererRapport(taches)


La fonction doit retourner :

{
    total: 4,
    terminees: 2,
    aFaire: 2,
    prioriteHaute: 2
}

Contraintes

La fonction doit :

recevoir le tableau taches en paramètre ;

calculer les statistiques ;

retourner un objet ;

ne pas afficher directement le résultat avec console.log().

💡 Utilisation de l'IA

Commence par demander :

Je dois créer une fonction JavaScript
qui reçoit un tableau de tâches
et retourne plusieurs statistiques.

Je suis débutant.

Aide-moi à concevoir cette fonction étape par étape.
Ne me donne pas immédiatement le code final.


Construis ensuite progressivement ta fonction.

🔍 Mission 9 — Vérifier le contenu du tableau

Utilise some() pour déterminer s'il existe au moins une tâche avec une priorité :

haute


Stocke le résultat dans :

const auMoinsUnePrioriteHaute


Le résultat doit être un booléen.

Avec les données fournies :

true

💡 Question

Demande à l'IA :

Je veux savoir si au moins un élément d'un tableau
respecte une condition.

Quelle méthode JavaScript dois-je utiliser ?
Explique-moi son fonctionnement simplement.

✅ Mission 10 — Vérifier si toutes les tâches sont terminées

Utilise every() pour vérifier si toutes les tâches sont terminées.

Stocke le résultat dans :

const toutesTerminees


Avec les données fournies :

false

💡 Question

Demande à l'IA :

Quelle est la différence entre some() et every() ?

Donne-moi un exemple simple avec mon tableau de tâches.

🏆 Mission finale — Générer un rapport complet

Regroupe maintenant ton travail dans une fonction :

genererRapportTaches(taches)


Elle doit retourner :

{
    total: 4,
    terminees: 2,
    aFaire: 2,
    prioriteHaute: 2,
    toutesTerminees: false,
    auMoinsUnePrioriteHaute: true
}


Exemple :

const rapport = genererRapportTaches(taches);

console.log(rapport);


L'objectif est d'obtenir un objet unique contenant toutes les informations importantes sur les tâches.

🤖 Consigne IA

Avant de demander du code à l'IA, explique-lui ton problème.

Ton prompt doit contenir :

ton niveau ;

le contexte ;

l'objectif ;

les données disponibles ;

les contraintes ;

le résultat attendu.

L'IA doit t'aider à construire la solution étape par étape.

⭐ Bonus — Ajouter une nouvelle tâche

Crée :

ajouterTache(taches, titre, priorite)


La fonction doit ajouter une nouvelle tâche au tableau.

Exemple :

ajouterTache(
    taches,
    "Découvrir les fonctions JavaScript",
    "moyenne"
);


La nouvelle tâche doit avoir :

terminee: false

💡 Utilisation de l'IA

Demande :

Donne-moi plusieurs façons d'ajouter un objet
dans un tableau JavaScript.

Je suis débutant.

Explique-moi les différences entre les solutions
et indique-moi laquelle serait la plus simple à comprendre.


Choisis ensuite toi-même la solution.

🚀 Bonus 2 — Trouver la tâche prioritaire

Crée :

trouverTachePrioritaire(taches)


La fonction doit retourner la première tâche dont la priorité est :

haute


Résultat attendu :

Installer Node.js

🎯 Objectif

Réutiliser find() dans un nouveau contexte sans demander directement la solution à l'IA.

🧠 Questions de réflexion

À la fin de l'exercice, sois capable d'expliquer :

1. Pourquoi utiliser filter() pour récupérer les tâches à faire ?
2. Quelle différence entre :
filter()


et :

find()

3. Pourquoi map() est-il adapté à la création de tableauDeBord ?
4. Quelle différence entre :
some()


et :

every()

5. Pourquoi créer une fonction comme :
genererRapportTaches()


plutôt que de répéter le même code ?

6. Quelle différence entre demander à une IA :
Fais-moi le code.


et :

Aide-moi à comprendre comment résoudre ce problème.

7. Pourquoi est-il important de comprendre un code généré par une IA avant de l'utiliser ?
8. Quelles informations dois-tu fournir à une IA pour qu'elle puisse efficacement t'aider à résoudre un problème ?
🎯 Défi supplémentaire — Le prompt parfait

Imagine que tu dois demander à une IA de t'aider à créer une nouvelle fonctionnalité JavaScript.

Écris toi-même un prompt contenant :

ton niveau ;

le contexte ;

l'objectif ;

les données disponibles ;

les contraintes ;

le résultat attendu ;

ce que tu attends de l'IA.

Ton prompt doit suivre une structure similaire à :

Je suis débutant en JavaScript.

Contexte :
...

Objectif :
...

Données disponibles :
...

Contraintes :
...

Résultat attendu :
...

Je veux que tu m'aides étape par étape.
Ne me donne pas directement toute la solution.
Explique chaque notion JavaScript utilisée.

🏆 Objectif

Être capable de transformer un problème vague en demande exploitable par une IA.

🎓 Défi ultime — Sans demander la solution

Reprends la fonction :

genererRapportTaches(taches)


et imagine que ton code ne fonctionne pas.

Tu dois résoudre le problème en utilisant uniquement l'IA comme pair de programmation.

Tu dois :

décrire le problème ;

fournir ton code ;

fournir le résultat obtenu ;

fournir le résultat attendu ;

demander à l'IA de t'aider à identifier le problème ;

comprendre l'explication ;

corriger toi-même le code ;

tester à nouveau.

🚫 Interdiction

Ne demande pas :

Corrige mon code et donne-moi la solution.


Essaie plutôt :

Je suis débutant en JavaScript.

Voici mon objectif :
...

Voici mon code :
...

Voici le résultat obtenu :
...

Voici le résultat attendu :
...

Aide-moi à identifier mon erreur.
Ne me donne pas directement la solution.
Commence par m'expliquer où se situe probablement le problème
et aide-moi à le corriger étape par étape.

✅ Concepts JavaScript travaillés

 Variables

 Constantes

 Tableaux

 Objets

 Propriétés

 Types de données

 Conditions

 Opérateurs logiques

 Fonctions personnalisées

 Paramètres

 return

 forEach()

 filter()

 find()

 map()

 some()

 every()

 length

 Transformation de données

 Analyse de données

 Débogage

 Raisonnement algorithmique

🤖 Compétences IA travaillées

 Formuler un prompt

 Donner du contexte à l'IA

 Décrire précisément un problème

 Demander une explication avant une solution

 Générer progressivement du code

 Faire expliquer du code généré

 Utiliser l'IA pour diagnostiquer une erreur

 Fournir un message d'erreur à l'IA

 Comparer sa solution avec celle de l'IA

 Demander des pistes plutôt qu'une réponse complète

 Tester le code généré

 Vérifier le résultat

 Utiliser l'IA comme pair de programmation

 Améliorer progressivement un prompt

 Vérifier sa compréhension du code généré

🎯 Objectif pédagogique final

À la fin de l'exercice, tu ne dois pas seulement être capable de dire :

« L'IA m'a donné le code. »


Tu dois être capable de dire :

« J'ai décrit le problème, j'ai utilisé l'IA pour m'aider à raisonner,
j'ai testé le code, j'ai corrigé mes erreurs et je comprends
ce que fait mon programme. »