# Le Voyage de Torri

Jeu 3D à la troisième personne réalisé avec **Unreal Engine 5.7** (Blueprints et C++).

<!-- Tu peux ajouter ici l'histoire de Torri, le but du jeu et des captures d'écran. -->

## Le jeu

- **Menu principal** pour lancer une partie, régler les options, voir les crédits ou quitter, avec un écran de chargement et un menu pause.
- **Options** réglables : général, graphismes, audio et contrôles. La liste des touches se trouve dans *Options > Contrôles*.
- **Un monde nature stylisé** à explorer, avec des effets de papillons, de feuilles qui tombent et de vent.
- **Une forêt tropicale** (niveau `Rain_Forest`).
- **Un parcours d'obstacles** avec des plateformes qui bougent et qui tournent (niveau `ObstacleAssault/Maps/Main`).

## Prérequis

- [Unreal Engine 5.7](https://www.unrealengine.com/download), installé via l'Epic Games Launcher
- **Visual Studio 2022** avec la charge de travail *Développement de jeux en C++*, nécessaire pour compiler le code du projet. Le fichier `.vsconfig` du projet propose automatiquement les bons composants à l'ouverture.
- Environ **10 Go** d'espace disque : ~3 Go pour le dépôt, le reste pour la compilation et les shaders.

## Installation

1. Cloner le dépôt (~2,6 Go à télécharger) :
   ```bash
   git clone https://github.com/JLFlo12/Le-Voyage-de-Torri.git
   ```
2. Ouvrir `Le Voyage de Torri-main/ObstacleAssault.uproject`.
3. Quand Unreal demande de reconstruire les modules manquants (*missing modules*), répondre **Oui**.
4. Au premier lancement, la compilation des shaders peut prendre un moment.
5. Le projet s'ouvre sur le menu principal : cliquer sur **Play** dans l'éditeur, puis lancer la partie depuis le menu.

## Structure du projet

| Dossier | Contenu |
| --- | --- |
| `Source/ObstacleAssault` | Code C++ (plateformes mobiles) |
| `Content/Stylized_Nature_Set/MainMenu` | Carte et widgets du menu principal (démarrage du jeu) |
| `Content/Stylized_Nature_Set/Demo/Maps` | Niveau principal, lancé depuis le menu |
| `Content/Rain_Forest` | Niveau forêt tropicale |
| `Content/ObstacleAssault` | Parcours d'obstacles et ses Blueprints |
| `Config` | Configuration du projet (carte de démarrage, entrées…) |

## Code C++

La classe `AMovingPlatform` ([MovingPlatform.h](Le%20Voyage%20de%20Torri-main/Source/ObstacleAssault/MovingPlatform.h)) fait bouger et tourner une plateforme. Trois propriétés se règlent directement dans l'éditeur :

- `MoveVelocity` : direction et vitesse du déplacement
- `MaxMoveDistance` : distance parcourue avant que la plateforme fasse demi-tour
- `RotationVelocity` : vitesse de rotation

## Crédits

- **Assets :** Stylized Nature Set, Rain Forest, Minimalistic Menu et Vefects Easy Impact Frames (Fab / Unreal Marketplace), ainsi que Learning Kit Games, Learning Kit Robots et Hour of Code (Epic Games). Ces assets appartiennent à leurs auteurs et restent soumis à leur propre licence.
