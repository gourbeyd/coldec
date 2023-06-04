# Notes coldec 

## contexte 

- collecte des bacs de déchets (2 à 10 par pts) dans des pts de collecte (~ 250, peut monter vite) à des clients  
- pts de collecte dans sté-métropole avec camion de capacité 20 bacs     
- collecte périodique (~1fois par semaine/mois) (FREQUENCE VARIABLE JUSQU'A (clients fonctionnent à l'appel) selon les points)

l'entreprise doit

    1 - itinéraire
    effectuer des itinéraires (définis par journée) pour la collecte (le + logiquement/rapidement possible)
    intégrer les appels des clients "ponctuels" dans les itinéraires prévus

    2 - relation client/facturation
    rendre des comptes au client (poids des déchets collectés, nb de bacs, heure de la collecte, MATERIELS DEPOSES...)
    facturer aux clients en fonction des collectes

    3 - intégration personnel/évolution
    composer avec nveaux personnels qui ne connait pas les pts de colelcte (clefs, codes batiments, localisation précise)

solution actuelle:

    1- travail de planification (humain via connaissance des pts de collecte + gestion appels)
    2- google sheets / form + mail envoyé manuellement au client
    3- formation nveau personnel

## fonctionnalités envisagées

via plateforme (site internet + appli android/ios ?)

- accès liste des pts de collecte (visualisation carte & liste)

- création d'un itinéraire à partir de la carte

- possibilité d'affecter un itinéraire à un "collecteur"

- en parcourant un itinéraire, le collecteur 

    - rentre les infos (nb de bacs, poids, DEPOSER DU MATERIELS (CATEGORIE DE SACS, FUT, SUPPORT DE FUT, heure de passage(AUTOMATIQUE AVEC LE SHEET PR LE MOMENT), ...) pour chaque pt de collecte traité
    
    - a les infos nécessaires à la collecte pour chaque pt (loc précise, code d'accès,CONTRAINTE HORAIRE tips/notes à savoir)

    - a la fin de son parcours, si camion pas plein
        -> recherche de pts de collecte proche (DANS UN PETIT PERIMETRE et qui REPOND AU CONTRAINTE)

- chaque client a accès à un espace où il peut voir les infos de ses pts de collecte (HEURE DE COLLECTE, POIDS, MATERIELS DEPOSES)

- client peut requêter une collecte "ponctuelle" et la solution indique en cb de tps la collecte est possible (DANS L'IDEE UN APPEL LE MATIN COLLECTE DANS LES 48H - UN APREM OU FIN DE SEMAINE DANS LES 72H)

- génération des factures à partir des données des collectes - POUR LE MOMENT RENE FONCTIONNE AVEC LE SHEET QUE JE TAI ENVOYe SUR MESSENGER - IL PREND CODE CLIENT ET GENERE UNE FACTURE DE CELUI-CI)

- gestion de la périodicité (ou non) des pts de collecte et ajout dynamique aux itinéraires

## organisation de la solution

différents espaces

### espace "administration"

- gestion des pts de collecte
    - ajout/suppression/modification

- gestion des itinéraires
    - création/modification/suppression à partir d'une carte
    - création/modification "automatique" ? 
        -> AStar ou dijkstra avec coût = temps de trajet gmap/waze

- génération de rapport/facture

### espace client

- visualisation des infos sur les collectes des pts qui lui appartiennent
- requête d'une collecte ponctuelel
- AFFICHAGE DE L'ORGANIGRAMME DE L'EQUIPE ET NUMERO DE TEL / MAIL EN FONCTION DES PERSONNES QUILS ONT AUSSI BESOIN DE JOINDRE

### espace collecteur
    
- visualisation des itinéraires à parcourir  
        point sur carte

- accès aux infos de chaque pt de collecte
- saisie des infos concernant la collecte
- recherche pt a proximité
    

## ébauche possible rapide (~1/2 mois)

version sans carte ni gestion des itinéraires automatique

- espace admin 

    - gestion pts de collecte
    - ajout itinéraire "manuel" 

- espace collecteur 

    - vue des itinéraires qui lui sont affectés
    - vue sans carte des pts de collecte (infos sur chaque pt)
    - saisie des infos de collecte quand il fait l'itinéraire

- espace client
    - vue des informations relatives à la collecte de ses points


## évaluation tps projet complet/coût 

### temps 

version simplifiée faisable en 1/2 mois

la partie difficile du projet: la gestion des itinéraires si on veut faire ça avec un algo dynamiquement qui prendrait en compte la périodicité, les appels des clients pour les collectes "ponctuelles"


### cout de fabrication

à définir après les avis sur une ébauche/1ere version simplifiée ? 

### cout de fonctionnement  

- serveur pour héberger le site + stockage des infos 
     
    <1k€/an, même <200€ à mon avis mais soyons prudents j'ai peut etre pas tout en tête

- maintien en condition, gestion des bugs

    dur à définir à l'avance mais rien ne semble instable a priori
 

## questions 
    
- extrait de la sheet avec laquelle vous travaillez actuellement ? AUCUNE IDEE PR CA....
- comment se passe explication a un nveau "collecteur" ? DEMONSTRATION ET TEMPS DE FORMATION AVEC LUI MEME SI C'EST UN NOVICE
- raisonnable de penser que le collecteur a accès à internet tout au long de la collecte ? OUI JE PENSE AC LES TELEPHONES.....
- oubli et choses à ajouter ? 
