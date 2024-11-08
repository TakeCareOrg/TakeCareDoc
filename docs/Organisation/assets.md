---
sidebar_position: 2
---

# Assets

Dans le projet **TakeCareAI**, les ressources (assets) sont organisées en trois dossiers principaux pour faciliter la gestion des polices, des icônes et des images.

## Structure des Dossiers

La structure des dossiers dans `src/assets` est la suivante :

```plaintext
src
└── assets
        ├── fonts
        ├── icons
        └── images
```

### 1. Dossier `fonts`

Ce dossier contient les polices utilisées dans l'application. Les polices sont organisées par famille de polices.

Exemple de fichier dans `fonts` :

- `Inter` :
  - `Inter Medium.ttf` : Police pour le texte avec une épaisseur moyenne.

### 2. Dossier `icons`

Ce dossier contient les icônes personnalisées, souvent sous forme de composants React.

Exemple de fichier dans `icons` :

- `AddIcon.tsx` :

  ```typescript
  import React from "react";
  import { Svg, Path } from "react-native-svg";
  import { Colors } from "../../styles/Colors";
  import { IconType } from "../../types/IconType";

  export const AddIcon: React.FC<IconType> = ({
    color = Colors().main.primary,
    height = 20,
    width = 20,
  }) => (
    <Svg width={width} height={height} viewBox="0 0 30 30" fill="none">
      <Path
        d="M15 5L15 25"
        stroke={color}
        strokeWidth="2.5"
        strokeLinecap="round"
      />
      <Path
        d="M5 15H25"
        stroke={color}
        strokeWidth="2.5"
        strokeLinecap="round"
      />
    </Svg>
  );
  ```

  Dans cet exemple, l’icône AddIcon est un composant React personnalisé qui accepte des props pour la couleur, la hauteur et la largeur, et utilise des chemins SVG pour dessiner l’icône.

### 3. Dossier `images`

Ce dossier contient toutes les images utilisées dans l’application, organisées en fonction des besoins spécifiques du projet.

## Bonnes Pratiques

- Organiser les polices et icônes par famille ou fonction : Chaque police ou icône devrait être placée dans un sous-dossier spécifique pour une meilleure organisation.
- Composants d’icônes réutilisables : Les icônes devraient être créées comme des composants React réutilisables, permettant de les personnaliser via des props pour une meilleure flexibilité.
- Utilisation d’images optimisées : Assurez-vous que les images sont optimisées pour le web pour améliorer les performances de l’application.

En suivant cette structure, la gestion des assets devient plus claire et maintenable, facilitant les modifications et les ajouts futurs.
