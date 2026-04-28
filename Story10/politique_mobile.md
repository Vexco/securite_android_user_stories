# Politique de Sécurité des Applications Mobiles (PSAM)

**Version :** 1.0

## 1. Objectif et Périmètre

### 1.1 Objectif
Le but est d'encadrer le cycle de vie des applications mobiles au sein de l'organisation. Elle vise à garantir que :
* Les applications développées (en interne ou par des prestataires) respectent les standards de sécurité (Secure by Design).
* L'usage des applications mobiles professionnelles par les collaborateurs protège les données de l'entreprise contre les fuites, les vols et les compromissions.

### 1.2 Périmètre
Cette politique s'applique à :
* **Tous les collaborateurs** (employés, stagiaires, prestataires) utilisant des applications mobiles dans le cadre de leurs fonctions (sur flotte d'entreprise ou en BYOD).
* **Toutes les équipes de développement** (internes et externes) concevant des applications mobiles pour le compte de l'entreprise.

---

## 2. Encadrement du Développement (Secure by Design)

Toute application mobile développée pour l'entreprise doit respecter les standards de l'**OWASP Mobile Top 10**.

### 2.1 Stockage et Protection des Données
* **Chiffrement :** Toutes les données sensibles stockées localement sur l'appareil doivent être chiffrées (utilisation des API natives comme iOS Keychain ou Android Keystore).
* **Minimisation :** Ne stocker sur le terminal que les données strictement nécessaires au fonctionnement hors-ligne de l'application.
* **Données en transit :** Toutes les communications client-serveur doivent être chiffrées via TLS 1.3 minimum. Le *Certificate Pinning* est exigé pour les applications critiques.

### 2.2 Authentification et Gestion de Session
* L'authentification multifacteur (MFA) doit être implémentée pour l'accès aux données classifiées "Confidentiel" ou "Interne".
* Les sessions doivent avoir une durée de vie limitée et expirer automatiquement après une période d'inactivité définie (ex: 15 minutes).
* La validation biométrique locale (FaceID, TouchID) est recommandée pour déverrouiller l'accès à l'application après une authentification initiale réussie auprès du serveur.

### 2.3 Qualité et Intégrité du Code
* **Obfuscation :** Le code source des applications en production doit être obfusqué pour limiter les risques de rétro-ingénierie (Reverse Engineering).
* **Tests de Sécurité :** L'intégration de tests de sécurité statiques (SAST) et dynamiques (DAST) est obligatoire dans le pipeline CI/CD.
* **Pentest :** Un test d'intrusion externe est requis avant la mise en production de toute application traitant des données critiques ou financières.

---

## 3. Encadrement de l'Usage et du Déploiement

### 3.1 Gestion de Flotte et des Applications (MDM / MAM)
* **Flotte d'entreprise :** Les terminaux fournis par l'entreprise doivent être enrôlés dans la solution de Mobile Device Management (MDM).
* **BYOD (Bring Your Own Device) :** L'usage d'appareils personnels est soumis à l'acceptation de l'enrôlement dans une solution de Mobile Application Management (MAM), créant un conteneur hermétique (séparation stricte entre les données pro et perso).

### 3.2 Déploiement des Applications
* Les applications internes doivent être distribuées **exclusivement** via le magasin d'applications d'entreprise (Enterprise App Store).
* Le téléchargement d'applications professionnelles depuis des sources non officielles (sideloading) est strictement interdit.

### 3.3 Maintien en Condition de Sécurité (MCS)
* Les utilisateurs sont tenus d'accepter et d'installer les mises à jour du système d'exploitation et des applications professionnelles dans un délai maximum de **7 jours** après leur publication.
* L'utilisation d'appareils "Jailbreakés" (iOS) ou "Rootés" (Android) est formellement interdite. Les applications professionnelles doivent implémenter des mécanismes de détection de jailbreak/root et bloquer leur exécution le cas échéant.

---

## 4. Gestion des Incidents de Sécurité

En cas de perte, de vol du terminal mobile, ou de suspicion de compromission d'une application professionnelle :

1.  **Signalement :** L'utilisateur doit signaler l'incident au centre de services informatique (Helpdesk) dans les plus brefs délais (maximum 24h).
2.  **Révocation :** L'équipe sécurité procédera à la révocation immédiate des accès liés au terminal.
3.  **Effacement à distance :** * *Flotte d'entreprise :* Effacement total des données de l'appareil (Wipe).
    * *BYOD :* Effacement ciblé du conteneur professionnel (Corporate Wipe).

---

## 5. Sanctions et Conformité

Le non-respect de cette politique (ex: contournement des mesures de sécurité, refus d'installer les mises à jour critiques) peut entraîner la suspension immédiate des accès aux systèmes d'information de l'entreprise depuis le terminal mobile, et faire l'objet de sanctions disciplinaires conformément au règlement intérieur.

> **Validation du DoD :** politique_mobile livrée et prête à être communiquée aux équipes.