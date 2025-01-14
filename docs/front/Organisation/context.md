---
sidebar_position: 6
---

# Context

Dans le projet **TakeCareAI**, la gestion des états globaux est réalisée à l'aide des **Contextes React**. Cette approche permet de partager des données et des fonctionnalités entre les composants sans avoir à les passer explicitement via les props, ce qui simplifie la structure et améliore la maintenabilité.

## Structure des Dossiers

Les contextes sont organisés dans le dossier `src/contexts`. Chaque fichier de contexte est dédié à une fonctionnalité spécifique, comme l'authentification.

```plaintext
src
└── context
    ├── AuthContext.tsx  // Contexte pour l'authentification
    └── [autres fichiers de contexte]
```

## Exemple de Fichier : AuthContext.tsx

Le fichier AuthContext.tsx centralise la gestion des données et des fonctions liées à l’authentification, comme l’utilisateur connecté, les tokens, et les méthodes de connexion et de déconnexion.

## Configuration et Utilisation

Le fichier AuthContext.tsx contient la configuration complète pour le contexte d’authentification. Il inclut :
• Un fournisseur : Pour encapsuler l’application et rendre les données disponibles globalement.
• Des données partagées : Comme les informations sur l’utilisateur connecté.
• Des fonctions globales : Comme les fonctions de connexion et de déconnexion.

## Exemple d’Utilisation

Dans vos composants, utilisez le hook useContext pour accéder aux données et fonctions fournies par le contexte. Voici un exemple :

```tsx
// src/views/profile/index.tsx
import { useAuth } from "../context/AuthContext";

const Profile = () => {
  const { user } = useAuth();

  return (
    <div>
      <h1>Bienvenue, {user?.name}!</h1>
    </div>
  );
};

export default Profile;
```

## Objectifs et Avantages

    1.	Centralisation des états : Les contextes permettent de regrouper les états globaux et les fonctions associées dans des fichiers dédiés.
    2.	Réduction des props : En utilisant des contextes, il n’est plus nécessaire de passer les données entre les composants via des props, simplifiant ainsi leur structure.
    3.	Réutilisabilité : Les fonctions et données définies dans un contexte peuvent être utilisées dans toute l’application, rendant le code plus modulable.
    4.	Meilleure maintenabilité : Les fichiers de contexte isolent la logique métier, ce qui facilite le débogage et l’évolution du projet.

## Ajouter un Nouveau Contexte

Pour ajouter un nouveau contexte dans l’application :

    1. Créez un fichier sous src/contexts/[NomDuContexte].tsx.
    2. Configurez le fournisseur et définissez les données et fonctions globales nécessaires.
    3. Encapsulez les composants concernés par ce contexte dans votre application, généralement dans le fichier principal App.tsx.

### Exemple de Configuration pour un Contexte “ThemeContext”

    1.	Créez le fichier src/contexts/ThemeContext.tsx.
    2.	Définissez les états et fonctions pour gérer les thèmes clairs et sombres.
    3.	Encapsulez les composants dans le ThemeProvider pour activer le support des thèmes.

## Conclusion

L’utilisation des contextes dans le projet TakeCareAI garantit une gestion efficace des états globaux et améliore la structure du code. Cette approche permet une meilleure modularité, facilite la collaboration entre développeurs, et assure une expérience utilisateur fluide.
