---
sidebar_position: 4
---

# Call API

Dans le projet **TakeCareAI**, les appels API sont centralisés dans des fichiers spécifiques pour chaque fonctionnalité, ce qui permet de mieux gérer les connexions avec le backend et de simplifier le débogage.

## Structure des Dossiers

Les appels API sont organisés par fonctionnalité dans le dossier `src/api`. Par exemple, les appels liés à l'authentification se trouvent dans le dossier `auth`, et chaque fichier gère une fonctionnalité spécifique, comme la connexion (signin).

```plaintext
src
└── api
    ├── auth
    │   ├── Signin.tsx
    │   └── [autres fichiers liés à l’authentification]
    └── [autres dossiers pour chaque fonctionnalité]
```

### Exemple de fichier `Signin.tsx` (auth)

Le fichier `Signin.tsx` contient la logique pour l'appel API de connexion avec Axios. Ce fichier permet d'éviter d'inclure les liens directement dans le code et facilite le débogage en isolant les appels API dans des modules distincts.

```typescript
// src/api/auth/Signin.tsx
import axios from "axios";

const API_URL = "https://api.takecareai.com/auth/signin"; // Lien de l'API de connexion

export const signin = async (email: string, password: string) => {
  try {
    const response = await axios.post(API_URL, { email, password });
    return response.data;
  } catch (error) {
    console.error("Erreur lors de la connexion :", error);
    throw error;
  }
};
```

## Objectifs et Avantages de cette Organisation

1. Centralisation des appels API : En plaçant chaque appel dans un fichier séparé, nous évitons la duplication des liens API dans le code. Chaque fonctionnalité a son propre fichier (comme Signin.tsx pour l’authentification), ce qui permet de centraliser la gestion des appels et des erreurs.
2. Sécurité des liens API : En gardant les liens dans un fichier séparé et non dans les composants UI, nous minimisons le risque de fuite de ces informations sensibles dans le code source.
3. Facilité de débogage : Lorsqu’une erreur survient, le débogage est simplifié car chaque appel est isolé dans son propre fichier. Cela permet de mieux comprendre où l’erreur se produit et d’effectuer des tests plus ciblés.
4. Réutilisabilité : Une fois que l’appel API est défini dans un fichier, il peut être facilement réutilisé dans toute l’application, ce qui simplifie la gestion des requêtes.

## Ajouter un Nouveau Call API

Pour ajouter un nouvel appel API dans l’application, procédez comme suit :

1. Créez un fichier sous src/api/[fonctionnalité]/[nom-du-fichier].tsx.
2. Définissez la logique de l’appel API à l’intérieur de ce fichier, en utilisant Axios pour effectuer les requêtes nécessaires.
3. Utilisez ce fichier dans vos composants pour effectuer les appels à l’API.

## Exemple de gestion d’erreur

Le fichier Signin.tsx montre également comment gérer les erreurs lors de l’appel API. Nous utilisons un bloc try-catch pour intercepter les erreurs et les afficher dans la console, ce qui permet une meilleure traçabilité.

## Conclusion

En centralisant les appels API dans des fichiers dédiés, nous rendons le code plus maintenable, sécurisé, et facile à déboguer. Cette approche est essentielle pour assurer une gestion efficace des interactions avec le backend et une meilleure organisation du projet TakeCareAI.
