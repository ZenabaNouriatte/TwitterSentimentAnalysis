
# Projet d'Analyse de Sentiment des Tweets sur les JO 2024 :  Exploration des Opinions des Utilisateurs de Twitter
 

Le compte à rebours est lancé, J-410 jours avant le coup d'envoi des Jeux Olympiques 2024, qui se tiendront à Paris. 

Une question se pose à moi : 

__Quel est le sentiment des Français au sujet des Jeux Olympiques 2024 à Paris ?__ 

À travers ce projet, j'ai tenté de répondre à cette question grâce à l'extraction, l'analyse et la visualisation de données. 

Cette analyse a pour objectif de comprendre les sentiments généraux et les opinions des utilisateurs de Twitter concernant les JO 2024, d'identifier les tendances positives, négatives et neutres associées à cet événement sportif mondial. Elle est automatisée et ne requiert pas d'action humaine pour identifier les sentiments à travers les tweets, grâce au machine learning.


## Processus d'analyse de données


*L'extraction des données selon les hashtags identifiés*

Les données à utiliser sont les tweets des utilisateurs de Twitter qui concernent le sujet des Jeux Olympiques. 

Pour extraire ces données, j'ai utilisé snscrape, une bibliothèque de Python permettant la recherche et la récupération de tweets sans limitation.
J'ai souhaité récupérer les tweets à partir de la date d'annonce des JO de Paris, le 13 septembre 2017, jusqu'au 05 juin 2023. 

Les hashtags identifiés étaient les suivants : #JO2024 - #JeuxOlympiques - #jeuxolympiques - #PARIS2024 - #Paris2024 - #JO - #jo - jeux olympiques 
Les informations extraites comprenaient l'URL du tweet, l'utilisateur, la vérification du compte, la source, la localisation, la langue, le contenu du tweet, le nombre de likes, de retweets, de citations et de réponses.



Les données collectées ont ensuite été nettoyées afin d'éliminer les valeurs manquantes et les variables inutiles. 
La variable "Localisation" a subi plusieurs modifications :
Les emojis (notamment les drapeaux) ont été supprimés.
Les valeurs manquantes ont été remplacées par "No Location".
Les localisations contenant les termes "Paris" ou "75" ont été remplacées par "Paris, France".
Les localisations faisant référence aux grandes villes de France ont été remplacées par "France".
Les localisations ne contenant ni "Paris", ni "75", ni "France", ni le nom d'une grande ville de France ont été remplacées par "Other".

*Récupération des hashtags*

Pour analyser les hashtags les plus utilisés et leur fréquence, les hashtags ont été extraits de la variable "Tweets" et ajoutés à une nouvelle variable appelée "Hashtags" dans le dataframe. Les valeurs vides ont été remplacées par "No Hashtag used". Un autre dataframe a été créé pour stocker les hashtags distincts et le nombre de fois où ils ont été utilisés.
df_tweets après nettoayage

## Analyse de sentiments

L'analyse de sentiment consiste à évaluer les opinions, émotions et attitudes exprimées dans un texte afin de déterminer si elles sont positives, négatives ou neutres. 
Elle permet de comprendre les sentiments du public, d'évaluer la réputation d'une marque, de détecter les tendances émergentes et de guider les décisions.

Avant de procéder à l'analyse de sentiment, les données sont préparées. Dans ce projet, le prétraitement a été réalisé sur la variable "Tweets" en appliquant différentes actions à l'aide d'une fonction : suppression des caractères spéciaux, de la ponctuation, des emojis, tokenisation, lemmatisation, suppression des chiffres, des mots vides et des liens. Les tweets ainsi traités sont stockés dans une variable appelée "data_clean".
Pipeline pré-processingDans ce projet, l'analyse de sentiment a été réalisée en utilisant la librairie Textblob. 
La variable "data_clean" a été traitée par une pipeline NLP qui a extrait la polarité du sentiment de chaque tweet et déterminé le sentiment global associé à chaque tweet (positif, négatif ou neutre).

Dans cette approche, les tweets avec une polarité supérieure à 0 sont considérés comme positifs, ceux avec une polarité inférieure à 0 sont considérés comme négatifs, et les tweets avec une polarité égale à 0 correspondent à un sentiment neutre.
La distribution de la variable "Sentiment" est la suivante :


*Worcloud*. 

Son utilité est de représenter graphiquement les mots les plus fréquents dans un texte : 


Wordcloud à partir des tweets


## Visualisation grâce à Power BI. 

Après avoir recueilli les données puis les avoir modélisées, nous pouvons désormais les visualiser. 
Pour cela, j'ai choisi Power BI, un outil puissant et populaire pour la visualisation des données. 

Voici le dashboard réalisé :

Dashboard de l'analyse de sentiments

## Insights 

Les données nous apprennent que : 
* Les sentiments des utilisateurs de Twitter sont en majorité (49%) positifs à l'égard des JO 2024. 18% des tweets sont négatifs et 33% sont neutres.
* La plupart des tweets n'ont pas de localisation, mais 12% proviennent de Paris, 22% proviennent de France et 29% d'autres localisations
* 17% des tweets sont positifs et proviennent de France, 15% sont positifs et proviennent d'autres localisations
* 5% des tweets sont négatifs et proviennent de France, 2%sont positifs et proviennent d'autres localisations
* Suites aux annonces récentes ( prix, recrutement de bénévoles) entre mars et mai 2023, ces actualités ont fait augmenter le nombre de tweets au sujet des JO, néanmoins, malgré une augmentation des tweets au sentiments négatifs à ce moment-là, les sentiments positifs restent majoritaires.

## Conclusion

Les résultats de ce projet indiquent un accueil favorable de la population à l'égard des Jeux Olympiques 2024. Avec une majorité de sentiments positifs exprimés dans les tweets analysés, il semble que les utilisateurs de Twitter aient une attitude positive et enthousiaste envers cet événement sportif majeur à venir. Cela suggère un fort intérêt et un soutien de la part du public.
Vous pouvez retrouver la totalité du projet sur mon profil Github : code et rapport plus approfondi du projet.

Zenaba MOGNE

![LinkdIn](https://www.linkedin.com/in/zenaba-mogne/)

![Portfolio](https://zenabamogne.carrd.co/)
