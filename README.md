# Walid Voyages — GPS Tracker Prototype

Contenu:
- `index.html` : dashboard agence avec carte et liste des appareils
- `tracker.html` : page mobile à ouvrir sur le téléphone du guide/accompagnateur
- `config.js` : configuration Firebase
- `style.css` : design

## Installation rapide
1. Créez un projet Firebase: https://console.firebase.google.com/
2. Ajoutez une application Web.
3. Activez **Realtime Database**.
4. Collez la configuration Firebase dans `config.js`.
5. Pour un test, utilisez ces règles Realtime Database (prototype uniquement):

```json
{
  "rules": {
    "devices": {".read": true, ".write": true},
    "history": {".read": true, ".write": true}
  }
}
```

6. Hébergez le dossier sur GitHub Pages / Netlify / Firebase Hosting.
7. Ouvrez `index.html` à l'agence.
8. Cliquez **Ajouter**. Le dashboard génère un lien `tracker.html?id=...`.
9. Ouvrez ce lien sur le téléphone de l'accompagnateur.
10. L'accompagnateur appuie sur **Autoriser et démarrer le GPS**.

## Important
- HTTPS est requis pour la géolocalisation sur la plupart des navigateurs (GitHub Pages fournit HTTPS).
- Le navigateur mobile peut limiter le suivi quand l'écran est éteint ou l'application est fermée. Pour du vrai suivi 24/24 en arrière-plan, il faut une application Android/iOS dédiée.
- Les règles Firebase ci-dessus sont uniquement pour un prototype. En production, ajoutez Firebase Authentication et des règles privées.
- Utilisez ce système seulement avec l'accord explicite de la personne qui partage sa position.
