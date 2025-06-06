# Documentation: Bot Discord "Faunaria" - Version 1.4

## Présentation Générale

Le Bot "Faunaria" est un Tamagotchi de serveur Discord permettant aux membres d'une communauté de cultiver et entretenir ensemble un jardin virtuel. Les utilisateurs peuvent planter différentes variétés de plantes, les arroser régulièrement, et gagner des points et des badges au fur et à mesure de leur progression.

## Fonctionnalités

### Système de Plantes

Le bot propose 5 types de plantes avec des caractéristiques différentes:

| Plante | Temps de croissance | Besoin en eau | Points | Rareté |
|--------|---------------------|---------------|--------|--------|
| Tournesol | 3 jours | 2 fois/jour | 50 | Commun |
| Cactus | 7 jours | 1 fois/jour | 75 | Peu commun |
| Rose | 5 jours | 1 fois/jour | 100 | Peu commun |
| Bonsaï | 14 jours | 1 fois/jour | 300 | Rare |
| Orchidée | 21 jours | 1 fois/jour | 500 | Très rare |
| Plante Draconique | 30 jours | 3 fois/jour | 1000 | Légendaire |
| Fleur de Lune | 40 jours | 4 fois/jour | 1400 | Légendaire |

### Système de Badges

Les utilisateurs peuvent obtenir des badges pour récompenser leurs accomplissements:

| Badge | Description | Condition d'obtention |
|-------|-------------|----------------------|
| Jardinier Débutant | A fait pousser sa première plante | Cultivé au moins 1 plante |
| Maître Arroseur | A arrosé 50 fois les plantes du serveur | Arrosé 50 fois |
| Botaniste | A fait pousser 5 plantes différentes | Cultivé 5 types de plantes différentes |
| Jardinier Légendaire | A fait pousser une plante légendaire | Cultivé une Plante Draconique ou une Fleur de Lune |

### Système de Progression du Serveur

Le serveur gagne des points lorsque les plantes arrivent à maturité. Ces points permettent de débloquer de nouvelles plantes:

| Jalon | Récompense |
|-------|------------|
| 500 points | Déblocage du Bonsaï |
| 2000 points | Déblocage de l'Orchidée |
| 5000 points | Déblocage de la Plante Draconique |
| 7000 points | Déblocage de la Fleur de Lune |

### Gestion des Limites de Plantes

- Limite absolue de 50 plantes par serveur
- Limite par défaut de 20 plantes par serveur
- Les administrateurs peuvent ajuster cette limite (jusqu'à 50)

## Commandes du Bot

Toutes les commandes commencent par le préfixe `!jardin`.

### Commandes Générales

| Commande | Description | Exemple |
|----------|-------------|---------|
| `aide` ou `help` | Affiche la liste des commandes disponibles | `!jardin aide` |
| `configurer` ou `config` | Configure le canal pour les notifications (requiert permission "Gérer le serveur") | `!jardin configurer` |
| `status` ou `état` | Affiche l'état du jardin du serveur | `!jardin status` |
| `profil` ou `profile` | Affiche le profil de jardinier de l'utilisateur | `!jardin profil` |
| `notifs` ou `notifications` | Active/désactive les notifications d'arrosage | `!jardin notifs` |
| `statuscanaux` ou `statuschannels` | Configure les canaux de statut pour les informations du jardin | `!jardin statuscanaux activer` |
| `limite` ou `limit` | Définit la limite de plantes du serveur | `!jardin limite 30` |

### Commandes de Jardinage

| Commande | Description | Exemple |
|----------|-------------|---------|
| `planter [type]` ou `plant [type]` | Plante une graine dans le jardin | `!jardin planter tournesol` |
| `arroser` ou `water` | Arrose les plantes qui en ont besoin | `!jardin arroser` |

## Système d'Événements

### Tâches Planifiées

Le bot exécute deux tâches planifiées:

1. **Mise à jour de l'état des plantes**: Toutes les heures, le bot vérifie l'état de chaque plante, met à jour leur progression, et détermine si elles ont besoin d'eau ou si elles sont mortes par manque d'arrosage.

2. **Rappels d'arrosage**: Tous les jours à 10h et lorsqu'une plante en a besoin, le bot envoie des rappels par message privé aux utilisateurs qui ont activé les notifications si des plantes ont besoin d'eau.

### Événements Spéciaux

Le bot envoie des messages dans le canal configuré lors des événements suivants:

- Une plante arrive à maturité
- Une plante meurt par manque d'eau
- Un jalon de serveur est atteint
- Un utilisateur obtient un nouveau badge

## Support et Contribution

Pour obtenir de l'aide ou contribuer au développement du bot, veuillez:
- Ouvrir une issue sur le repository GitHub
- Contacter @soleil-des-chats pour des questions spécifiques

---

© 2025 Faunaria v1.4 - Créé avec 💚 pour les communautés Discord
