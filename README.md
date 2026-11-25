# Pokou, coach de prononciation bretonne

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
Le micro exige une adresse HTTPS (ou localhost). Publié avec GitHub Pages : https://periggouanvic.github.io/Pokou/
Test local : `python3 -m http.server 8000`, puis http://localhost:8000

## Apprendre
Onglet « Apprendre » : cartes de vocabulaire avec répétition espacée (boîtes de Leitner), par profil.
Exercices : découverte, écouter et trouver le sens, lire et trouver le sens, choisir la phrase bretonne,
et « dis-le en breton » noté par le coach. Chaque profil (« Qui apprend ? ») a sa progression et ses étoiles.

## Voix de référence
- Plusieurs voix par phrase : chaque proche reçoit un lien à son nom, `…/Pokou/#voix=Nom` (`#maman` reste valable).
  Il peut aussi ajouter ses propres mots et phrases ; le texte, la traduction et le nom de la voix voyagent dans le fichier WAV.
- Depuis chez elle : la personne modèle ouvre https://periggouanvic.github.io/Pokou/#maman, enregistre les phrases et touche « Envoyer mes enregistrements » (partage Android : courriel, WhatsApp…). Les fichiers WAV portent l'identifiant de la phrase ; on les importe dans « Enregistrer la voix de référence > Importer les fichiers reçus ».
- Dans l'appli : « Enregistrer la voix de référence » (stocké sur l'appareil).
- Ou pour tous les appareils : déposer `refs/<id>.mp3` et ajouter `"ref": "refs/<id>.mp3"` à la phrase dans `phrases.json`.

## Voix libres
Onglet « Prononcer » et nouvelles cartes : chaque mot de la phrase se touche pour entendre un enregistrement
Lingua Libre (fichiers « LL-Q12107 (bre)-Locuteur-mot.wav » sur Wikimedia Commons), cherché à la volée par l'API Commons.
L'auteur et la licence de l'enregistrement joué s'affichent, avec un lien vers la page du fichier.

## Limites
- La note mesure si la machine reconnaît les mots, pas l'accent.
- Modèle entraîné surtout sur Brezhoweb, Dizale, Common Voice : le breton standard est mieux reconnu que certains parlers locaux.
- Licence du modèle non précisée par son auteur ; à confirmer avant une diffusion publique large.
