# 🛸 Rick & Morty Explorer

Tu vas construire une application qui affiche les personnages de Rick & Morty
en les fetchant depuis une API externe, et qui permet de les filtrer par statut.

**API utilisée :** `https://rickandmortyapi.com/api/character`

---

## Étape 1 — Afficher les personnages au chargement

Dans `Home.js` :

1. Crée un état `characters` initialisé à un tableau vide `[]`
2. Importe et utilise `useEffect` pour lancer un `fetch` vers l'API **au chargement de la page**
3. Une fois les données reçues, affiche-les dans la console avec `console.log` pour observer la structure avant de continuer
4. Stocke les personnages dans ton état `characters`
5. Boucle sur `characters` pour afficher un composant `<CharacterCard />` par personnage

> ⚠️ Les personnages ne sont pas directement dans `data` — ils sont dans `data.results`.

Dans `CharacterCard.js` :

Affiche les informations suivantes reçues en props :
- L'image du personnage
- Son nom
- Son espèce (`species`)
- Son statut (`status`) : Alive, Dead, ou unknown

---

## Étape 2 — Filtrer par statut

Dans `Home.js` :

1. Crée un état `status` initialisé à `''` (chaîne vide = pas de filtre)
2. Ajoute un menu déroulant `<select>` avec les options suivantes :
   - Tous (valeur `''`)
   - Alive
   - Dead
   - unknown
3. Quand l'utilisateur change le filtre, mets à jour l'état `status`
4. Adapte ton `useEffect` pour qu'il se redéclenche quand `status` change :
   - Si `status` est vide → fetch tous les personnages
   - Si `status` a une valeur → fetch avec le filtre : `?status=Alive`

> 💡 Un seul `useEffect` peut gérer les deux cas.
> Réfléchis à ce que tu dois mettre dans le tableau de dépendances pour que le `useEffect` se redéclenche au bon moment.

**URL sans filtre :** `https://rickandmortyapi.com/api/character`
**URL avec filtre :** `https://rickandmortyapi.com/api/character?status=Alive`
