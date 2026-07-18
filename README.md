# Maloba — Dataset Français ↔ Lingala

Un dataset ouvert de phrases français ↔ lingala, construit à partir de transcriptions manuelles de vidéos YouTube, avec une attention particulière portée au lingala parlé à **Brazzaville et Pointe-Noire** (Congo-Brazzaville), une variante sous-représentée dans les ressources NLP existantes.

## Objectif

La plupart des ressources open-source disponibles pour le lingala (Hugging Face, Masakhane) sont construites autour du lingala de Kinshasa, ou proviennent de textes journalistiques/religieux qui ne reflètent pas la langue parlée au quotidien. **Maloba** vise à combler ce manque en constituant un *Golden Dataset* : chaque paire de phrases est transcrite et validée manuellement, avec le contexte d'usage (courant, familier, soutenu, argot...).

Ce dataset est pensé comme un bien commun pour la communauté de développeurs et chercheurs congolais et africains : traduction automatique, reconnaissance vocale (Speech-to-Text), synthèse vocale (Text-to-Speech).

## Contenu du dataset

Chaque ligne correspond à une phrase extraite d'une vidéo, avec les colonnes suivantes :

| Colonne | Description |
|---|---|
| `ID` | Identifiant unique de la phrase (ex: `MALOBA-001`) |
| `Français` | Phrase source en français |
| `Lingala` | Traduction telle qu'entendue dans la vidéo (peut inclure des variantes) |
| `Lien Source` | URL de la vidéo YouTube d'origine |
| `Horodatage` | Plage de temps où la phrase est prononcée, format `MM:SS - MM:SS` |
| `Contexte / Nuance` | Tags de registre (`[Courant]`, `[Familier]`, `[Soutenu]`, `[Argot]`, `[Emprunt Français]`, `[Emprunt Portugais]`, `[Grammaire]`...) et notes explicatives |

## État d'avancement

- **564 phrases** transcrites à ce jour
- **32 vidéos sources** différentes
- Couverture actuelle : salutations, vie quotidienne, nombres, anatomie, famille, couleurs, expressions familières/argot, vocabulaire automobile, santé, insectes

*(Mets à jour ces chiffres à chaque export important.)*

## Structure du dépôt

```
maloba-lingala-dataset/
├── data/
│   ├── raw/      # Exports bruts depuis Google Sheets, non modifiés
│   └── clean/    # Fichiers CSV nettoyés (workflow KNIME), prêts à l'emploi
├── docs/         # Notes de méthode, conventions de tags, guide de transcription
├── LICENSE
└── README.md
```

## Comment contribuer

Ce projet est encore en phase de collecte. Les contributions sont les bienvenues, en particulier :
- Transcription de nouvelles vidéos (YouTube, TikTok) en lingala de Brazzaville/Pointe-Noire
- Relecture et correction orthographique des entrées existantes
- Ajout d'exemples de kituba (encore totalement absent)

Pour proposer une modification, ouvre une *issue* ou une *pull request* sur ce dépôt.

## Licence

Ce dataset est publié sous licence **[Creative Commons Attribution 4.0 International (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/)**. Vous pouvez l'utiliser, le modifier et le redistribuer, y compris à des fins commerciales, à condition de créditer le projet Maloba.

## Sources

Les phrases sont issues de vidéos publiques créditées individuellement dans la colonne `Lien Source` de chaque ligne. Seuls les liens vers les vidéos sont conservés — aucun contenu vidéo n'est hébergé dans ce dépôt.
