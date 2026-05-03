# 🥏 Ultimate EPS — Application Enseignant

Application web progressive tout-en-un pour l'enseignement de l'Ultimate en EPS. Conçue pour être utilisée sur **smartphone ou tablette**, directement depuis un fichier HTML local — aucune installation, aucun serveur requis.

---

## 🔐 Connexion

Au lancement, un écran de connexion protège l'accès à l'application.

- **Mot de passe :** `epsultimate`
- Le mot de passe est stocké sous forme de hash SHA-256 fragmenté dans le code source — il n'est pas lisible en clair.
- Appuyez sur 👁️ pour afficher/masquer le mot de passe saisi.
- La touche **Entrée** valide la connexion.

---

## 📋 Onglet Tests

### ⚡ Efficacité Collective

Évalue l'efficacité d'une équipe sur ses possessions de disque, sur deux matchs.

**Fonctionnement :**
1. Saisir ou choisir le nom de l'équipe observée (bouton 📋 pour piocher dans la liste des équipes).
2. Sélectionner le match en cours (Match 1 ou Match 2).
3. Pour chaque possession, taper le nombre de **zones atteintes** (0 à 4).
4. Si au moins 1 zone est atteinte, indiquer si un **point a été marqué** (non / après 1 zone / après 2 zones ou plus).
5. Appuyer sur **➕ Enregistrer la possession** — jusqu'à 20 possessions par match.

**Barème des points par possession :**

| Zones atteintes | Points de base | + Point après 1 zone | + Point après 2z+ |
|:-:|:-:|:-:|:-:|
| 0 | 0 | — | — |
| 1 | 1 | +1 | — |
| 2 | 2 | +1 | +3 |
| 3 | 3 | +1 | +3 |
| 4 | 4 | +1 | +3 |

**Résultats calculés automatiquement :**
- Nombre de possessions, total de points, indice d'efficacité (pts / possessions) par match
- Note /20 basée sur le barème officiel
- Niveau de maîtrise : ✅✅ Très bonne · ✅ Bonne · ❌ Fragile · ❌❌ Insuffisante

**Barème de notation :**

| Indice | Note /20 |
|:-:|:-:|
| ≥ 3,5 | 20 |
| ≥ 3,3 | 19 |
| ≥ 3,1 | 18 |
| … | … |
| ≥ 0,6 | 1 |
| < 0,6 | 0 |

---

### 👤 Efficacité Individuelle

Évalue un joueur sur la qualité de ses actions, sur deux matchs.

**Fonctionnement :**
1. Saisir ou choisir le joueur observé (bouton 📋).
2. Renseigner l'observateur.
3. Sélectionner le match.
4. Comptabiliser les **actions négatives** (mauvaise passe / réception → perte du disque) et les **actions positives** (passe conservée, interception, défense décisive, score).

**Calcul automatique :**
- % d'efficacité = actions positives / total d'actions
- Niveau de maîtrise affiché en temps réel

| % Efficacité | Niveau |
|:-:|:-|
| > 75 % | ✅✅ Très bonne maîtrise — Les choix sont déterminants |
| 60 – 75 % | ✅ Bonne maîtrise — Choix souvent bons |
| 30 – 60 % | ❌ Maîtrise fragile — 1 action sur 2 incorrecte |
| < 30 % | ❌❌ Maîtrise insuffisante — Mauvais choix importants |

---

## 🏟️ Onglet Terrain — Gagne Terrain

Suivi en temps réel d'un match, avec inversion automatique du terrain.

**Réglage :**
- Sélectionner les deux équipes en jeu depuis la liste des équipes créées (ou saisir les noms librement).

**Saisie d'une possession :**
1. Taper les zones atteintes dans l'ordre (Z1 → Z2 → Z3 → Z4 → 🏆 En-But).
2. Bouton ↩ pour annuler la dernière zone.
3. **🏆 POINT !** pour valider un score ou **🔄 TURNOVER** pour changer de possession.

**Inversion automatique du terrain :**
Après chaque point marqué ou chaque turnover, le schéma du terrain s'inverse — l'en-but est toujours affiché **à droite** du point de vue de l'équipe qui attaque, ce qui facilite la saisie sans se tromper de sens.

Le score, l'équipe attaquante et l'historique des possessions sont mis à jour en temps réel.

---

## 👥 Onglet Élèves

### 📋 Liste des élèves

Gestion complète des élèves avec filtres et tri.

**Ajouter un élève :**
- Renseigner nom, prénom, sexe (♂/♀), classe et niveau (1 à 5 étoiles).
- Le niveau est modifiable directement sur la fiche en cliquant les étoiles.

**Importer depuis Pronote / Excel :**
- Bouton 📥 Excel — accepte les formats `.xlsx`, `.xls`, `.csv`.
- L'application détecte automatiquement les colonnes Nom, Prénom, Sexe.
- Les colonnes sans en-tête sont également gérées (prénom + nom sur une seule colonne).

**Statuts des élèves (clic sur l'avatar) :**
- 1 clic → 🚫 **Absent** (exclu des équipes générées)
- 2 clics → 🤕 **Blessé** (peut être assigné comme 🟡 arbitre)
- 3 clics → ✅ **Actif** (retour au statut normal)

**Gestion des classes :**
- Créer plusieurs classes (CA4, 5ème A, 6ème B…) via le bouton + Classe.
- Chaque classe a sa propre liste, ses propres équipes et son propre tournoi.
- Basculer entre les classes depuis la barre en haut de l'onglet.

### 💞 Affinités

Définir des relations entre élèves pour optimiser la génération d'équipes.

- **💚 Affinités** : ces élèves seront placés dans la même équipe si possible.
- **🚫 Incompatibilités** : ces élèves ne seront jamais dans la même équipe.

---

## 🎽 Onglet Équipes

### Configuration

| Paramètre | Valeurs disponibles |
|:-|:-|
| Nombre d'équipes | 2, 3, 4, 5 ou 6 |
| Format de jeu | 3v3, 4v4, 5v5, 6v6, 7v7 |
| Mode de génération | 7 modes (voir ci-dessous) |

### Modes de génération

| Mode | Description |
|:-|:-|
| ⚖️ Homogène mixte | Niveaux équilibrés, sexes mélangés |
| 🔵 Homogène démixé | Niveaux équilibrés, équipes mono-sexe |
| 🔀 Hétérogène mixte | Forts et faibles ensemble, sexes mélangés |
| 🟠 Hétérogène démixé | Forts et faibles ensemble, mono-sexe |
| ⭐ Par niveau | Élèves de même niveau regroupés |
| 💚 Affinités | Respecte les préférences des élèves |
| 🚫 Contraintes | Évite absolument les incompatibilités |

- **🎲 Générer** : crée de nouvelles équipes avec couleurs aléatoires parmi 9 disponibles (Rose, Bleu foncé, Bleu ciel, Vert, Noir, Orange, Rouge, Violet, Jaune).
- **🔄 Mixer** : remélange les joueurs dans les équipes existantes sans rechanger les noms ni les couleurs.

### Noms des équipes par couleur

Les équipes sont automatiquement nommées d'après leur couleur (ex : *Équipe Rose*, *Équipe Bleu ciel*). Le nom et la couleur sont modifiables depuis le bouton ✏️ de chaque équipe.

### Transfert de joueurs

Un **appui long** (maintenir ~0,5s) sur un joueur dans une équipe ouvre un menu de transfert vers une autre équipe.

---

## 🏆 Onglet Tournoi

Génération automatique d'un **round-robin** : chaque équipe joue contre toutes les autres.

**Réglages :**
- Nombre de terrains simultanés (1 à 4).

**Navigation :**
- 📅 **Planning** : liste de tous les matchs avec indication de l'avancement.
- ⚽ **Scores** : saisie des scores match par match.
- 🏆 **Classement** : tableau de classement mis à jour en temps réel.

**Système de points :**
- Victoire = 3 pts · Nul = 1 pt · Défaite = 0 pt

Les noms et couleurs des équipes sont affichés dans tout le tournoi.

---

## 💾 Export / Import

Accessible via le bouton 💾 en haut à droite.

| Action | Format | Contenu |
|:-|:-|:-|
| 📊 Équipes → Excel | `.xlsx` | Résumé + liste détaillée par équipe |
| 🏆 Tournoi → Excel | `.xlsx` | Calendrier des matchs + scores |
| 👥 Élèves → Excel | `.xlsx` | Liste complète avec niveaux |
| 📤 Sauvegarde | `.json` | Toutes les données (élèves, équipes, tournoi) |
| 📥 Importer | `.json` | Restauration complète d'une sauvegarde |

Les données sont également sauvegardées **automatiquement** dans le navigateur (localStorage) à chaque modification.

---

## ⚙️ Paramètres

Accessible via le bouton ⚙️ en haut à droite.

- Visualiser et supprimer les classes enregistrées.
- **🗑️ Tout effacer et recommencer** : efface intégralement toutes les données (irréversible).

---

## 📱 Compatibilité

| Plateforme | Support |
|:-|:-|
| iOS Safari | ✅ Recommandé |
| Android Chrome | ✅ Recommandé |
| iPad / tablette | ✅ Optimal |
| Navigateur desktop | ✅ Compatible |

L'application fonctionne **hors ligne** une fois le fichier chargé. Aucune connexion internet n'est nécessaire pour l'utilisation (la police de caractères nécessite une connexion au premier chargement).

---

## 🗂️ Structure du fichier

```
ultimate-final.html   ← Application complète en un seul fichier autonome
README.md             ← Ce document
```

Toute la logique, le style et les données sont contenus dans un unique fichier `.html` de ~1 600 lignes.

---

*Application développée pour l'enseignement de l'Ultimate Frisbee en cours d'EPS — Cycle 4.*
