# CERTIFICATION DÉVELOPPEUR EN INTELLIGENCE ARTIFICIELLE ET DATA SCIENCE RNCP 36581

## BLOCS DE COMPÉTENCES

**BLOC DE COMPÉTENCES E6.3 :** Produire et maintenir une solution I.A.

**BLOC DE COMPÉTENCES E6.4 :** Gérer les activités/tâches du développement d'une solution I.A.

## CAHIER DES CHARGES DE LA MSPR

### Mise en production d'une solution à partir des éléments de contextes fournis

---

### Objectifs techniques

#### Développement Back-end

- Développer les composants de la solution IA sous forme d'API et/ou des programmes intégrés en utilisant des outils adaptés.

#### Développement Front-end

- Développer l'interface homme-machine en utilisant les techniques, les outils et les plateformes dans l'objectif de rendre l'approche ergonomique et conforme à l'accessibilité numérique.

#### Tests et Déploiement

- Mettre en œuvre des plans de tests définis pour préparer le déploiement de la solution I.A.

#### Supervision et Maintenance

- Superviser le fonctionnement de la solution IA à partir des outils de monitorage afin de détecter et corriger les éventuels dysfonctionnements dans une démarche d'amélioration continue.
- Corriger les dysfonctionnements de son périmètre de responsabilité.
- Réaliser les évolutions fonctionnelles de la solution I.A afin de répondre au besoin d'amélioration.

#### Méthodologie

- Mettre en œuvre une méthodologie adaptée d'utilisation et sa maintenance.

---

## LIVRABLES ATTENDUS

### Partie Technique

1. Des scripts et configurations pour le déploiement de l'infrastructure.
2. Des fichiers Docker/Podman pour la conteneurisation des solutions.
3. Des mécanismes de sauvegarde et de restauration des données et des services.
4. Des fichiers relatifs aux pipelines d'intégration et des déploiements continus, incluant les étapes de build, test, analyse de code, et déploiement.
5. Une documentation détaillée du pipeline, avec des instructions pour son utilisation et sa maintenance.
6. Une documentation détaillée de vos images Docker/Podman.
7. Des rapports de tests automatisés et indicateurs de qualité de code.
8. Une documentation de l'architecture système en format UML.

### Partie gestion de projet

1. Des rapports de sprint incluant les objectifs et les réalisations.
2. Un tableaux Kanban ou Scrum illustrant l'avancement des tâches.
3. La présentation de l'ensemble des cérémonies utilisées en fonction du choix de votre méthode agile.

### Bonus

Enfin, et en bonus, la mise en place d'un environnement Kubernetes (Mononœud), comprenant les fichiers de configuration Kubernetes, ainsi qu'une documentation liée sera appréciée.

### Rapport final

Un rapport écrit et une présentation des deux parties sont attendus pour structurer l'ensemble.

---

## MODALITÉS D'ÉVALUATION

**19 heures** : Durée de préparation

### Mise en œuvre

Travail d'équipe constituée de 4 apprenants-candidats (5 maximum si groupe impair)

### Résultats attendus

- Mise en place d'une infrastructure supportant la charge
- Mise en place d'une stratégie de conteneurisation de l'applicatif
- Sécurisation de l'application
- Déploiement automatisé de l'application
- Mise en place d'une gestion de projet Agile
- Présentation des réalisations

---

## EXIGENCES TECHNIQUES SPÉCIFIQUES

### Contexte d'agilité

Dans un contexte d'agilité, la solution de gestion de projet pour laquelle vous avez opté doit être complétée. Vous prendrez notamment en compte la nécessité de la mise en place de cérémonie agile au sein d'un projet tel que celui-ci et définirez des rapports d'avancement réguliers, à intervalle de 3 jours.

### Adaptation par pays

#### États-Unis

- Le système devra gérer de grandes quantités de données à cause de la taille de la population
- Il devra inclure l'ensemble des solutions mise en place jusqu'à présent
- **Figure 1 : Cluster pour les États-Unis**

``` text
┌─────────────────────────────────────────────────────────────────────────┐
│ CLUSTER ÉTATS-UNIS                                                      │
│                                                                         │
│  ┌─────────────┐                    ┌──────────────────┐                │
│  │ API         │                    │ Solution Dataviz │                │
│  │ Technique   │                    │ (MSPR1)          │                │
│  │ (MSPR1)     │                    └──────────────────┘                │
│  └─────────────┘                             │                          │
│         │                                    │                          │
│         └──────────────┐          ┌──────────┘                          │
│                        ▼          ▼                                     │
│  ┌──────────┐     ┌─────────────────────┐     ┌─────────────┐           │
│  │Front-end │◄───►│Back-end (API IA)    │◄───►│Base de      │           │
│  │          │     │                     │     │données      │           │
│  └──────────┘     └─────────────────────┘     └─────────────┘           │
│                                                      ▲                  │
|                                                      │                  │
│                                               ┌──────────────┐          │
│                                               │ ETL          │          │
│                                               └──────────────┘          │
└─────────────────────────────────────────────────────────────────────────┘
```

#### France

- L'accent est mis sur le respect strict du RGPD et la sécurité des données personnelles
- Accès simplifié pour le grand public via des dispositifs mobiles et une interface en français
- La France n'ayant pas de spécialiste pour la consultation des données brutes, il ne sera pas nécessaire de déployer l'API technique conçue dans le MSPR1
- **Figure 2 : Cluster pour la France**

``` text
┌─────────────────────────────────────────────────────────────────────────┐
│ CLUSTER FRANCE                                                          │
│                                                                         │
│                                     ┌──────────────────┐                │
│                                     │ Solution Dataviz │                │
│                                     │ (MSPR1)          │                │
│                                     └──────────────────┘                │
│                                              │                          │
│                                              │                          │
│                                   ┌──────────┘                          │
│                                   ▼                                     │
│  ┌──────────┐     ┌─────────────────────┐     ┌─────────────┐           │
│  │Front-end │◄───►│Back-end (API IA)    │◄───►│Base de      │           │
│  │          │     │                     │     │données      │           │
│  └──────────┘     └─────────────────────┘     └─────────────┘           │
│                                                      ▲                  │
|                                                      │                  │
│                                               ┌──────────────┐          │
│                                               │ ETL          │          │
│                                               └──────────────┘          │
└─────────────────────────────────────────────────────────────────────────┘
```

#### Suisse

- L'application devra s'adapter aux trois langues nationales (français, allemand, italien)
- La Suisse ne souhaite pas intégrer la solution de Dataviz ainsi que l'API technique conçu lors du MSPR1
- **Figure 2 : Cluster pour la Suisse**
  
``` text
┌─────────────────────────────────────────────────────────────────────────┐
│ CLUSTER SUISSE                                                          │
│                                                                         │
│  ┌──────────┐     ┌─────────────────────┐     ┌─────────────┐           │
│  │Front-end │◄───►│Back-end (API IA)    │◄───►│Base de      │           │
│  │          │     │                     │     │données      │           │
│  └──────────┘     └─────────────────────┘     └─────────────┘           │
│                                                      ▲                  │
|                                                      │                  │
│                                               ┌──────────────┐          │
│                                               │ ETL          │          │
│                                               └──────────────┘          │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## COMPÉTENCES ÉVALUÉES

### Compétences techniques

- Développer le back-end : Développer les composants de la solution IA sous forme d'API et/ou des programmes intégrés en utilisant des outils adaptés.
- Développer le front-end : Développer l'interface homme-machine en utilisant les techniques, les outils et les plateformes dans l'objectif de rendre l'approche ergonomique et conforme à l'accessibilité numérique.
- Mettre en œuvre des plans de tests définit pour préparer le déploiement de la solution I.A.
- Superviser le fonctionnement de la solution IA à partir des outils de monitorage afin de détecter et corriger les éventuels dysfonctionnements dans une démarche d'amélioration continue.
- Corriger les dysfonctionnements de son périmètre de responsabilité.
- Réaliser les évolutions fonctionnelles de la solution I.A afin de répondre au besoin d'amélioration.

### Compétences en gestion de projet

- Mettre en œuvre une méthodologie adaptée de réalisation du projet, afin de garantir le déploiement du projet en collaboration avec les équipes projet dans les délais et dans un environnement agile.
- Rendre compte de l'avancement du projet aux personnes en lien avec le projet grâce aux canaux de communication adéquat et adapté afin de permettre à tout public d'accéder librement et facilement au numérique (public cible, collaborateurs interne, …)
- Rédiger des rapports d'activité et de reste à faire, éventuellement en anglais. Recommander des actions.
- Contribuer ou animer des réunions de travail avec les équipes projets afin de faire évoluer l'avancée du projet, possiblement en anglais.
- Auto-contrôler ses actions et productions au regard du cahier des charges afin de garantir leurs cohérences.

### Compétences en veille technologique

- Définir et mettre en place un système de veille permettant de collecter, classifier et analyser l'information afin d'améliorer la prise de décisions techniques.
- Améliorer le potentiel de développement et/ou d'exploitation des solutions IA en exploitant les informations recueillies par le système de veille : Technologiques, Réglementaires, Sécurité informatique.

---

## WEBOGRAPHIE

### Documentation technique

- [Docker](https://docs.docker.com/)
- [Kubernetes](https://kubernetes.io/docs/home/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)

### CI/CD

- [Jenkins](https://www.jenkins.io/doc/)
- [GitLab CI](https://docs.gitlab.com/ee/ci/)
- [GitHub Actions](https://docs.github.com/fr/actions)

### Qualité de code

- [SonarQube](https://docs.sonarqube.org/latest/)

### Gestion de projet Agile

- [Scrum Guides](https://scrumguides.org/)
- [Jira](https://www.atlassian.com/software/jira)
- [Trello](https://trello.com/en)

### Sécurité et réglementation

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [RGPD](https://gdpr.eu/)
