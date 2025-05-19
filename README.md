# Agent IA de Recherche de Missions Freelance UX/UI

Ce workflow n8n vous aide à trouver des opportunités freelance en tant que directeur artistique UX/UI.

## Fonctionnalités

- Recherche automatique quotidienne d'offres sur plusieurs plateformes :
  - Freelancer.com
  - Malt
  - Welcome to the Jungle
  - Upwork
- Filtrage des offres selon les mots-clés UX, UI et Art Director
- Notifications via Slack et WhatsApp des nouvelles opportunités avec indication de la source

## Configuration requise

1. Une instance n8n installée
2. Les variables d'environnement suivantes :
   - `SLACK_CHANNEL` : ID du canal Slack où envoyer les notifications
   - `WHATSAPP_NUMBER` : Numéro de téléphone WhatsApp pour les notifications (format international, ex: +33612345678)

## Installation

1. Importez le fichier `workflow.json` dans votre instance n8n
2. Configurez les variables d'environnement dans les paramètres n8n
3. Configurez les connexions Slack et WhatsApp dans n8n
4. Activez le workflow

## Configuration de Slack

1. **Créer une application Slack** :
   - Allez sur https://api.slack.com/apps
   - Cliquez sur "Create New App"
   - Choisissez "From scratch"
   - Nommez votre application (ex: "Freelance Job Bot")
   - Sélectionnez votre espace de travail

2. **Configurer les permissions** :
   - Dans "OAuth & Permissions", ajoutez :
     - `chat:write`
     - `chat:write.public`

3. **Installer l'application** :
   - Dans "OAuth & Permissions", cliquez sur "Install to Workspace"
   - Autorisez l'application

4. **Obtenir le token** :
   - Copiez le "Bot User OAuth Token" (commence par `xoxb-`)

5. **Dans n8n** :
   - Ajoutez une nouvelle credential de type "Slack"
   - Collez le token
   - Nommez la credential (ex: "Slack Job Bot")

6. **Configurer le canal** :
   - Créez un canal dans Slack ou utilisez un existant
   - Invitez le bot avec `/invite @NomDeVotreBot`
   - Copiez l'ID du canal (clic droit > "Copier le lien")

7. **Dans le workflow** :
   - Ajoutez la variable `SLACK_CHANNEL` avec l'ID du canal

## Personnalisation

Vous pouvez modifier :
- La fréquence de recherche en ajustant le nœud "Schedule Trigger"
- Les critères de recherche en ajustant les conditions dans le nœud "Filter Jobs". Les mots-clés actuels sont :
  - UX
  - UI
  - Art Director

## Support

Pour toute question ou assistance, n'hésitez pas à ouvrir une issue sur ce repository. 