# Procedure recherche strings.xml
- lancer la commande
```shell
find app_src -name "strings.xml" -exec grep -HniE "key|api|token|secret|password" {} \;
```
![resultat](Story5.png)

- Les Strings obtenues ont été résumées dans le fichier : 
![strings_findings](strings_findings.md)
