---
sidebar_position: 3
---

# Types

Dans le projet **TakeCareAI**, le dossier `types` est utilisé pour définir des types TypeScript spécifiques aux différentes fonctionnalités de l'application. Cela permet d'améliorer la lisibilité du code, d'assurer la sécurité des types, et de faciliter le développement en équipe.

## Structure des Dossiers

La structure des types dans `src/types` est organisée par fonctionnalité, ce qui permet de mieux séparer les responsabilités et de retrouver facilement les types associés à chaque domaine de l'application.

```plaintext
src
└── types
        ├── auth.types.ts
        ├── quiz.types.ts
        └── [autres types liés aux fonctionnalités]
```

## L’Utilisation de TypeScript dans un Projet

L’utilisation de TypeScript dans ce projet apporte plusieurs avantages :

1. Sécurité des Types : TypeScript vérifie la cohérence des types à la compilation, réduisant ainsi le risque d’erreurs lors de l’exécution, comme l’assignation de valeurs incorrectes à des variables.
2. Autocomplétion et Documentation : Les types permettent aux éditeurs de code comme VSCode de fournir des suggestions d’autocomplétion, ce qui améliore l’expérience de développement et la productivité.
3. Clarté du Code : Les types rendent le code plus lisible et compréhensible pour les développeurs, notamment lorsqu’il s’agit de comprendre les données attendues dans chaque partie du projet.

## Types de Variables dans les Fichiers de Types

Les variables et types que vous trouverez dans ces fichiers sont généralement définis comme suit :

- Interfaces (interface) : Utilisées pour définir des structures d’objets complexes. Par exemple, User, AuthState, Quiz sont des interfaces qui décrivent des objets avec des propriétés spécifiques.
- Types Primitifs : Des types comme string, number, boolean, etc., sont utilisés pour les valeurs simples.
- Types de tableaux et de listes : Par exemple, string[] pour un tableau de chaînes de caractères, ou Question[] pour une liste de questions.
- Types optionnels : Grâce à l’opérateur ?, certains champs peuvent être optionnels dans une interface, ce qui permet de décrire des objets flexibles.

### 1. Exemple de fichier `auth.types.ts`

Le fichier `auth.types.ts` contient des types relatifs à l'authentification. Par exemple :

```typescript
// src/types/auth.types.ts

export interface User {
  id: string;
  email: string;
  name: string;
}

export interface AuthState {
  user: User | null;
  isAuthenticated: boolean;
  loading: boolean;
}

export interface LoginCredentials {
  email: string;
  password: string;
}
```

Dans cet exemple, nous avons trois types principaux :

- User : Représente les informations d’un utilisateur authentifié, comme l’ID, l’email, et le nom.
- AuthState : Contient l’état de l’authentification, incluant les informations de l’utilisateur, un indicateur de statut d’authentification (isAuthenticated), et un état de chargement (loading).
- LoginCredentials : Décrit les informations nécessaires pour effectuer une tentative de connexion, comme l’email et le mot de passe.

### 2. Exemple de fichier `quiz.types.ts`

Le fichier `quiz.types.ts` contient des types relatifs au quiz. Par exemple :

```typescript
// src/types/quiz.types.ts

export interface Question {
  id: string;
  text: string;
  options: string[];
  correctAnswer: string;
}

export interface Quiz {
  id: string;
  title: string;
  description: string;
  questions: Question[];
}

export interface QuizState {
  currentQuiz: Quiz | null;
  currentQuestionIndex: number;
  isQuizComplete: boolean;
}
```

Dans cet exemple, nous avons les types suivants :

- Question : Représente une question de quiz avec un texte, des options de réponse, et la réponse correcte.
- Quiz : Représente un quiz avec un titre, une description, et une liste de questions.
- QuizState : Contient l’état du quiz en cours, y compris le quiz actuel, l’index de la question actuelle, et un indicateur de fin de quiz (isQuizComplete).

## Conclusion

L’utilisation de TypeScript permet une gestion claire et efficace des types dans le projet. En séparant les types par fonctionnalité (comme l’authentification ou le quiz), nous facilitons la maintenance et la compréhension du code, tout en minimisant les erreurs potentielles liées aux types.
