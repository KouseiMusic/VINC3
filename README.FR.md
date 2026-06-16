<p align="center"><img width="190" height="193" alt="vinc3banner" src="https://github.com/user-attachments/assets/ba115c1a-ce26-4999-8672-56a88455eabb" /></p>

_<p align="center">Analyse Audio & Mesure DSP. Visualisation de Fréquence & Monitoring Audio.</p>_

---

![Version](https://img.shields.io/badge/Version-1.2.0-brightgreen?style=flat-square)
![macOS Support](https://img.shields.io/badge/macOS-Sonoma%20%7C%20Sequoia%20%7C%20Tahoe-000000?style=flat-square&logo=apple&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-Universal-black?labelColor=606060&style=flat-square&logo=apple&logoColor=white)
![Format](https://img.shields.io/badge/Format-Standalone-00CED1?style=flat-square)
![DAW](https://img.shields.io/badge/DAW-All-000000?style=flat-square&logo=abletonlive&logoColor=white)


---

<img width="1439" height="868" alt="vinc3preview" src="https://github.com/user-attachments/assets/8f94e5c6-8586-49af-a916-3a74b9249dbc" />

---

## 𝐅𝐨𝐧𝐜𝐭𝐢𝐨𝐧𝐧𝐚𝐥𝐢𝐭é𝐬

- **Moteur de Spectrogramme 3D** : Une vue tridimensionnelle du contenu fréquentiel de votre audio, mise à jour en temps réel. Visualisez comment l'énergie est répartie sur le spectre au fil du temps avec cinq modes d'animation distincts pour répondre à vos préférences analytiques ou esthétiques.
- **Suite de Mesure Complète** : Neuf modules de monitoring indépendants couvrant le loudness, la dynamique, l'image stéréo, la forme d'onde, l'analyse de fréquence et le pitch; tout le nécessaire pour prendre des décisions de mixage et de mastering éclairées sans changer d'outil.
- **Application Standalone** : Fonctionne comme une application macOS native. Pas de navigateur, pas d'abonnement et pas de compte. Ouvrez-la et elle fonctionne.
- **Entièrement Offline** : Aucune connexion internet n'est requise ou utilisée. Tout le traitement se fait localement sur votre machine.
- **Fenêtres de Modules Flottantes** : Chaque module de mesure est une fenêtre indépendante. Faites-les glisser n'importe où sur l'écran, redimensionnez-les à votre guise et sauvegardez cette disposition comme configuration par défaut. Différentes sessions, différentes configurations.
- **Sept Thèmes Visuels** : Alternez entre Teal, Pink, Purple, Green, White, Blue et Windows 98 pour correspondre à votre environnement de studio ou à vos préférences personnelles.
- **Interface Minimaliste** : Thème sombre et haut contraste, conçu pour être lisible d'un coup d'œil dans les environnements de studio peu éclairés sans distraire de l'expérience d'écoute.

---

## 𝐂𝐨𝐧𝐟𝐢𝐠𝐮𝐫𝐚𝐭𝐢𝐨𝐧 𝐑𝐞𝐪𝐮𝐢𝐬𝐞

- **macOS** : 14.0 (Sonoma), 15.0 (Sequoia) ou 16.0 (Tahoe).
- **Architecture** : Intel (x64), Apple Silicon (arm64) & Universal (U2B).
- **RAM** : 4 Go minimum, 8 Go recommandés pour les sessions prolongées avec plusieurs modules ouverts.
- **Compatibilité DAW** : Fonctionne parallèlement à n'importe quel DAW.
- **Permissions** : Accès Microphone (pour le monitoring des entrées matérielles) et Enregistrement de l'écran (pour la capture de l'audio système). Voir la section Permissions ci-dessous.

---

## 𝐈𝐧𝐬𝐭𝐚𝐥𝐥𝐚𝐭𝐢𝐨𝐧
1. Téléchargez la dernière version de [`VINC3`](https://github.com/KouseiMusic/VINC3/releases/download/VINC3_1.2.0/VINC3.app.macOS.U2B.zip).
2. Ouvrez le fichier ZIP téléchargé et faites glisser `VINC3.app` dans votre dossier `Applications`.
3. Avant de lancer l'application pour la première fois, accordez les permissions requises décrites dans la section ci-dessous. Faire cela avant le premier lancement évite de devoir redémarrer l'application.
4. Lancez `VINC3`. Si macOS affiche un avertissement indiquant que l'application provient d'un développeur non identifié, faites un clic droit sur l'icône de l'application, sélectionnez `Ouvrir`, puis confirmez.
5. Lorsque vous y êtes invité, autorisez l'accès au Microphone.
6. Sélectionnez votre source audio. `MIC` pour votre microphone ou interface audio, `SYSTEM` pour tout ce qui est lu par votre ordinateur.
7. Cliquez sur `INITIALIZE` pour démarrer le moteur. Tous les modules actifs commenceront à afficher les données en direct.

---

## 𝐦𝐚𝐜𝐎𝐒 𝐏𝐞𝐫𝐦𝐢𝐬𝐬𝐢𝐨𝐧𝐬

VINC3 nécessite deux permissions pour fonctionner. macOS les demandera automatiquement lors de la première utilisation de chaque fonction, mais les accorder à l'avance via les Réglages Système évite les interruptions pendant une session.

### 1. Accès au Microphone

Requis lors de l'utilisation du mode MIC pour analyser l'audio de votre microphone, de votre interface audio ou de toute entrée matérielle connectée à votre Mac.

`Réglages Système` > `Confidentialité et sécurité` > `Microphone` > activer `VINC3`.

### 2. Enregistrement de l'écran

Requis lors de l'utilisation du mode SYSTEM pour capturer l'audio lu par votre Mac : provenant d'un DAW, d'un service de streaming, d'une vidéo ou de toute autre application. VINC3 n'enregistre pas et ne stocke pas votre écran. macOS utilise la permission d'Enregistrement de l'écran comme passerelle vers la capture de l'audio système, ce qui est une décision d'architecture macOS sans rapport avec l'enregistrement visuel.

`Réglages Système` > `Confidentialité et sécurité` > `Enregistrement de l'écran` > activer `VINC3`.

_VINC3 n'enregistre pas de vidéo, ne filme pas votre écran, ne stocke pas l'audio et ne transmet rien. Ces permissions sont utilisées exclusivement pour le routage du signal audio. Aucune donnée ne quitte votre machine._

---

## 𝐌𝐨𝐝𝐞𝐬 𝐝𝐞 𝐒𝐨𝐮𝐫𝐜𝐞 𝐀𝐮𝐝𝐢𝐨

**SYSTEM - System Audio Loopback**

Capture tout l'audio en cours de lecture via la sortie audio de votre Mac, le bus master de votre DAW, une application de streaming, une vidéo ou tout autre élément. C'est le mode principal pour le monitoring de mastering, les comparaisons d'écoute de référence et la vérification de conformité broadcast.

Sur macOS Sonoma et versions ultérieures, la capture de l'audio système est gérée nativement par le système d'exploitation via ScreenCaptureKit. Aucun périphérique audio virtuel tiers n'est requis. Si vous utilisez une version plus ancienne de macOS, vous aurez besoin d'un pilote audio virtuel tel que [BlackHole](https://github.com/ExistentialAudio/BlackHole) pour router l'audio vers VINC3.

**MIC - Microphone / Entrée matérielle**

Capture l'audio directement depuis votre microphone ou votre interface audio. Utilisez ce mode lorsque vous souhaitez analyser un signal entrant dans votre Mac depuis une source externe, un instrument, un chanteur, un synthétiseur matériel ou tout appareil branché sur votre interface. Aucun logiciel supplémentaire n'est nécessaire.

---

## 𝐌𝐨𝐝𝐮𝐥𝐞𝐬

| Module | Ce qu'il affiche | Options d'affichage |
| :--- | :--- | :--- |
| **Spectrogram 3D** | Une représentation tridimensionnelle du contenu fréquentiel de votre audio au fil du temps. L'énergie est affichée sur tout le spectre, la profondeur représentant l'historique temporel. | Sphere, Wave, Cube, Terminal, Singularity |
| **FFT Meter** | Un affichage précis du spectre de fréquences de 20 Hz à 20 kHz sur une échelle logarithmique (celle utilisée par vos oreilles). Une lecture en direct indique la fréquence la plus forte et le nom de sa note musicale. Des lignes de maintien de crête montrent l'activité transitoire récente. | Line, Bars, Binary |
| **Level Meters** | Mesure du loudness conforme aux standards de l'industrie. Affiche les niveaux de crête pour les canaux gauche et droit en dBFS, ainsi que le LUFS Momentary, Short-Term et Integrated selon la norme ITU-R BS.1770-4. Affiche également le Crest Factor (l'écart entre la crête et la moyenne) qui indique la plage dynamique. | Horizontal, Vertical |
| **Analog VU Meter** | Une recréation fidèle du VU-mètre matériel classique, avec un temps d'intégration balistique de 300 ms qui reflète le loudness perçu, similairement à la façon dont les ingénieurs formés sur consoles analogiques perçoivent le niveau. | Classic needle, Modern LED bar |
| **Oscilloscope** | Affiche la forme d'onde audio brute pour les canaux gauche et droit simultanément en temps réel. Utile pour vérifier la symétrie de la forme d'onde, le clipping et la relation entre les canaux. Le déclencheur par passage à zéro assure un affichage stable et lisible. | - |
| **Stereo Monitor** | Un vectorscope montrant l'image stéréo sous forme de figure de Lissajous. Un signal parfaitement mono apparaît comme une ligne verticale. Un signal stéréo large remplit les coins. Un audio hors phase tire l'image horizontalement. La persistance du phosphore donne une idée de l'historique des mouvements. | - |
| **Pitch & Stats** | Une collection de lectures analytiques : la note musicale dominante présente dans le signal, une estimation du bit depth de l'audio, le DC offset par canal (signe de problèmes matériels ou de plugins) et la corrélation de phase stéréo. | - |
| **Linear Spectrogram** | Un affichage en cascade (waterfall) défilant qui montre l'énergie des fréquences de gauche à droite au fil du temps. Utile pour repérer les résonances soutenues, l'accumulation tonale ou l'énergie basse fréquence difficile à voir sur un affichage FFT standard. | Couleurs du thème, Palette thermique classique |
| **Phase Correlation** | Montre la relation de phase entre les canaux gauche et droit sur une échelle de -1 à +1. Une lecture proche de +1 signifie que les canaux sont en phase et s'additionneront correctement en mono. Une lecture proche de -1 signifie que les canaux sont hors phase et s'annuleront partiellement ou totalement en mono. Affiche également les niveaux Mid et Side. | - |

---

## 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐬

| Contrôle | Ce qu'il fait |
| :--- | :--- |
| **MIC / SYSTEM** | Sélectionne la source audio avant le démarrage. Ne peut pas être modifié pendant que le moteur tourne. |
| **OPTIONS** | Ouvre le panneau de réglages pour la sélection du thème et la visibilité des modules. Accessible à tout moment, y compris pendant que le moteur tourne. |
| **INITIALIZE** | Démarre le moteur audio et active tous les modules visibles. Les permissions vous seront demandées lors de la première utilisation. |
| **STOP** | Arrête le moteur audio et efface toutes les lectures actives. Les réglages et la disposition sont conservés. |
| **SAVE** | Sauvegarde les positions actuelles, les tailles et la visibilité de tous les modules, ainsi que le thème et la source sélectionnés comme disposition par défaut. |
| **LOAD** | Restaure la disposition sauvegardée la plus récente. Utile si vous avez déplacé des fenêtres par erreur ou si vous souhaitez revenir à un agencement connu. |
| **RESET** | Réinitialise toutes les fenêtres de modules à leurs positions et tailles d'usine par défaut. N'affecte pas le thème ou la sélection de la source. |
| **Module - Move** | Cliquez et maintenez n'importe où sur la surface d'une fenêtre de module (loin de la poignée de redimensionnement) et faites glisser pour la repositionner n'importe où sur l'écran. |
| **Module - Resize** | Faites glisser la petite poignée dans le coin inférieur droit de n'importe quelle fenêtre de module pour la redimensionner. |
| **App window - Resize** | Faites glisser les bords ou les coins de la fenêtre principale de VINC3 pour redimensionner la zone globale de l'application. |

---

## 𝐂𝐫𝐞𝐝𝐢𝐭𝐬

- **Sponsor / Mécénat** : Vincent P.

---

_Ce logiciel est gratuit. Si vous le trouvez utile, une ⭐️ sur GitHub aide les autres à le découvrir._

---

<p align="center"><code>Kousei</code></p>
<p align="center">2026</p>