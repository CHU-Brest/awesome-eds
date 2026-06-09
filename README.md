# Awesome EDS - Entrepôts de Données de Santé [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
Une liste de ressources utiles pour les entrepôts de données de santé (EDS) 
## Sommaire

- [Standards & modèles de données](#standards--modèles-de-données)
- [Terminologies & ontologies](#terminologies--ontologies)
- [ETL & orchestration](#etl--orchestration)
- [Bibliothèques](#bibliothèques)
- [Traitement du langage naturel (TAL)](#traitement-du-langage-naturel-tal)
- [Plateforme ouverte](#plateformes-ouvertes)
- [Plateforme propriétaire](#plateformes-propriétaires)
- [Jeux de données](#jeux-de-données)
- [Cadre réglementaire & gouvernance](#cadre-réglementaire--gouvernance)
- [Institutions, réseaux & communautés](#institutions-réseaux--communautés)
- [Ressources, formations & documentation](#ressources-formations--documentation)
- [Contribuer](#contribuer)

## Standards & modèles de données

- [OMOP Common Data Model](https://ohdsi.github.io/CommonDataModel/) - Modèle de données commun de l'OHDSI, largement adopté par les EDS pour standardiser les données observationnelles.
- [HL7 FHIR](https://hl7.org/fhir/) - Standard d'échange et de représentation des données de santé, central pour l'interopérabilité.
- [i2b2](https://www.i2b2.org/) - Plateforme historique d'entrepôt et de requêtage de données cliniques pour la recherche.
- [openEHR](https://www.openehr.org/) - Spécifications ouvertes pour la modélisation des dossiers de santé.
- [Osiris](https://ig-osiris.cancer.fr/ig/osiris/) - Modèle de données commun pour des données cliniques et génomiques en oncologie de précision.

## Terminologies & ontologies

- [Serveur Multi-Terminologies (SMT)](https://smt.esante.gouv.fr/) - Catalogue et API des terminologies de santé publiés par l'Agence du Numérique en Santé (ANS).
- [Vocabulaires OMOP (Athena)](https://athena.ohdsi.org/) - Référentiel standardisé des concepts utilisés par le CDM OMOP.
- [HeTOP](https://www.hetop.eu/) - Portail multi-terminologies et multilingue du CISMeF (CHU de Rouen).
- [SNOMED CT](https://www.snomed.org/) - Nomenclature clinique internationale de référence.
- [LOINC](https://loinc.org/) - Codification des examens de biologie et observations cliniques.
- [CIM-10 / ICD-10](https://icd.who.int/) - Classification internationale des maladies (OMS).
- [CCAM](https://www.atih.sante.fr/) - Classification commune des actes médicaux (France, ATIH).
- [SMT au format parquet](https://www.data.gouv.fr/datasets/terminologie-medicale-au-format-parquet) - Ontologie (ATC, CIM10, CCAM, CIM10) du SMT au format parquet.

## ETL & orchestration

- [Apache Airflow](https://airflow.apache.org/) - Orchestrateur de workflows par DAG, courant pour piloter les pipelines d'alimentation d'un EDS.
- [Airflow](https://airflow.apache.org) - Orchestrateur orienté *tâches* dans un écosystème python.
- [Dagster](https://dagster.io/) - Orchestrateur orienté *resultat*, avec typage, tests et observabilité des pipelines dans un écosystème python.
- [Prefect](https://www.prefect.io/) - Un autre oprchestrateur en Python.
- [Mage](https://www.mage.ai/) - Un orchestrateur très graphique ressemblant à des notebook jupyter.
- [dbt](https://www.getdbt.com/) - Transformation de données en SQL versionné, utile pour construire les couches de mapping vers OMOP.
- [Nifi](https://nifi.apache.org/) -  Outil open source d'automatisation et de gestion de flux de données avec une interface graphique.

## Bibliothèques
- [pypmsi](https://guillaumepressiat.github.io/pypmsi) - Package Python pour importer, gérer et exploiter les données PMSI (MCO, SSR, HAD, PSY, RSF).
- [pmeasyr](https://github.com/GuillaumePressiat/pmeasyr) - Package R pour importer, gérer et exploiter les données PMSI (MCO, SSR, HAD, PSY, RSF).
- [eds-scikit](https://github.com/aphp/eds-scikit) - Boîte à outils Python pour l'analyse de données OMOP issues d'un EDS (AP-HP).
- [unword](https://github.com/dridk/unword) - Conversion des ancien fichier word (*.doc) en markdown
  
## Traitement du langage naturel (TAL)
- [EDS-NLP](https://github.com/aphp/edsnlp) - Framework de NLP clinique francophone (règles + deep learning), compatible spaCy et PyTorch, développé à l'AP-HP.
- [eds-pseudo](https://github.com/aphp/eds-pseudo) - Modèle hybride de pseudonymisation des comptes-rendus cliniques, basé sur EDS-NLP.
- [unpii](https://github.com/dridk/unpii) - Outi de pseudo-anonymisation basé sur des regexp écrit en Rust avec un backend python. Très rapide.
- [incognito](https://micropot.github.io/incognito/) - Outi de pseudo-anonymisation basé sur des regexpm écrit en python

## Plateformes ouvertes

- [Jupyter](https://jupyter.org/) - Une plateforme d'analyse pour les datascientist.
- [Marimo](https://marimo.io/) - une alternative à Jupyter très appréciée à Brest.
- [JupyterLite](https://chu-brest.github.io/jupyter-lite) - Une instance client only de jupyter lite avec duckdb et pola.rs
- [LinkR](https://linkr.interhop.org/) - Plateforme open source de data science sur EDS permettant à cliniciens et data scientists de collaborer.
- [LibreDataHub](https://interhop.org/) - Environnement de data science hébergeable en interne (HDS) pour l'apprentissage et l'analyse de données de santé (InterHop).
- [OHDSI Broadsea](https://github.com/OHDSI/Broadsea) - Déploiement conteneurisé de la suite d'outils OHDSI.
- [OHDSI ATLAS](https://github.com/OHDSI/Atlas) - Interface web de définition de cohortes et d'analyses sur des données OMOP.
- [Goupile](https://interhop.org/projets/goupile) - Editeur de formulaire pour le reccueil de données pour la recherche.
- [LibreDataHub](https://libredatahub.org/) - Plateforme datascience ouverte 
- [Termose](https://chu-brest.github.io/termose/) - Explorateur de terminologie SMT.

## Plateformes propriétaires

- [Arkhn](https://www.arkhn.com/fr/eds) - une solution d'EDS assez moderne proposant des fonctionnalités basé sur des LLM/   
- [Codoc](https://www.codoc.co/fr) - Une suite d'applications et une solution d'entrepôt de données de santé pour démocratiser l'usage de la donnée médicale dans les établissements de santé. 
- [Ehop](https://www.enovacom.com/solution/ehop-lentrepot-de-donnees-dedie-a-la-reutilisation-de-donnees-de-vie-reelles) - Une solution d'EDS basé sur des technologies  d'un autre âge ( php / oracle ).
  
## Jeux de données

- [MIMIC-IV](https://physionet.org/content/mimiciv/) - Base de données de réanimation en accès contrôlé (PhysioNet), de référence pour la recherche.
- [eICU Collaborative Research Database](https://physionet.org/content/eicu-crd/) - Données multicentriques de soins critiques.
- [Open DAMIR](https://www.data.gouv.fr/datasets/open-damir-base-complete-sur-les-depenses-dassurance-maladie-interregimes) -base complète sur les dépenses d'assurance maladie interrégimes

 
## Cadre réglementaire & gouvernance

- [Référentiel EDS de la CNIL](https://www.cnil.fr/) - Cadre de conformité (délibération n° 2021-123) pour la constitution d'un entrepôt de données de santé.
- [Cartographie des EDS en France (CNIL)](https://www.cnil.fr/fr/explorez-la-cartographie-des-entrepots-de-donnees-de-sante-en-france) - Recensement des EDS déclarés sur le territoire.
- [Health Data Hub](https://www.health-data-hub.fr/) - Plateforme nationale des données de santé.
- [Entrepôts de données EDS (Ministère de la Santé)](https://sante.gouv.fr/systeme-de-sante/numerique-en-sante/sih/entrepots-de-donnees-eds/) - Cadre institutionnel et appels à projets.

## Ressources, formations & documentation

- [Starter kit EDS (Health Data Hub)](https://www.health-data-hub.fr/starter-kit-EDS) - Boîte à outils pour monter un EDS de bout en bout.
- [Documentation collaborative du SNDS](https://documentation-snds.health-data-hub.fr/) - Référence sur les données du SNDS et leur transformation OMOP.
- [Traitement des données PMSI avec R](https://guillaumepressiat.github.io/pmeasyr-book/) - Livret d'exemples d'analyses PMSI avec `pmeasyr`.

## Contribuer

Les contributions sont les bienvenues !


> Cette liste suit les principes des [awesome lists](https://github.com/sindresorhus/awesome). Sauf mention contraire, son contenu est diffusé sous licence [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
