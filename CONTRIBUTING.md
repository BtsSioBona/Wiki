## Formatage des noms de fichiers
Les fichiers et dossiers doivent respecter un format assez précis :
* Pas d'espace dans les noms de dossiers et fichiers
* Pas de caractère spéciaux dans les noms de dossiers et fichiers
* Les espaces pour les noms de fichiers et dossiers doivent être remplacé par des "_"

**Bon :**

* 01_Getting_Started.md = Getting Started
* API_Calls.md = API Calls
* 200_Something_Else-Cool.md = Something Else-Cool
* _5_Ways_to_Be_Happy.md = 5 Ways To Be Happy

**Mauvais :**

* File Name With Space.md = Mauvais

## Sorting

Pour organiser les fichiers et dossiers dans un ordre spécifique, il suffit de les préfixer avec un chiffre et un underscore.  
Exemple :  `/docs/01_Hello_World.md` et `/docs/05_Features.md` vont donner *Hello World* avant *Features*, en outrepassant le triage par défaut (alphanumérique).  
Il est possible d'échappé le chiffre en début de fichier. Pour le fichier `6 Ways to Get Rich`, vous pouvez entrer `/docs/_6_Ways_to_Get_Rich.md`

