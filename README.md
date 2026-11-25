# Distagañ, coach de prononciation bretonne

Page web statique qui fonctionne entièrement dans le navigateur (ordinateur ou Android) :
la phrase cible s'affiche, on écoute la voix de référence, on s'enregistre, puis le coach
transcrit avec le modèle Vosk breton d'Anaouder et colore chaque mot.

## Contenu
- `index.html` : l'application
- `phrases.json` : phrases de départ (on peut en ajouter dans l'appli, elles restent sur l'appareil)
- `model.tar.gz` : modèle `vosk-model-br-26.01` (Gweltaz Duval-Guennoc, via https://github.com/gweltou/patromou), repaqueté en tar.gz
- `vocab.txt` : vocabulaire du modèle (pour signaler les mots inconnus)
- `vosk.js` : vosk-browser 0.0.8 (Apache-2.0)

## Mise en ligne
Le micro exige une adresse HTTPS (ou localhost). Publié avec GitHub Pages : https://periggouanvic.github.io/pokou/
Test local : `python3 -m http.server 8000`, puis http://localhost:8000

## Voix de référence
- Depuis chez elle : la personne modèle ouvre https://periggouanvic.github.io/pokou/#maman, enregistre les phrases et touche « Envoyer mes enregistrements » (partage Android : courriel, WhatsApp…). Les fichiers WAV portent l'identifiant de la phrase ; on les importe dans « Enregistrer la voix de référence > Importer les fichiers reçus ».
- Dans l'appli : « Enregistrer la voix de référence » (stocké sur l'appareil).
- Ou pour tous les appareils : déposer `refs/<id>.mp3` et ajouter `"ref": "refs/<id>.mp3"` à la phrase dans `phrases.json`.

## Limites
- La note mesure si la machine reconnaît les mots, pas l'accent.
- Modèle entraîné surtout sur Brezhoweb, Dizale, Common Voice : le breton standard est mieux reconnu que certains parlers locaux.
- Licence du modèle non précisée par son auteur ; à confirmer avant une diffusion publique large.
