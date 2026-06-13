<div align="center">

# Compétences d'Enseignement · zhijiao-skills

**Boîte à outils IA pour les enseignants bénévoles dans les régions des minorités ethniques de Chine (Xinjiang, Tibet, etc.)**

</div>

<div align="center">

[中文](README_CN.md) | [English](README.md) | **Français**

</div>

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-orange)
![Compatible](https://img.shields.io/badge/compatible-Claude%20Code%20%7C%20IA%20universelle-blue)
![Licence](https://img.shields.io/badge/licence-MIT-green)

</div>

---

## Qu'est-ce que c'est ?

**zhijiao-skills** est un ensemble de compétences IA qui aide les enseignants bénévoles à créer des supports pédagogiques complets en une seule phrase :

- 📊 **Diaporamas HTML interactifs** — un seul fichier, utilisable hors ligne sur n'importe quel appareil
- 📑 **Diaporamas PPTX** — compatibles avec les tableaux blancs et les anciens projecteurs
- 📝 **Plans de cours** (教案) — format Markdown, prêt à imprimer
- 📋 **Banques d'exercices par niveaux** — exercices en classe, devoirs, contrôles de chapitre

**Conçu spécifiquement pour les classes des minorités ethniques :**
- ✅ Polices plus grandes, mise en page plus claire
- ✅ Rythme d'enseignement plus lent — un concept clé par page
- ✅ Effets d'animation pour les points de connaissance importants
- ✅ Diaporamas entièrement hors ligne — aucune connexion Internet requise
- ✅ Annotations optionnelles en langues minoritaires (ouïghour, tibétain, kazakh, etc.)
- ✅ Exercices à trois niveaux de difficulté avec version simplifiée pour les élèves en difficulté

---

## Installation

### Prérequis

Vous avez besoin de **Claude Code** ou d'un autre outil IA compatible.

**Vérifier si Claude Code est installé :**
```bash
claude --version
```

---

### Option 1 — Télécharger et copier (sans programmation)

1. Cliquez sur le bouton vert **Code** → **Download ZIP**
2. Décompressez le fichier — vous obtenez un dossier `zhijiao-skills`
3. Copiez ce dossier dans le répertoire des compétences Claude Code :
   - **Windows :** `C:\Users\VotreNom\.claude\skills\`
   - **Mac/Linux :** `~/.claude/skills/`
4. Tapez `claude` puis `/skills` pour vérifier l'installation

---

### Option 2 — Cloner avec Git

```bash
cd ~/.claude/skills
git clone https://github.com/votre-nom/zhijiao-skills.git
```

---

### Option 3 — Outils IA universels

| Outil | Comment utiliser |
|---|---|
| **Claude.ai (web)** | Téléversez `SKILL.md` ou collez son contenu comme invite système |
| **ChatGPT / GPT-4** | Collez le contenu de `SKILL.md` dans le System Prompt |
| **Cursor / Windsurf** | Ajoutez `SKILL.md` comme fichier de règles du projet |
| **IA locale (Ollama, etc.)** | Utilisez le contenu de `SKILL.md` comme invite système |

---

## Utilisation

Décrivez simplement ce dont vous avez besoin en langage naturel.

### Exemples de prompts

**Créer un diaporama HTML :**
```
Fais un cours sur "Les fractions" pour le CE2, manuel Renjiao
```

**Rédiger un plan de cours :**
```
Je prépare "La première loi de Newton", physique en 4e,
ma classe a beaucoup d'élèves ouïghours — rédige un plan de cours détaillé
```

**Générer des exercices :**
```
Crée une série d'exercices pour "L'addition jusqu'à 100",
CE1 maths, avec niveaux de base, intermédiaire et avancé
```

**Package complet :**
```
La semaine prochaine j'enseigne "Le cycle de l'eau", CM1 sciences —
fais un package complet : plan de cours + diaporama HTML
```

**Avec annotations en langue minoritaire :**
```
Fais un cours sur "Lire l'heure", CE1 maths,
ajoute de petites annotations en ouïghour à côté des termes clés
```

---

## Fonctionnalités

### Diaporamas HTML

| Fonctionnalité | Détails |
|---|---|
| Entièrement hors ligne | Fichier HTML unique, copiez sur clé USB |
| Navigation clavier | Touches ← →, ESC pour vue d'ensemble |
| Support tactile | Balayage sur téléphone et tablette |
| Surbrillance des termes clés | Fond rouge + texte blanc |
| Animations | Couverture particules, révélation d'exemples étape par étape, confettis |
| Révélation des réponses | Cliquez "Voir la réponse" dans les exercices |

### Thèmes de couleurs

| Thème | Idéal pour |
|---|---|
| 🟠 Orange chaud (défaut) | Mathématiques, école primaire |
| 🔵 Bleu ciel | Chinois, anglais, collège |
| 🟢 Vert herbe | Sciences, biologie, géographie |
| ⬛ Noir et blanc fort contraste | Vieux projecteurs, salles très éclairées |

### Annotations en langues minoritaires

| Langue | Code | Région |
|---|---|---|
| Ouïghour | ug | Xinjiang |
| Tibétain | bo | Tibet, Qinghai |
| Kazakh | kk | Xinjiang |
| Mongol | mn | Mongolie intérieure |
| Kirghiz | ky | Xinjiang |

Précisez dans votre prompt : `ajouter des annotations en tibétain`

---

## Structure des fichiers

```
zhijiao-skills/
├── SKILL.md                      ← Point d'entrée principal (lu par l'IA)
├── sub-skills/
│   ├── ppt-html/SKILL.md         ← Génération de diaporamas HTML
│   ├── ppt-pptx/SKILL.md         ← Génération de diaporamas PPTX
│   ├── lesson-plan/SKILL.md      ← Génération de plans de cours
│   └── quiz-bank/SKILL.md        ← Génération de banques d'exercices
├── assets/
│   ├── template-ethnic.html      ← Modèle de base HTML
│   └── emoji-vectors/            ← Icônes SVG préchargées (hors ligne)
├── references/
│   ├── layouts.md                ← 12 squelettes de mise en page
│   ├── themes.md                 ← 4 thèmes de couleurs
│   ├── animations.md             ← Guide d'utilisation des animations
│   ├── minority-languages.md     ← Vocabulaire en langues minoritaires
│   ├── svg-embed-guide.md        ← Référence d'intégration SVG
│   └── checklist.md              ← Liste de contrôle qualité
└── README_CN.md / README.md / README_FR.md
```

---

## Questions fréquentes

**Q : Ai-je besoin de connaissances en programmation ?**
R : Non. L'installation consiste à copier un dossier. L'utilisation se fait en langage naturel.

**Q : Le diaporama généré nécessite-t-il Internet ?**
R : L'IA nécessite Internet pour générer le fichier, mais le fichier `.html` final est entièrement hors ligne.

**Q : Quels navigateurs fonctionnent ?**
R : Chrome, Edge, Firefox, Safari — tous fonctionnent.

**Q : Les traductions en langues minoritaires sont-elles précises ?**
R : Généralement précises, mais les dialectes varient. Pour le contenu important, faites vérifier par un locuteur natif.

---

## Contribution

Les contributions, issues et pull requests sont les bienvenues. Les contributions au vocabulaire des langues minoritaires sont particulièrement appréciées.

---

## Licence

Licence MIT.

---

<div align="center">

Créé avec ❤️ pour les enseignants bénévoles · Que chaque cours illumine les yeux d'un enfant

</div>
