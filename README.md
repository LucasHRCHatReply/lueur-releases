# Lueur pour macOS

Lueur pilote le rétroéclairage du clavier du MacBook. Depuis que la touche de luminosité du clavier a disparu, et que
la nuit le clavier s'éteint, elle rend la main : un curseur dans la barre des menus (petite icône de clavier lumineux),
des raccourcis, un délai d'extinction jusqu'à « jamais », et « jamais éteint la nuit » sur horaire.
Aucun compte, aucune télémétrie.

- **Raccourcis** : ⌃⌥L allume ou éteint · ⌃⌥→ et ⌃⌥← plus ou moins de lumière.
- **Extinction** : délai réglable, éteint en plein écran ou écran verrouillé, reprise de la main si macOS rétablit son réglage.
- **Nuit** : de 22 h à 7 h par défaut, le clavier ne s'éteint jamais seul.
- **Lumière** : suit la lumière de la pièce, avec un seuil.
- **Saisie** : réveil à la frappe (clavier intégré seulement), indicateur Verr. Maj., saisie sécurisée.

Lueur s'appuie sur des fonctions non documentées de macOS : une mise à jour du système peut les changer. Lueur le détecte
et cesse de toucher au clavier plutôt que de mal faire.

Ce dépôt ne contient que les versions à installer. Le code source n'est pas public.

## Ce qu'il faut

- un Mac à puce Apple (M1 ou plus récent) avec un clavier rétroéclairé ;
- macOS 14 ou plus.
Aucun compte GitHub, aucun outil à installer, aucun mot de passe administrateur.

## Installer

Dans Terminal (Cmd + Espace, « Terminal »), une seule commande, qui installe aussi les mises à jour :

```
curl -fsSL https://raw.githubusercontent.com/LucasHRCHatReply/lueur-releases/main/installer.sh | zsh
```

Le script télécharge la dernière version, vérifie l'empreinte SHA-256 du zip, l'identifiant de l'app et sa signature
(équipe Apple `JT9FY7PP7K`, `codesign --verify --deep --strict`), copie `Lueur.app` dans `~/Applications`, puis ouvre
l'app. Il garde les réglages.

Une autorisation facultative : pour le réveil à la frappe, Réglages Système › Confidentialité et sécurité ›
Surveillance de la saisie › Lueur. Lueur la demande elle-même, dans son écran de premier lancement.

Autre voie : télécharger `Lueur.dmg` dans les [Releases](../../releases/latest), l'ouvrir, glisser Lueur sur
Applications. Le disque est signé, non notarisé : au premier lancement, clic droit sur l'app › Ouvrir.
