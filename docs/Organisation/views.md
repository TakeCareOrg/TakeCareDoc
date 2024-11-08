---
sidebar_position: 1
---

# Views

Dans le projet **TakeCareAI**, chaque page principale est structurée dans un répertoire spécifique et suit une organisation bien définie pour faciliter la personnalisation et la maintenance.

## Structure des Dossiers

Pour chaque **View** (ou écran), vous trouverez la structure suivante dans le dossier `src/Views` :

```plaintext
src
└── Views
    └── NameView
        ├── NameScreen.tsx
        └── Components
```

- **NomDeLaView** : Représente le nom de la page ou de l'écran (par exemple, `Home` pour la page d'accueil).
- **NomScreen.tsx** : Le fichier principal de l'écran (par exemple, `HomeScreen.tsx`). Ce fichier doit **uniquement** contenir les appels aux composants de la page.
- **Components** : Un dossier contenant les différents composants utilisés dans cet écran spécifique.

### Exemple de Structure : Home

Pour la page d'accueil, la structure serait la suivante :

```plaintext
src
└── Views
    └── Home
        ├── HomeScreen.tsx
        └── Components
            ├── Header.tsx
            ├── Footer.tsx
            └── Content.tsx
```

Dans cet exemple :

- `HomeScreen.tsx` ne contient que les appels aux composants `Header`, `Footer`, et `Content`, sans logique de traitement ou de style supplémentaire.
- Chaque composant dans le dossier `Components` est indépendant, ce qui permet de modifier ou de remplacer facilement chaque section de l'écran.

## Bonnes pratiques pour organiser un écran

1.  **Simplicité du fichier Screen** : Dans `NomScreen.tsx`, n'incluez que les appels aux composants et les props nécessaires pour construire l'interface. Cela permet de rendre ce fichier léger et facile à lire.

    ```typescript
    // src/Views/Home/HomeScreen.tsx
    import React from "react";
    import Header from "./Components/Header";
    import Content from "./Components/Content";
    import Footer from "./Components/Footer";

    const HomeScreen = () => {
      return (
        <>
          <Header />
          <Content />
          <Footer />
        </>
      );
    };

    export default HomeScreen;
    ```

2.  **Indépendance des composants** : Les composants dans le dossier Components doivent être autonomes, en gérant leurs propres styles et éventuelles sous-composantes si nécessaire. Cela permet de les réutiliser dans d’autres écrans sans duplication de code.

3.  **Facilité de personnalisation** : Cette organisation en modules facilite la personnalisation de chaque section de la page. Par exemple, pour modifier l’en-tête de la page d’accueil, il suffit d’éditer le fichier `Header.tsx` dans src/Views/Home/Components/Header.tsx sans avoir à toucher le reste de l’écran.

## Créer une nouvelle View

Pour ajouter une nouvelle page dans l’application :

    1.	Créez un dossier sous src/Views portant le nom de la page souhaitée.
    2.	Ajoutez un fichier `NomScreen.tsx` dans ce dossier pour définir la structure de l’écran.
    3.	Créez un dossier Components pour y placer les différents composants spécifiques à cette page.
