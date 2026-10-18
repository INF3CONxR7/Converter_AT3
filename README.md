<h1 align="center">Converter AT3</h1>

<p align="center">
  Convertissez vos musiques en <b>SND0.AT3</b> (ATRAC3) pour le son de lancement XMB de vos backups PS3,<br>
  et écoutez vos fichiers <b>.AT3</b> d’un double-clic.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Windows-10%20%7C%2011-0078D6?logo=windows&logoColor=white" alt="Windows 10 et 11">
  <img src="https://img.shields.io/badge/.NET-10-512BD4?logo=dotnet&logoColor=white" alt=".NET 10">
  <img src="https://img.shields.io/badge/version-1.0.0-1CC4C8" alt="Version 1.0.0">
  <a href="https://discord.gg/TbFYvqsh5z"><img src="https://img.shields.io/badge/Discord-rejoindre-5865F2?logo=discord&logoColor=white" alt="Serveur Discord"></a>
</p>

---

## Sommaire

- [Fonctionnalités](#fonctionnalités)
- [Téléchargement](#téléchargement)
- [Créer un son de lancement](#créer-un-son-de-lancement)
- [Lecteur AT3](#lecteur-at3)
- [Compiler le projet](#compiler-le-projet)
- [Organisation de la solution](#organisation-de-la-solution)
- [Ce que l’application garde sur votre PC](#ce-que-lapplication-garde-sur-votre-pc)
- [Crédits et licences](#crédits-et-licences)

## Fonctionnalités

- **Conversion audio** : MP3, WAV, WMA, M4A/AAC, FLAC… (décodeurs intégrés à Windows) vers un WAV PCM 16 bits
  (44,1 ou 48 kHz, stéréo ou mono), puis vers l’**ATRAC3** de Sony en 66, 105 ou 132 kbit/s.
- **Export direct en SND0.AT3** : fichier en boucle sur tout le morceau, comme ceux de l’outil officiel de Sony,
  prêt à copier dans le dossier `PS3_GAME` de la backup.
- **Extrait choisi sur la forme d’onde** : 55 s par défaut à partir du début du son (le silence d’ouverture est
  sauté), réglable à la souris, avec un fondu aux bords coupés pour une boucle sans claquement.
- **Contrôle de compatibilité XMB** : nom du fichier (`SND0` avec un zéro), attributs du WAV, durée de l’extrait et
  taille estimée du fichier, vérifiée encore après l’encodage.
- **Écoute du fichier source**, avec sa forme d’onde, avant toute conversion.
- **Lecteur AT3** dans une fenêtre à part : double-clic sur un `.AT3`, lecture en boucle comme dans le XMB, en
  **ATRAC3** comme en **ATRAC3plus** (les sons officiels des jeux), sans rien extraire.
- **Mises à jour automatiques** depuis les versions GitHub, signées et vérifiées avant l’installation.
- **Présence Discord** : votre profil indique ce que fait l’application (désactivable depuis l’en-tête).

## Téléchargement

1. Téléchargez `ConverterAT3-win-x64.zip` dans les
   [versions du dépôt](https://github.com/INF3CONxR7/Converter_AT3/releases).
2. Décompressez le dossier où vous voulez (Documents, Bureau, Program Files…).
3. Lancez **Converter AT3.exe**.

Rien d’autre à installer : le runtime .NET est inclus dans l’exécutable. Il faut **Windows 10 ou 11 (64 bits)** ;
l’encodeur ATRAC3 utilise le .NET Framework 4.8, déjà présent dans Windows.

Gardez ensemble tous les fichiers du dossier : `Converter AT3.exe`, `Converter AT3 Update.exe` (mises à jour),
`Converter AT3 Encoder.exe` et `atrac3.acm` (encodeur ATRAC3), `Converter_AT3.Atrac3Plus.dll` et sa licence (lecture de
l’ATRAC3plus).

## Créer un son de lancement

1. **Fichier source** : *Parcourir*, ou glissez une musique sur la fenêtre. Le bouton ▶ l’écoute.
2. **Extrait** : sur la forme d’onde, déplacez la bande ambre ou tirez ses bords. Au-delà de 55 s, la fin de la bande
   est hachurée : c’est possible, mais plus long que conseillé.
3. **Conversion WAV** : gardez **44.1 kHz** et **Stéréo**, les attributs attendus par le XMB.
4. **Profil ATRAC3** : 132 kbit/s pour la meilleure qualité, 105 ou 66 kbit/s pour un fichier plus léger.
5. **Exporter AT3** : nom `SND0.AT3`, dossier `PS3_GAME` de votre backup, puis **Convertir en .AT3**. Le WAV est refait
   s’il ne correspond plus à vos réglages.

Le cadre en bas de la page indique si le fichier convient au XMB :

| Exigence | Valeur |
|---|---|
| Nom et emplacement | `PS3_GAME/SND0.AT3` (S, N, D, puis le **chiffre zéro**) |
| Format | ATRAC3, 44,1 kHz, stéréo, en boucle |
| Durée conseillée | 30 à 55 secondes |
| Taille maximale | 2,4 Mo |

Repères : un extrait de 55 s fait environ 0,87 Mo à 132 kbit/s. La limite de 2,4 Mo correspond à environ 2 min 32 à
132 kbit/s, 3 min 12 à 105 kbit/s et 5 min 04 à 66 kbit/s ; la bande de l’extrait ne peut pas aller au-delà.

## Lecteur AT3

- **Double-clic sur un fichier .AT3** : la fenêtre du lecteur s’ouvre et la musique démarre, en boucle comme dans le
  XMB. L’association des `.AT3` est faite pour votre compte au lancement de l’application (sans droits
  d’administrateur) ; si un autre programme ouvre déjà les `.AT3`, il le reste et Converter AT3 apparaît dans
  *Ouvrir avec*.
- **Depuis le convertisseur** : glissez un `.AT3` sur la fenêtre principale, le lecteur s’ouvre à côté.
- Affiche la durée, le format (ATRAC3 et son débit, ou ATRAC3plus), la taille et la boucle du fichier ; boutons
  *Boucle* et *Afficher dans le dossier*.
- Le fichier est décodé dans un WAV temporaire, écouté puis supprimé : rien n’est écrit à côté de votre fichier.

## Compiler le projet

Prérequis : **Visual Studio 2026** avec la charge de travail *Développement .NET Desktop* (SDK .NET 10 et pack de
ciblage .NET Framework 4.8, pour l’encodeur).

```bash
dotnet build Converter_AT3.slnx -c Debug
```

Ou ouvrez `Converter_AT3.slnx` dans Visual Studio. La compilation copie à côté de l’application l’encodeur ATRAC3, le
codec, le décodeur ATRAC3plus et (en Debug) le programme de mise à jour.

Pour publier une version (exécutables autonomes, paquet `.zip` signé, notes de version), utilisez
`build\Publish-Release.ps1`. Le fonctionnement des mises à jour, la création de la clé de signature
(`build\New-SigningKey.ps1`) et la publication sur GitHub sont expliqués dans
[build/README-MISES-A-JOUR.md](build/README-MISES-A-JOUR.md).

## Organisation de la solution

| Dossier | Rôle |
|---|---|
| `Converter_AT3.csproj`, `Resources/` | L’application WinForms (.NET 10) : fenêtres, pages, contrôles dessinés, audio, Discord, mises à jour. |
| `Encoder/Converter_AT3.Encoder` | Encodeur et décodeur ATRAC3 (.NET Framework 4.8, 32 bits) : il charge le codec de Sony `atrac3.acm`, une bibliothèque 32 bits que l’application 64 bits ne peut pas charger elle-même. |
| `Atrac3Plus/Converter_AT3.Atrac3Plus` | Décodeur ATRAC3plus du lecteur AT3, portage en C# du décodeur de FFmpeg (LGPL). |
| `Updates/` | Système de mise à jour : bibliothèque commune et programme `Converter AT3 Update.exe`. |
| `build/` | Scripts de publication et de clé de signature, outil de signature des versions. |

## Ce que l’application garde sur votre PC

| Emplacement | Contenu |
|---|---|
| `HKEY_CURRENT_USER\Software\ConverterAT3` | Réglages : dossiers, fréquence, canaux, profil, activité Discord. |
| `HKEY_CURRENT_USER\Software\Classes\.at3` et `…\ConverterAT3.At3` | Ouverture des `.AT3` par double-clic. |
| `%TEMP%\Converter AT3` | Copies d’écoute temporaires, supprimées à la fermeture du fichier. |
| `%LocalAppData%\Converter AT3\Logs` | Journal des mises à jour. |

Pour tout retirer : supprimez le dossier de l’application, puis ces clés et dossiers.

## Crédits et licences

- **Converter AT3** : © 2026 INF3C7ONxR7.
- **Décodeur ATRAC3plus** (`Converter_AT3.Atrac3Plus`) : portage du décodeur ATRAC3+ de
  [FFmpeg](https://ffmpeg.org/) (© 2010-2013 Maxim Poliakovski), sous licence
  [GNU LGPL 2.1 ou ultérieure](Atrac3Plus/Converter_AT3.Atrac3Plus/LICENSE.txt). Il reste une bibliothèque à part,
  remplaçable, livrée avec sa licence.
- **Codec ATRAC3** (`atrac3.acm`) : codec de Sony.
- **Logos Discord et GitHub** : tracés de [Simple Icons](https://simpleicons.org/) (CC0) ; ces logos sont des marques
  de leurs propriétaires.

Projet non officiel, sans lien avec Sony. PlayStation, PS3 et ATRAC sont des marques de Sony Interactive Entertainment
et de Sony Group Corporation.

---

<p align="center">
  <a href="https://discord.gg/TbFYvqsh5z">Serveur Discord</a> ·
  <a href="https://github.com/INF3CONxR7/">GitHub</a>
</p>
