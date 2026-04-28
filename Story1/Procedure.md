# Procédure Téléchargement et Vérification du Hash app.apk

## Téléchargement
- Cliquer sur le lien partagé par le PO
- Télécharger l'apk

## Vérification du hash
Sur Windows :
- Ouvrir Powershell dans le dossier ou se situe l'apk
- Lancer la commande 
```Powershell
Get-FileHash app.apk -Algorithm SHA256
```
- Résultat : F01F08C8B6E2FE4612E81BC7E3A3BA9440DAD0D7A962F4E67640390DD721D528
- Sur Virutotal rentrer le hash obtenu
