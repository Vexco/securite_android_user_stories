# Document de Recommandation MDM (`mdm_recommandation`)

## 1. Tableau Comparatif

| Critère d'évaluation | Headwind MDM (Open Source / Gratuit) | Microsoft Intune (Licence Commerciale) |
| :--- | :--- | :--- |
| **Modèle économique** | Gratuit (Version Community). Code source ouvert. | Payant (Abonnement mensuel / Inclus dans Microsoft 365 E3/E5). |
| **Hébergement & Souveraineté** | Auto-hébergé (On-Premise) sur vos propres serveurs. Maîtrise totale des données. | SaaS (Cloud Microsoft). Hébergement géré par l'éditeur. |
| **OS Supportés** | **Android exclusivement** (optimisé pour les flottes AOSP et terminaux durcis). | Multiplateforme : iOS, Android, Windows, macOS, ChromeOS, Linux. |
| **Fonctionnalités clés (MAM/MDM)** | Mode Kiosque (Lockdown), déploiement d'APK silencieux, géolocalisation, effacement à distance. Pas de MAM (profil de travail). | MDM complet + MAM (protection des apps sans gérer tout le téléphone). Intégration *Zero Trust*. |
| **Support Technique** | Communautaire (Forums, GitHub). Support payant disponible uniquement si passage à la version Enterprise. | Support éditeur inclus (Microsoft) avec SLA garanti (Service Level Agreement). |
| **Complexité de mise en œuvre** | Nécessite des compétences d'administration système (Linux, Tomcat, PostgreSQL) pour l'installation du serveur. | Déploiement rapide via le cloud, mais complexité liée à la richesse des règles d'Accès Conditionnel. |

---

## 2. Analyse Détaillée

### Les atouts de Headwind MDM (Open Source)
Headwind MDM est un excellent choix pour une **souveraineté totale des données**. Étant auto-hébergé, aucune donnée ne transite par des serveurs tiers. Il est particulièrement puissant pour créer des flottes de terminaux Android dédiés à une seule tâche (Mode Kiosque), par exemple pour des livreurs, des techniciens sur le terrain ou des bornes interactives. Le coût de licence est nul, seul le coût d'hébergement du serveur est à prévoir.

**Limites :** Il ne gère pas les appareils Apple (iOS) et ne propose pas nativement de conteneurisation fine pour le BYOD.

### Les atouts de Microsoft Intune (Licence)
Intune est le standard de l'industrie pour les entreprises modernes. Sa force réside dans la gestion hétérogène (iOS et Android) et surtout dans sa gestion du **BYOD**. Grâce à ses politiques de protection des applications (MAM), il permet de sécuriser les données de l'entreprise sur le téléphone personnel du collaborateur sans avoir à prendre le contrôle total de l'appareil, garantissant ainsi le respect de la vie privée.

**Limites :** Coût récurrent des licences (~8€ par mois par utilisateur) et dépendance au Cloud Microsoft.

---

## 3. Recommandations

Le choix entre une solution Open Source et une solution sous licence dépend de l'usage et de la composition de notre flotte :

**Recommandation 1 : Opter pour Microsoft Intune (Licence) si :**
* Notre flotte est mixte (employés avec des iPhones et des Androids).
* Nous autorisons le BYOD (les employés utilisent leur smartphone personnel pour lire leurs mails professionnels).
* Nous utilisons déjà la suite Microsoft 365, ce qui amortit immédiatement le coût des licences.

**Recommandation 2 : Opter pour Headwind MDM (Open Source) si :**
* Nous déployons **exclusivement des terminaux Android** (ex: flotte de PDA pour la logistique ou téléphones d'entreprise basiques).
* Notre politique de sécurité exige que le serveur MDM soit hébergé dans notre propre centre de données (On-Premise) pour des raisons de confidentialité stricte.
* Le budget logiciel (OpEx) est limité, mais nous disposons des compétences en interne pour maintenir un serveur Linux.
