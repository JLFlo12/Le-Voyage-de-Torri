<div align="center">

# Le Voyage de Torri

**Jeu 3D à la troisième personne réalisé avec Unreal Engine 5.7**

[🇬🇧 English](README.md) · 🇫🇷 Français

![Unreal Engine](https://img.shields.io/badge/Unreal%20Engine-5.7-0E1128?logo=unrealengine&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?logo=cplusplus&logoColor=white)
![Blueprints](https://img.shields.io/badge/Blueprints-visual%20scripting-1E90FF)
![Plateforme](https://img.shields.io/badge/Plateforme-Windows-0078D6)
![Licence : MIT (code)](https://img.shields.io/badge/Licence-MIT%20(code)-yellow.svg)

</div>

---

## Présentation

*Le Voyage de Torri* est un jeu 3D personnel à la troisième personne, développé avec **Unreal Engine 5.7** en **Blueprints** et en **C++**. On y explore un monde nature stylisé, une forêt tropicale et un parcours d'obstacles avec des plateformes mobiles.

## Fonctionnalités

- **Menu principal** pour lancer une partie, régler les options, voir les crédits ou quitter, avec un écran de chargement et un menu pause
- **Options** réglables : général, graphismes, audio et contrôles. La liste des touches se trouve dans *Options > Contrôles*.
- **Un monde nature stylisé** à explorer, avec des effets de papillons, de feuilles qui tombent et de vent
- **Une forêt tropicale**
- **Un parcours d'obstacles** avec des plateformes qui bougent et tournent, pilotées par du code C++

## Niveaux

| Niveau | Carte | Description |
| --- | --- | --- |
| Menu principal | `Content/Stylized_Nature_Set/MainMenu/MainMenu` | Carte de démarrage du jeu et de l'éditeur |
| Monde nature | `Content/Stylized_Nature_Set/Demo/Maps/Demo_Level` | Niveau principal, lancé depuis le menu |
| Forêt tropicale | `Content/Rain_Forest/Maps/Rain_Forest` | Forêt tropicale |
| Parcours d'obstacles | `Content/ObstacleAssault/Maps/Main` | Plateformes mobiles et rotatives |

## Prérequis

- **Windows 10/11**
- [Unreal Engine 5.7](https://www.unrealengine.com/download), installé via l'Epic Games Launcher
- **Visual Studio 2022** avec la charge de travail *Développement de jeux en C++*, nécessaire pour compiler le code C++ du projet. Le fichier `.vsconfig` du projet propose automatiquement les bons composants à l'ouverture.
- Environ **10 Go** d'espace disque : ~3 Go pour le dépôt, le reste pour la compilation et les shaders

## Installation

1. Cloner le dépôt (~2,6 Go à télécharger) :

   ```bash
   git clone --depth 1 https://github.com/JLFlo12/Le-Voyage-de-Torri.git
   ```

   `--depth 1` ne récupère pas l'historique Git, ce qui accélère le téléchargement.

2. Ouvrir `Le Voyage de Torri-main/ObstacleAssault.uproject`.
3. Quand Unreal demande de reconstruire les modules manquants (*missing modules*), répondre **Oui**.
4. Au premier lancement, la compilation des shaders peut prendre un moment.
5. Le projet s'ouvre sur le menu principal : cliquer sur **Play** dans l'éditeur, puis lancer la partie depuis le menu.

> [!TIP]
> Pour tester un seul niveau, ouvrez sa carte depuis le Content Browser (voir [Niveaux](#niveaux)) et cliquez sur **Play**.

## Structure du projet

Le projet Unreal se trouve dans le dossier `Le Voyage de Torri-main/`.

| Dossier | Contenu |
| --- | --- |
| `Source/ObstacleAssault` | Code C++ (plateformes mobiles) |
| `Content/Stylized_Nature_Set/MainMenu` | Carte et widgets du menu principal (démarrage du jeu) |
| `Content/Stylized_Nature_Set/Demo/Maps` | Niveau principal, lancé depuis le menu |
| `Content/Rain_Forest` | Niveau forêt tropicale |
| `Content/ObstacleAssault` | Parcours d'obstacles et ses Blueprints |
| `Content/…` | Autres packs d'assets utilisés par les niveaux (voir [Crédits](#crédits)) |
| `Config` | Configuration du projet (carte de démarrage, entrées…) |
| `Plugins/VisualStudioTools` | Plugin Microsoft d'intégration à Visual Studio |

## Code C++

La classe `AMovingPlatform` ([MovingPlatform.h](Le%20Voyage%20de%20Torri-main/Source/ObstacleAssault/MovingPlatform.h), [MovingPlatform.cpp](Le%20Voyage%20de%20Torri-main/Source/ObstacleAssault/MovingPlatform.cpp)) déplace et fait tourner une plateforme à chaque image. Quand la plateforme a parcouru plus de `MaxMoveDistance`, elle fait demi-tour.

Trois propriétés se règlent directement dans l'éditeur :

| Propriété | Type | Rôle |
| --- | --- | --- |
| `MoveVelocity` | `FVector` | Direction et vitesse du déplacement |
| `MaxMoveDistance` | `float` | Distance parcourue avant le demi-tour |
| `RotationVelocity` | `FRotator` | Vitesse de rotation |

## Crédits

**Assets :** Stylized Nature Set, Rain Forest, Minimalistic Menu et Vefects Easy Impact Frames (Fab / Unreal Marketplace), ainsi que Learning Kit Games, Learning Kit Robots et Hour of Code (Epic Games).

Ces assets appartiennent à leurs auteurs et restent soumis à leur propre licence.

## Licence

Le code original de ce dépôt (principalement `Source/`) est distribué sous [licence MIT](LICENSE).
Les assets et plugins tiers ne sont **pas** couverts par cette licence (voir [Crédits](#crédits)).
