# Aelyon - Mon Projet

## Sommaire

1. L'histoire, les objectifs
2. Le Problème avec l'IA actuelle
3. Les enjeux
4. Mon Projet
5. Un projet dificiles
6. Les apports en terme de compétences développées
7. Le Futur du projet
8. La Suite ...

## 1. L'histoire, les objectifs

Depuis la fin du lycée, j'ai toujours été attiré par le développement. À force de faire du développement web, j'ai cherché un autre domaine tout aussi intéressant et en vois d'amélioration. C'est là que j'ai découvert l'Intelligence Artificielle. Depuis ce moment, je me suis lancé un défi : comprendre, concevoir et créer tout ce qu'il est possible de faire avec cette technologie, sans juste consommer une API existante. Je me suis donné une marge de 3 ans, en me disant qu'au début de mon Bac +3, je devais avoir un projet aboutit !

J'ai décidé de lancer ce projet personnel dans un but pédagogique : comprendre comment ce monde fonctionne (celui de l'ia), manipuler et comprendre la data, la sécurité et la logique derrière son fonctionnement. J'ai pu me former en autodidacte grâce à des documentations techniques, des livres, nombreuses expérimentations et de vidéo expliquant le sujet.

C'est ainsi qu'est né l'idée du **Projet Aelyon**.

Aujourd'hui, un peu plus de 2 ans plus tard, je peux dire que j'ai réussi mon défi. Mon IA est en cour de phase de test et disponible en ligne via ce lien https://aelyon.digitalprojects.fr/, Si vous souhaitez un acces pour tester m'envoyer un message privée.

## 2. Le Problème avec l'IA actuelle

Depuis 2022, l'IA a pris une place considérable dans notre quotidien et celui des entreprises.

Malheureusement, aujourd'hui, nos moindres interactions sont souvent enregistrées pour en tirer le plus de données possible et améliorer les modèles propriétaires, sans que les utilisateurs soient toujours clairement informés de quelles données sont récoltées ni pourquoi. On assiste à une centralisation massive de l'intelligence.

## 3. Les enjeux

Aelyon répond à deux enjeux principaux que j'ai définis en me basant sur mon analyse du secteur :

1. **La Souveraineté et la Confidentialité :** L'utilisateur doit pouvoir choisir à 100% si sa conversation est stockée ou non. Il doit être garanti que ses données ne servent pas à entraîner d'autres modèles à son insu. **L'utilisateur est libre de son choix**.

2. **L'Évolution Personnelle :** Je ne voulais pas que ce projet soit "juste" une ligne sur un CV. Je voulais qu'il ait un impact réel. Nous avons évolué ensemble : l'IA a appris de mes données, et j'ai appris, grâce à elle, les architectures complexes.

## 4. Mon Projet

Ce projet ne s'est pas fait en un jour. Il a été fait grace a de l'apprentissage continue sur deux ans et un suivi des différents informations, que je peux découper en trois grandes phases techniques, transformant un simple fantasme en une application complexe.

### Phase 1 : Le Commencement et l'Exploration (2024)
Au tout début, mon objectif était simple : faire tourner une IA sur ma propre machine. Je pensais naïvement qu'il suffirait d'installer une bibliothèque Python et de lancer un script.

**La réalité technique :** J'ai commencé par utiliser des outils standards comme Hugging Face Transformers pour charger des modèles "bruts" (Pythia, GPT-Neo). C'est là que j'ai pris une claque technique. Un modèle de langage, c'est lourd (plusieurs gigaoctets), c'est excessivement lent en inférence, et ça demande une puissance de calcul (VRAM GPU) que je n'avais pas forcément sur un PC étudiant.

Mes premiers scripts étaient basiques : des lignes de commande qui prenaient une entrée texte et ressortaient une suite de mots, souvent incohérente ou s'arrêtant au milieu d'une phrase. C'était la phase de "tâtonnement", où j'ai dû apprendre tout le vocabulaire spécifique (tokens, inférence, température, top-k sampling) et comprendre que l'IA n'est pas magique : c'est des mathématiques probabilistes.

### Phase 2 : L'Architecture Logicielle et le Backend (2025)
Une fois que j'ai réussi à faire "parler" l'IA de manière cohérente, je voulais en faire un vrai produit utilisable, pas juste un script terminal pour développeur. C'est là que le vrai développement Full-Stack a commencé.

* **Création de l'API Serveur :** J'ai dû développer une API complète en Python en utilisant le framework **FastAPI**. Le but était de séparer totalement le "cerveau" (le moteur d'inférence deep learning) de l'interface utilisateur. Cela permet d'avoir un backend qui peut être interrogé par un site web, une application mobile, etc.
* **Le Système de "Routing Sémantique" :** J'ai vite réalisé qu'un seul modèle ne pouvait pas tout faire bien. Si je lui demandais du code Python complexe, le modèle "généraliste" était moyen. Si je lui demandais une histoire créative, le modèle "codeur" était terrible.
    * *L'innovation :* J'ai eu l'idée de créer un **Routeur**. C'est un morceau de code intelligent qui analyse ce que l'utilisateur demande avant même de répondre ("Est-ce du code ?", "Est-ce de la rédaction ?") et qui redirige la demande vers le "spécialiste" approprié (charge un modèle Llama-3 pour le texte, ou Phi-3 pour le code). C'est comme un chef d'orchestre invisible qui optimise la qualité des réponses.
* **Authentification et Sécurité :** Pour rendre le projet public, j'ai dû implémenter un système de sécurité solide. Pas question d'utiliser des solutions toutes faites sans comprendre, j'ai codé mon propre système de gestion d'utilisateurs et de tokens d'accès sécurisés (JWT Like) pour comprendre comment sécuriser une API critique en production.

### Phase 3 : La Data et l'Autonomie (2026)
C'est la partie la plus récente et la plus complexe, celle qui transforme l'outil en véritable assistants intelligent. Une IA dont les données d'entraînement s'arrêtent en 2023 ne sait pas ce qu'il s'est passé hier.

* **Le Collecteur Automatique (The Crawler) :** J'ai développé un agent autonome (un script Python qui tourne en permanence en tâche de fond) qui va lire des articles technologiques sur le web via des flux RSS et des API d'actualités.
* Il ne fait pas que lire : il "nettoie" le contenu (enlève les pubs, les menus, le bruit HTML) pour ne garder que l'information pure.
* **L'Apprentissage (Fine-Tuning) :** J'ai mis en place un pipeline de données (ETL) qui permet à l'IA d'apprendre de ses propres conversations passées. Les logs de discussion sont anonymisés, nettoyés, et convertis en "datasets d'entraînement". C'est une boucle d'amélioration continue : plus on l'utilise, plus elle devient pertinente sur mes sujets de prédilection.

## 5. Un projet difficiles

Derrière le résultat actuel se cachent des mois de résolution de problèmes complexes et de nuits blanches. Ce ne fut pas qu'une simple écriture de code, mais une lutte contre les contraintes techniques.

### Difficulté 1 : La Barrière du Matériel
C'est la première barrière majeure. Les modèles d'IA modernes d'OpenAI tournent sur des clusters de GPU H100 à 20 000€ l'unité. Je voulais faire la même chose sur un PC standard.
* **Le Problème :** Charger un modèle demandait 16 Go de mémoire vidéo. Mon PC plantait immédiatement ("CUDA Out of Memory").
* **La Solution Technique :** J'ai dû plonger dans l'optimisation bas niveau et les mathématiques. J'ai découvert et implémenté la **Quantification (format GGUF)**. C'est une technique de compression qui réduit la précision des calculs (de 16 bits à 4 bits) pour qu'il le modèle tienne dans la mémoire RAM classique. J'ai divisé la consommation par 4 sans perdre l'intelligence. C'était la clé de la viabilité du projet.

### Difficulté 2 : Le Problème de la Concurrence (Backend Async)
Quand j'ai voulu mettre le site en ligne pour la première fois, j'ai invité deux amis à tester en même temps.
* **Le Résultat :** Le serveur a crashé immédiatement ou mélangeait les réponses.
* **Le Problème :** Les modèles d'IA monopolisent 100% du processeur (ou du GPU) quand ils génèrent une réponse. C'est une opération "bloquante". Si une deuxième personne envoie une demande pendant ce temps, le système ne répond plus.
* **La Solution :** J'ai dû réécrire tout mon backend en architecture **Asynchrone (AsyncIO)**. Ce n'est pas juste un changement de syntaxe, c'est un changement de paradigme. J'ai mis en place un système complexe de file d'attente (Queue) et de verrous (Mutex/Locks) qui permet au serveur d'accepter des centaines de connexions, de les mettre en attente proprement, et de les traiter une par une à la vitesse de l'éclair, sans jamais planter. C'était un défi d'algorithmique pure.

### Difficulté 3 : La Qualité des Données
Au début, je nourrissais mon IA avec n'importe quoi trouvé sur internet via mon collecteur. Elle se mettait à "halluciner" ou à répéter des textes publicitaires qu'elle avait lus.
* **L'Apprentissage :** J'ai compris le principe de "Garbage In, Garbage Out". La qualité de l'IA dépend de la qualité des données.
* **La Solution :** J'ai dû développer des algorithmes de filtrage stricts. J'ai appris à manipuler le DOM HTML avec BeautifulSoup pour extraire chirurgicalement le "vrai" contenu d'une page web et ignorer le reste. J'ai aussi mis en place un système de dédoublonnage par hachage (MD5 checksum) pour éviter que l'IA ne lise 10 fois la même news et ne boucle dessus.

## 6. Les apports en terme de compétences développées

Ce projet m'a fait grandir techniquement bien plus vite que n'importe quel cours théorique. Il valide des compétences professionnelles concrètes :

* **Architecture & Système :** Conception d'applications complexes, micro-services, gestion de serveurs sous Linux.
* **Python :** Maîtrise avancée du langage (Gestionnaire de contexte, Optimisation mémoire).
* **Data Engineering :** Capacité à construire des pipelines ETL (Extract, Transform, Load) robustes pour manipuler des millions de données textuelles.
* **Intelligence Artificielle (MLOps) :** Compréhension profonde des Transformers, processus d'Inférence, Fine-Tuning QLoRA, RAG (Retrieval Augmented Generation). Je ne suis plus dépendant des GAFAM pour innover.

## 7. Le Futur du projet

Maintenant que j'ai réussi à réaliser mon objectif initial et que le produit est plutot stable, le but est de le continuer et de le faire évoluer. Pour moi, Aelyon n'est que la première étape de mon parcours.

J'ai plusieurs idées d'évolution constante. Je travaille actuellement sur comment améliorer les réponses, evité une surchare coté serveur. Ce projet je veux que ce projet sois en constante évolution avec ce que je vais apprendre dans le futur.

## 8. La suite ...

Aujourd'hui j'ai pour ambition de devenir developpeur IA, ce projet ma donc permis de découvrir en profondeur ce monde la ainsi que ceux qui l'entoure (je pense principalement a la data), c'est donc pour ca que je suis a la recherche d'une alternance en tant que developpeur IA 

### Mots de Fin

Merci aux différentes personnes qui m'ont accompagné de près ou de loin dans ce projet, en prenant du temps pour effectuer des tests, essayer de résoudre des problèmes techniques, m'avoir soutenu ou même suivi tout au long de celui-ci.

Je tiens particulièrement à remercier **Gentien Philibert** qui a suivi le projet tout du long, a contribué techniquement à la création du site web, et a réaliser des tests avec le models.

**Merci**
