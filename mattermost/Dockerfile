FROM mattermost/mattermost-team-edition:7.1.3

USER root
RUN apt-get update && apt-get install -y jq && \
    rm -rf /var/lib/apt/lists/*
RUN for i in /mattermost/client/i18n/*.json; do jq '."login.gitlab"="Espace Membre Élèfàn"' $i > $i.tmp && mv $i.tmp $i; done
RUN for i in /mattermost/client/i18n/fr*.json; do jq '."web.root.signup_info"= "Toute la communication de l Élèfàn au même endroit, accessible de partout. Se connecter via le bouton Compte Élèfàn ci-dessous."' $i > $i.tmp && mv $i.tmp $i; done

USER mattermost
