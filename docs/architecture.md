# Cahier des Charges - Site Communautaire JDR

## 1. Objectifs

Créer un site communautaire permettant :

- La gestion des campagnes de jeu de rôle.
- La gestion des disponibilités des membres.
- La planification automatique des parties.
- La communication avec les fans.
- La centralisation des contenus YouTube et Twitch.
- La gestion des commentaires et de la communauté.

Le projet servira également de démonstration de compétences de développement logiciel via :

- Une architecture propre.
- Des tests automatisés.
- Une documentation technique.
- Des pratiques modernes de développement.

---

# 2. Gestion des utilisateurs

## Visiteur

Peut :

- Consulter les campagnes.
- Consulter les news.
- Consulter les prochaines parties.
- Consulter les profils publics.
- S'inscrire.

---

## Fan

Inscription publique.

Informations :

- Pseudo
- Email
- Mot de passe
- Avatar

Peut :

- Commenter.
- Gérer son profil.
- S'abonner aux campagnes.
- Recevoir des notifications.
- Consulter les campagnes.
- Consulter les parties validées.

Ne peut pas :

- Participer à la planification.
- Voir les disponibilités de l'équipe.

---

## Équipe

Attribué uniquement par un administrateur.

Peut :

- Tout ce qu'un fan peut faire.
- Participer à une ou plusieurs campagnes.
- Déclarer ses disponibilités.
- Déclarer ses indisponibilités.
- Voter sur les propositions de dates.
- Annuler sa présence.
- Consulter son lien Video Ninja.

---

## Administrateur

Peut :

- Gérer les utilisateurs.
- Gérer les campagnes.
- Gérer les playlists.
- Gérer les news.
- Gérer les commentaires.
- Gérer les notifications.
- Gérer les paramètres du site.
- Gérer les liens Video Ninja.
- Consulter les statistiques.
- Consulter les journaux d'activité.

---

# 3. Campagnes

Chaque campagne possède :

- Nom
- Description
- Bannière
- Statut (active / archivée)
- Membres
- Playlists YouTube
- Sessions

## Membres d'une campagne

Un membre peut être :

- MJ
- Joueur

Une campagne peut avoir :

- Plusieurs MJ
- Plusieurs joueurs

## Playlists

Une campagne peut posséder :

- Aucune playlist
- Une playlist
- Plusieurs playlists

Exemple :

```text
Oblivion
├── Saison 1
├── Saison 2
└── Saison 3
```

Chaque playlist est liée à une saison.

---

# 4. Planning

## Disponibilités

Les membres peuvent :

- Proposer des dates.
- Indiquer leurs disponibilités.
- Indiquer leurs indisponibilités.

Aucune justification n'est demandée.

## Validation automatique

Lorsqu'une date réunit les conditions nécessaires :

- La session est automatiquement validée.
- Elle est ajoutée au planning public.
- Les notifications sont générées.

## États d'une session

```text
proposed
confirmed
cancelled
completed
```

## Annulation

Après validation :

- Un membre peut retirer sa disponibilité.
- La session peut être annulée.
- La session est mise à jour automatiquement.

## Historique

Les visiteurs peuvent consulter :

- Les prochaines parties.
- Les parties passées.

---

# 5. Notifications

## Équipe

- Session validée.
- Rappel le matin de la partie.

## Fans

- Nouvelle session validée.
- Rappel 2 heures avant la partie.

Abonnement facultatif par campagne.

## News

Abonnement facultatif :

- Réception d'un email lors de la publication d'une news.

## Gestion technique

Toutes les notifications passent par une file d'attente.

---

# 6. Video Ninja

Chaque membre possède :

- Un lien Video Ninja unique.

Le lien est :

- Généré automatiquement.
- Modifiable par l'administrateur.

Le lien est associé à l'utilisateur et non à une campagne.

---

# 7. Accueil

## Bloc Live

Affichage automatique :

- Live Twitch en cours.
- Live YouTube en cours.

Si aucun live n'est actif :

- Bloc masqué.

## News

Affichage des dernières actualités.

## Dernière vidéo YouTube

Affichage automatique de la dernière vidéo publiée.

## Prochaines parties

Affichage des sessions validées.

## Pied de page

Liens :

- Twitch
- YouTube

---

# 8. Page campagne

Contient :

- Bannière
- Description
- Équipe
- Playlists
- Prochaines parties
- Historique
- Commentaires

---

# 9. Page équipe

Contient :

- Avatar
- Pseudo
- Présentation
- Liens personnels

Liens possibles :

- YouTube
- Twitch

---

# 10. Commentaires

Tous les utilisateurs connectés peuvent commenter :

- Fan
- Équipe
- Admin

## Modération

### Équipe

Peut :

- Masquer un commentaire

### Admin

Peut :

- Masquer
- Restaurer
- Supprimer définitivement

---

# 11. News

Par défaut :

- Publication réservée aux administrateurs.

Option configurable dans le back-office :

```text
Autoriser la publication des news par l'équipe
```

Lorsque cette option est activée :

- Les membres de l'équipe peuvent publier des news.

---

# 12. Tableau de bord administrateur

Statistiques :

- Nombre de comptes.
- Nombre de fans.
- Nombre de membres.
- Campagnes actives.
- Campagnes archivées.
- Prochaines sessions.
- Sessions réalisées.
- Commentaires masqués.
- Abonnements aux notifications.

---

# 13. Journal d'activité

Historisation des événements importants :

- Création d'utilisateur.
- Promotion fan → équipe.
- Création campagne.
- Modification campagne.
- Validation session.
- Annulation session.
- Publication news.
- Masquage commentaire.
- Suppression commentaire.
- Modification paramètres.

---

# 14. Paramètres du site

Configuration depuis le back-office :

- Nom du site.
- Description.
- Chaîne Twitch.
- Chaîne YouTube.
- Discord.
- Email de contact.
- Activation publication news par l'équipe.
- Paramètres de notifications.

---

# 15. RGPD

Le site doit permettre :

- Modification du profil.
- Suppression du compte.
- Export des données utilisateur.
- Consentement lors de l'inscription.

Les mots de passe doivent être chiffrés.

---

# 16. Qualité logicielle

Le projet doit inclure :

- Documentation technique.
- Documentation d'installation.
- Documentation API.
- Tests automatisés.
- Gestion des permissions.
- Journalisation.
- Gestion des erreurs.
- Docker.
- GitHub Actions.
- Couverture de tests sur les règles métier principales.

---

# 17. Stack technique cible

## Frontend

- React
- TypeScript
- Vite
- TailwindCSS

## Backend

- Node.js
- Express
- TypeScript

## Base de données

- PostgreSQL

## ORM

- Prisma

## Authentification

- JWT
- bcrypt

## Emails

- Nodemailer

## Tests

- Vitest

## Qualité

- ESLint
- Prettier

## DevOps

- Docker
- Docker Compose
- GitHub Actions
