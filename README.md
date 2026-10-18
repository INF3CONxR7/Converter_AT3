<p align="center">
  <img src="logo.png" alt="Logo de Converter AT3" width="128">
</p>

<h1 align="center">Converter AT3</h1>

<p align="center">
  Convertissez vos musiques en <b>SND0.AT3</b> (ATRAC3) pour le son de lancement XMB de vos backups PS3,<br>
  et écoutez vos fichiers <b>.AT3</b> d’un double-clic.
</p>

<p align="center">
  <a href="https://github.com/INF3CONxR7/Converter_AT3/releases/latest"><img src="https://img.shields.io/github/v/release/INF3CONxR7/Converter_AT3?label=t%C3%A9l%C3%A9charger&color=1CC4C8" alt="Télécharger"></a>
  <img src="https://img.shields.io/badge/Windows-10%20%7C%2011-0078D6?logo=windows&logoColor=white" alt="Windows 10 et 11">
  <a href="https://discord.gg/TbFYvqsh5z"><img src="https://img.shields.io/badge/Discord-rejoindre-5865F2?logo=discord&logoColor=white" alt="Serveur Discord"></a>
</p>

---

## Sommaire

- [Fonctionnalités](#fonctionnalités)
- [Installation](#installation)
- [Créer un son de lancement](#créer-un-son-de-lancement)
- [Lecteur AT3](#lecteur-at3)
- [Mises à jour et Discord](#mises-à-jour-et-discord)
- [En cas de problème](#en-cas-de-problème)
- [Désinstaller](#désinstaller)
- [Crédits et licences](#crédits-et-licences)

## Fonctionnalités

- **Conversion audio** : MP3, WAV, WMA, M4A/AAC, FLAC… vers un WAV, puis vers l’**ATRAC3** de Sony en 66, 105 ou
  132 kbit/s.
- **Export direct en SND0.AT3** : fichier en boucle sur tout le morceau, prêt à copier dans la backup.
- **Extrait choisi sur la forme d’onde** : 55 s par défaut à partir du début du son, réglable à la souris, avec un
  fondu aux bords coupés pour une boucle sans claquement.
- **Contrôle de compatibilité XMB** : nom du fichier, format, durée et taille vérifiés avant et après l’export.
- **Écoute du fichier source** avant toute conversion.
- **Lecteur AT3** : double-clic sur un `.AT3` pour l’écouter en boucle comme dans le XMB, en **ATRAC3** comme en
  **ATRAC3plus** (les sons officiels des jeux), sans rien extraire.
- **Mises à jour automatiques** et **présence Discord**.

## Installation

1. Téléchargez `ConverterAT3-win-x64.zip` dans la
   [dernière version](https://github.com/INF3CONxR7/Converter_AT3/releases/latest).
2. Décompressez le dossier où vous voulez (Documents, Bureau…).
3. Lancez **Converter AT3.exe**.

Il faut **Windows 10 ou 11 (64 bits)**, rien d’autre à installer.

Au premier lancement, Windows peut afficher « Windows a protégé votre ordinateur » : cliquez sur
*Informations complémentaires*, puis *Exécuter quand même*.

Gardez ensemble tous les fichiers du dossier : l’application en a besoin pour encoder l’ATRAC3, lire l’ATRAC3plus et
se mettre à jour.

## Créer un son de lancement

1. **Fichier source** : *Parcourir*, ou glissez une musique sur la fenêtre. Le bouton ▶ l’écoute.
2. **Extrait** : sur la forme d’onde, déplacez la bande ambre ou tirez ses bords. Au-delà de 55 s, la fin de la bande
   est hachurée : c’est possible, mais plus long que conseillé.
3. **Conversion WAV** : gardez **44.1 kHz** et **Stéréo**, les réglages attendus par le XMB.
4. **Profil ATRAC3** : 132 kbit/s pour la meilleure qualité, 105 ou 66 kbit/s pour un fichier plus léger.
5. **Exporter AT3** : gardez le nom `SND0.AT3`, choisissez le dossier de destination, puis **Convertir en .AT3**.

Le cadre en bas de la page indique si le fichier convient au XMB :

| Exigence | Valeur |
|---|---|
| Nom | `SND0.AT3` (S, N, D, puis le **chiffre zéro**, pas la lettre O) |
| Format | ATRAC3, 44,1 kHz, stéréo |
| Durée conseillée | 30 à 55 secondes |
| Taille maximale | 2,4 Mo |

Repères : un extrait de 55 s fait environ 0,87 Mo à 132 kbit/s. La limite de 2,4 Mo correspond à environ 2 min 32 à
132 kbit/s, 3 min 12 à 105 kbit/s et 5 min 04 à 66 kbit/s : la bande de l’extrait ne peut pas aller au-delà.

**Sur la PS3** : copiez `SND0.AT3` dans le dossier `PS3_GAME` de la backup (par exemple
`/dev_hdd0/GAMES/<nom du jeu>/PS3_GAME/`), en remplaçant l’ancien fichier ; gardez-en une copie si vous voulez revenir
à la musique d’origine. La musique se joue quand le jeu est sélectionné dans le XMB.

## Lecteur AT3

- **Double-clic sur un fichier .AT3** : le lecteur s’ouvre et la musique démarre, en boucle comme dans le XMB.
- **Depuis le convertisseur** : glissez un `.AT3` sur la fenêtre principale, le lecteur s’ouvre à côté.
- Il affiche la durée, le format, la taille et la boucle du fichier. Le bouton *Boucle* arrête ou relance la lecture
  en boucle, *Afficher dans le dossier* ouvre l’Explorateur sur le fichier.
- Vous pouvez écouter les `SND0.AT3` officiels des jeux (ATRAC3plus) comme ceux que vous créez (ATRAC3).

## Mises à jour et Discord

- **Mises à jour** : l’application vérifie les nouvelles versions au démarrage. Le bouton de la version, en haut à
  droite, indique quand une mise à jour est disponible ; elle s’installe en un clic, puis l’application redémarre.
- **Présence Discord** : si Discord est ouvert, votre profil indique ce que fait l’application (sans jamais montrer le
  nom de vos fichiers). Le bouton aux ondes, à côté de la version, l’affiche ou la masque.
- Les logos Discord et GitHub de l’en-tête ouvrent le serveur Discord et la page GitHub de l’auteur.

## En cas de problème

| Problème | Solution |
|---|---|
| La musique ne se joue pas dans le XMB | Vérifiez le nom (`SND0.AT3`, avec un **zéro**), l’emplacement (`PS3_GAME`), et que le cadre de compatibilité était vert : 44.1 kHz, stéréo, 2,4 Mo au plus. |
| Le double-clic n’ouvre pas les `.AT3` | Un autre programme les ouvre déjà : clic droit sur le fichier, *Ouvrir avec*, puis Converter AT3. Lancez l’application une fois si elle n’apparaît pas dans la liste. |
| « Fichier illisible » à l’ouverture d’une musique | Le format n’est pas lu par Windows : convertissez-la d’abord en MP3 ou en WAV. |
| L’application ne démarre pas | Vérifiez que tous les fichiers du dossier sont présents ; sinon, retéléchargez la dernière version. |

Une question ? Rejoignez le [serveur Discord](https://discord.gg/TbFYvqsh5z).

## Désinstaller

Supprimez le dossier de l’application. Elle garde aussi, pour votre compte Windows :

| Emplacement | Contenu |
|---|---|
| `HKEY_CURRENT_USER\Software\ConverterAT3` | Réglages (dossiers, fréquence, canaux, profil, activité Discord). |
| `HKEY_CURRENT_USER\Software\Classes\.at3` et `…\ConverterAT3.At3` | Ouverture des `.AT3` par double-clic. |
| `%LocalAppData%\Converter AT3` | Journal des mises à jour. |

Vous pouvez supprimer ces clés et ce dossier.

## Crédits et licences

- **Converter AT3** : © 2026 INF3C7ONxR7. Tous droits réservés.
- **Décodeur ATRAC3plus** (`Converter_AT3.Atrac3Plus.dll`) : adaptation du décodeur ATRAC3+ de
  [FFmpeg](https://ffmpeg.org/) (© 2010-2013 Maxim Poliakovski), sous licence GNU LGPL 2.1 ou ultérieure. La licence
  est livrée avec l’application (`Converter_AT3.Atrac3Plus.LICENSE.txt`) et le code source de cette bibliothèque est
  joint à chaque version (`Converter_AT3.Atrac3Plus-source.zip`). Vous pouvez la remplacer par une version modifiée.
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
