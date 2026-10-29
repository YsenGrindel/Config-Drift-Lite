# Config Drift Lite

**🇫🇷 Français** · 🇬🇧 [English](README.en.md)

Application de bureau open source pour **comparer deux instantanés de configurations** et repérer ce qui a changé.

> **Prototype v0.1** — lecture seule, hors ligne, et sans collecte réseau. Les résultats indiquent des changements, pas nécessairement la cause d'une panne.

## Fonctionnalités

- Comparaison de deux dossiers de fichiers texte exportés.
- Affichage des fichiers **ajoutés, supprimés, modifiés ou identiques**.
- Différences ligne par ligne dans une interface graphique.
- Export **HTML local**, avec échappement des caractères HTML.
- Mode ligne de commande, interface FR/EN, exemples fictifs.
- Exclusion prudente de certaines clés et noms de fichiers sensibles (sans garantie de détection).

## Démarrer

Prérequis : Python **3.10+** et Tkinter (habituellement fourni avec Python Windows ; paquet `python3-tk` sur certaines distributions Linux).

```powershell
py app.py
```

Depuis un terminal Python compatible sur Linux/macOS :

```bash
python3 app.py
```

Pour l'interface en anglais : `py app.py --lang en`.

### Essayer sans configuration réelle

```powershell
py app.py --before examples/before --after examples/after --report drift-report.html
```

Le rapport est écrit localement ; il peut révéler des éléments présents dans les fichiers source. Les exemples utilisent des adresses de documentation.

## Précautions

- L'application **ne modifie pas les configurations** ; seul l'export écrit un fichier.
- Elle **n'envoie pas de données sur Internet**.
- Les exclusions par noms ne détectent **pas tous les secrets** : examine toujours un rapport avant de le partager.
- Ne charge pas de données de production, de stage ou de client sans autorisation.
- Limites : UTF-8, 1 Mo par fichier, 2 000 fichiers maximum par dossier.
- Ne compare pas (encore) directement une machine Windows, un switch ou un pare-feu.
- Ce projet n'est **pas encore un installateur Windows signé**.

## Tests

```bash
python -m unittest discover -s tests -v
```

## Feuille de route

Comparaison sémantique JSON/INI, suppression du bruit (timestamps), profils Cisco/Windows/FortiGate, classification des différences et application Windows empaquetée.

## Licence

[MIT](LICENSE). Contribution : issues et pull requests bienvenues ; ne jamais publier de secrets.
