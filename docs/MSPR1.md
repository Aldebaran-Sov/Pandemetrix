# CERTIFICATION DÉVELOPPEUR EN INTELLIGENCE ARTIFICIELLE ET DATA SCIENCE RNCP 36581

## BLOC DE COMPÉTENCES 1 : Créer un modèle de données d'une solution I.A en utilisant des méthodes de Data sciences

## CAHIER DES CHARGES DE LA MSPR

### Développement et déploiement d'une application dans le respect du cahier des charges Client // Création d'un backEnd métier permettant le nettoyage et la visualisation des données

---

### Contexte du Projet

Vous travaillez pour le groupe **ANALYZE IT**, spécialisé dans les données de santé et dépêché par l'OMS en tant que prestataire de service pour répondre à son besoin de création de Système d'Information.

Votre équipe et vous-même avez la charge de développer une solution permettant d'ingérer des données provenant de différentes sources, telles que :

- Les bases de données publiques de santé
- Les archives hospitalières  
- Les publications scientifiques

Les données devront être au format **JSON ou CSV**. Les données peuvent être des pandémies de votre choix, une justification sera attendue.

En complément, vous aurez la charge de nettoyer, trier, et assurer la qualité des données, en tenant compte des différentes sources hétérogènes. Il serait appréciable d'avoir une solution générique, le minimum attendu dans un premier temps est une solution permettant de nettoyer et trier des données sur deux sources de données de votre choix que vous justifierez.

Enfin, vous avez la charge de la construction d'une structure de stockage adaptée pour l'analyse des données, permettant une interrogation rapide et flexible de ces dernières. Vous mettrez également en place une solution de lecture de données.

---

## Compétences Visées

1. **Définir les sources et les outils nécessaires** pour permettre de collecter les données

2. **Recueillir de manière sécurisée** les informations à partir de sources adaptées (sources hétérogènes, internes fournies par le client ou externes accessibles en Open Data) permettant de définir les données à collecter pour réaliser l'architecture de données

3. **Paramétrer les outils** afin d'importer les données de manière automatisée et sécurisée

4. **Analyser, nettoyer, trier et s'assurer de la qualité des données** afin de les rendre exploitables pour la solution I.A, en utilisant des outils d'analyse et de visualisation des données et se basant sur des approches de la Data science

5. **Construire la structure de stockage des données** (modèle de données) qui répond au mieux au besoin d'analyse

6. **Représenter graphiquement** le modèle de données

---

## LIVRABLES ATTENDUS

1. **Un modèle de données** au format Merise avec MCD, MLD et MPD ou format UML

2. **Une base de données relationnelle** (script de création)

3. **Mise en place d'une solution ETL**. Les jobs mis en place devront permettre de :
   a. Extraire les données des fichiers Json et CSV
   b. Nettoyer, agréger, normaliser et supprimer les doublons de données
   c. Charger les données dans la base de données mis en place

4. **Une API** afin de pouvoir lire, modifier, supprimer et ajouter des données. L'API doit être flexible et permettre d'obtenir qu'une partie des informations si le développeur le souhaite. L'API ne sera utilisée que par un seul développeur pour le moment.

5. **Une documentation d'API** de type OPEN API Spécification

6. **Un tableau de bord interactif** réalisé avec un outil de datavisualisation, permettant l'exploration et l'exportation des données historiques des pandémies. Mise en place de filtres afin de fluidifier la lecture de ces tableaux. Les filtres mis en place seront à justifier dans une documentation.

7. **Une documentation** présentant la solution ETL ainsi que sa justification

8. **Une documentation détaillée** sur la solution mise en place

---

## WEBOGRAPHIE

- [Documentation Power BI](https://docs.microsoft.com/fr-fr/power-bi/)
- [Kaggle Dataset](https://www.kaggle.com/datasets/)
- [Guide ETL open source Apache Hop](https://hop.apache.org/manual/latest/getting-started/)
- [Guide ETL Talend](https://www.talend.com/fr/resources/guide-etl/)
- [Comparatif ETL vs ELT](https://www.talend.com/fr/resources/elt-vs-etl/)
