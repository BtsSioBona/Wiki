- Exemple de requête SQL :
```sql
##Sql
select codesemi, seminaire.codecour, libellecours
from seminaire inner join cours
      on seminaire.codecour = cours.codecours;
```

sous LinQ
```c#
//linq
var requete = from s in oracleContexte.SEMINAIREs
                              join COUR in oracleContexte.COURS on s.CODECOURS equals COUR.CODECOURS
                              select s;
```

- Méthode qui supprime les blancs inutiles en fin de chaîne.
```c#
TrimEnd();
```
- Retourne l'objet ou null s'il n'éxiste pas.
```c#
FirstOrDefault();
```
