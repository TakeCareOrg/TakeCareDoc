---
sidebar_position: 8
---

# UI

Dans le projet **TakeCareAI**, les composants d'interface utilisateur (UI) génériques sont regroupés dans un dossier dédié. Ces composants, comme les boutons ou les champs de formulaire, sont conçus pour être réutilisables et stylisés de manière cohérente à travers toute l'application.

## Structure des Dossiers

Les composants génériques sont organisés dans le dossier `src/ui`. Chaque fichier correspond à un type de composant, comme les boutons ou les champs d'entrée.

```plaintext
src
└── ui
    ├── buttons.tsx      // Composants pour les boutons
    ├── inputField.tsx   // Composants pour les champs d'entrée
    └── [autres fichiers pour les composants génériques]
```

### Exemple de Fichier : buttons.tsx

Le fichier buttons.tsx contient les définitions des boutons utilisés dans l’application. Ces boutons incluent des variantes comme des boutons primaires, secondaires ou des boutons désactivés. Ils sont stylisés pour respecter les directives de design globales.

## Fonctionnement et Utilisation

Les composants du dossier src/ui sont conçus pour être modulaires et paramétrables. Par exemple, un bouton peut accepter des props comme onPress, disabled, ou encore une prop de style personnalisée.

### Exemple d’Utilisation

Voici un exemple d’utilisation d’un bouton défini dans le fichier buttons.tsx :

```tsx
// src/components/ExampleComponent.tsx
import React from "react";
import { View } from "react-native";
import { PrimaryButton } from "../ui/buttons";

const ExampleComponent = () => {
  const handlePress = () => {
    console.log("Bouton cliqué !");
  };

  return (
    <View>
      <PrimaryButton label="Cliquez ici" onPress={handlePress} />
    </View>
  );
};

export default ExampleComponent;
```

## Contenu Typique d’un Fichier UI

Un fichier comme buttons.tsx inclut généralement :
• Plusieurs variantes de composants : Par exemple, un bouton primaire, un bouton secondaire, et un bouton désactivé.
• Des props configurables : Comme label, onPress, ou disabled.
• Une gestion des styles : Les styles sont souvent centralisés ou dérivés d’un système de design.

```tsx
import React from "react";
import { TouchableOpacity, Text, StyleSheet } from "react-native";

export const PrimaryButton = ({ label, onPress, disabled }) => (
  <TouchableOpacity
    style={[styles.button, disabled && styles.disabled]}
    onPress={onPress}
    disabled={disabled}
  >
    <Text style={styles.label}>{label}</Text>
  </TouchableOpacity>
);

const styles = StyleSheet.create({
  button: {
    backgroundColor: "#007BFF",
    padding: 12,
    borderRadius: 8,
    alignItems: "center",
  },
  disabled: {
    backgroundColor: "#A0A0A0",
  },
  label: {
    color: "#FFF",
    fontSize: 16,
  },
});
```

## Objectifs et Avantages

    1.	Réutilisabilité : Les composants génériques peuvent être utilisés dans toute l’application, réduisant ainsi la duplication de code.
    2.	Cohérence visuelle : Les styles centralisés garantissent une apparence uniforme à travers toutes les pages et fonctionnalités.
    3.	Facilité de maintenance : En modifiant un composant générique, toutes ses occurrences dans l’application sont mises à jour automatiquement.
    4.	Flexibilité : Les composants sont configurables via des props, ce qui permet de les adapter à différents contextes.

## Ajouter un Nouveau Composant UI

Pour ajouter un nouveau composant générique : 1. Créez un fichier sous src/ui/[nom-du-composant].tsx. 2. Définissez la logique et les styles du composant. 3. Exportez le composant pour qu’il puisse être utilisé dans toute l’application.

### Exemple : Ajouter un Champ de Saisie InputField

    1.	Créez le fichier src/ui/inputField.tsx.
    2.	Définissez le composant avec des props comme placeholder et onChangeText.
    3.	Stylisez le composant en respectant le design de l’application.

```tsx
import React from "react";
import { TextInput, StyleSheet } from "react-native";

export const InputField = ({ placeholder, onChangeText }) => (
  <TextInput
    style={styles.input}
    placeholder={placeholder}
    onChangeText={onChangeText}
  />
);

const styles = StyleSheet.create({
  input: {
    borderColor: "#CCC",
    borderWidth: 1,
    borderRadius: 8,
    padding: 12,
    fontSize: 16,
  },
});
```

## Conclusion

En centralisant les composants UI dans un dossier dédié, le projet TakeCareAI bénéficie d’une structure claire et maintenable. Cette organisation garantit une expérience utilisateur cohérente et simplifie le développement de nouvelles fonctionnalités.
