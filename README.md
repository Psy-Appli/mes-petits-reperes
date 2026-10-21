# Mes petits repères 🌿

**Prototype de journal personnel d’humeur et d’activités, conçu pour une utilisation sur smartphone.**

> Observer son quotidien avec curiosité, sans avoir à réussir quoi que ce soit.

## À quoi sert ce projet ?

Ce journal permet de noter librement ses émotions, les contextes associés, quelques activités, le plaisir et la satisfaction ressentis, ainsi que ce qui pourrait faire du bien dans l’instant. Il ne mesure ni la performance ni l’assiduité : une journée peut rester vide.

Le projet est pensé comme un **support personnel de réflexion**, susceptible d’être montré ou partagé volontairement à l’occasion d’un entretien. Ce n’est ni un dispositif de surveillance, ni un outil d’urgence.

## Fonctions

- **Mon jour** : observations quotidiennes facultatives.
- **Ma semaine** : consultation des journées renseignées.
- **Ma séance** : choix d’une période et des journées à partager, deux questions facultatives, aperçu du bilan.
- **Bilan protégé (`.mpr`)** : export chiffré, à transmettre *manuellement*, avec phrase secrète communiquée par un autre canal. La lecture se fait dans l’application, via « Lire un bilan reçu ».
- **Sauvegarde protégée (`.mprb`)** : export et réimport d’une copie chiffrée de toutes les journées.
- **Installation sur l’écran d’accueil** et fonctionnement hors ligne après chargement des fichiers nécessaires.

## Installation

Ouvrir l’adresse GitHub Pages de ce dépôt dans le navigateur du téléphone, puis choisir **« Installer l’application »** ou **« Ajouter à l’écran d’accueil »** selon le navigateur. L’installation et les fonctionnalités de base ne nécessitent pas de compte patient ni d’abonnement.

Pour publier ou mettre à jour le site : conserver `index.html`, `manifest.webmanifest`, `service-worker.js`, `icon-192.png` et `icon-512.png` à la racine du dépôt ; publier la branche choisie avec GitHub Pages. Après une mise à jour, rouvrir l’application pour charger la nouvelle version. **Ne pas effacer les données du site** sans sauvegarde préalable.

## Où vont les données ?

- Les observations quotidiennes sont conservées **dans le stockage local du navigateur, sur l’appareil utilisé**. Elles **ne sont pas chiffrées au repos par l’application** et ne se synchronisent pas entre appareils.
- Le code actuel n’envoie pas automatiquement le journal à un professionnel ou à un serveur. La politique de sécurité du navigateur limite les connexions initiées par la page ; les fichiers de l’application sont néanmoins chargés depuis l’hébergement GitHub Pages, dont l’opérateur peut disposer de journaux techniques de connexion.
- Les exports `.mpr` et `.mprb` sont chiffrés côté appareil avec **AES-256-GCM**, à partir d’une phrase secrète via **PBKDF2-SHA-256**. Ne jamais transmettre la phrase secrète dans le même mail que le fichier.
- La perte de l’appareil, un effacement du stockage du navigateur ou un changement de navigateur peut entraîner la perte des journées en l’absence de sauvegarde.
- Les anciens exports `.json` non chiffrés peuvent être importés pour compatibilité : ils ne doivent pas être utilisés pour des données sensibles.

## Précautions de sécurité

**Statut : prototype expérimental, testé avec des données fictives uniquement.** Le projet n’a pas fait l’objet d’un audit indépendant ni d’une validation réglementaire pour un usage clinique avec des données réelles de psychothérapie. Ne pas le considérer comme un dispositif médical ou comme une solution dont la conformité RGPD/HDS aurait été établie.

Pour les essais : utiliser un appareil personnel verrouillé, ne pas saisir d’informations identifiantes sur des tiers, protéger les sauvegardes, et ne jamais déposer de bilans, sauvegardes ou phrases secrètes dans ce dépôt public. Vérifier les obligations applicables avant tout usage professionnel réel.

La sécurité du contenu reçu par mail dépend également du transport, du stockage de la messagerie et de la gestion de la phrase secrète. Les pièces jointes déchiffrées ou les PDF imprimés depuis le lecteur ne sont **pas** automatiquement protégés.

## Maintenance

Le dépôt héberge le **code de l’application**, pas les journées personnelles. Protéger le compte GitHub par authentification à deux facteurs. Avant une mise à jour, conserver une copie du code opérationnel et une sauvegarde chiffrée de test ; contrôler ensuite la saisie, l’export, l’import, le bilan et le fonctionnement hors ligne.

**Point technique important :** la politique de sécurité du navigateur (CSP) contient des empreintes (`hash`) de scripts. Modifier ces scripts sans mettre à jour leurs empreintes peut empêcher l’application de fonctionner.

## Licence et contributions

Aucune licence de réutilisation ou de distribution n’a encore été définie. Le dépôt public rend le code consultable, mais ne lui attribue pas automatiquement une licence libre. Les contributions et modifications doivent être examinées avant publication, compte tenu du contexte sensible du projet.
