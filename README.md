# Awesome EDS - Entrepôts de Données de Santé [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
Une liste de ressources utiles pour les entrepôts de données de santé (EDS). La majorité des solutions présentées sont libre ou opensource. La section *plateformes propriétaires* décrit les principaux acteurs privés.

## Sommaire

- [Standards & modèles de données](#standards--modèles-de-données)
- [Terminologies & ontologies](#terminologies--ontologies)
- [ETL & orchestration](#etl--orchestration)
- [Bases de données](#bases-de-données)
- [Bibliothèques](#bibliothèques)
- [Pseudonymisation et anonymisation](#pseudonymisation-et-anonymisation)
- [Plateformes ouvertes](#plateformes-ouvertes)
- [Plateformes propriétaires](#plateformes-propriétaires)
- [Jeux de données](#jeux-de-données)
- [SNDS](#SNDS)
- [Cadre réglementaire & gouvernance](#cadre-réglementaire--gouvernance)
- [Ressources, formations & documentation](#ressources-formations--documentation)
- [Qualité des données](#qualité--des--données)
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
- [Dagster](https://dagster.io/) - Orchestrateur orienté *resultat*, avec typage, tests et observabilité des pipelines dans un écosystème python.
- [Prefect](https://www.prefect.io/) - Un autre orchestrateur en Python.
- [Mage](https://www.mage.ai/) - Un orchestrateur très graphique ressemblant à des notebook jupyter.
- [dbt](https://www.getdbt.com/) - Transformation de données en SQL versionné, utile pour construire les couches de mapping vers OMOP.
- [Nifi](https://nifi.apache.org/) -  Outil open source d'automatisation et de gestion de flux de données avec une interface graphique.
- [PICOLA](https://gitlab.com/healthdatahub/boas/hdh/picola) - Pipeline Airflow prêt à l'emploi pour convertir des lames d'anatomopathologie numérisées (ndpi, mrxs, svs, scn…) en TIFF pyramidal via vips. Apache 2.0.

## Bases de données

- [clickhouse](https://clickhouse.com/) - Base de données OLAP très efficace
- [duckdb](https://duckdb.org/) - Le couteau suisse de la donnée. 
- [chromadb](https://www.trychroma.com/) - Un base de données vectorielle pour faire un RAG.
- [MORS](https://gitlab.com/ricdc/outils/mors) - Module d'Observation et de Rapprochement du Statut vital : rapprochement des patients de l'EDS avec le fichier des décès INSEE (Python/Polars, distance de Damerau-Levenshtein). 
- [extract_metadata](https://gitlab.com/healthdatahub/boas/hdh/extract_metadata) - Extraction des métadonnées d'une base tabulaire (.csv) et d'images DICOM vers des fichiers JSON.

## Bibliothèques
- [pypmsi](https://guillaumepressiat.github.io/pypmsi) - Package Python pour importer, gérer et exploiter les données PMSI (MCO, SSR, HAD, PSY, RSF).
- [pmeasyr](https://github.com/GuillaumePressiat/pmeasyr) - Package R pour importer, gérer et exploiter les données PMSI (MCO, SSR, HAD, PSY, RSF).
- [eds-scikit](https://github.com/aphp/eds-scikit) - Boîte à outils Python pour l'analyse de données OMOP issues d'un EDS (AP-HP).
- [unword](https://github.com/dridk/unword) - Conversion des ancien fichier word (*.doc) en markdown
- [EDS-NLP](https://github.com/aphp/edsnlp) - Framework de NLP clinique francophone (règles + deep learning), compatible spaCy et PyTorch, développé à l'AP-HP.

## Pseudonymisation et anonymisation

- [eds-pseudo](https://github.com/aphp/eds-pseudo) - Modèle hybride de pseudonymisation des comptes-rendus cliniques, basé sur EDS-NLP.
- [unpii](https://github.com/dridk/unpii) - Outil de pseudonymisation basé sur des regexp écrit en Rust avec un backend python. Très rapide.
- [incognito](https://github.com/Micropot/incognito) - Outil de pseudonymisation basé sur des regexp écrit en python.
- [Presidio](https://github.com/microsoft/presidio) - Librarie de microsoft pour pseudonymiser des documents. Pas de bon support en français.
-  [Open AI Privacy Filter](https://huggingface.co/openai/privacy-filter) - Modèle de pseudonymisation
- [deidcm](https://github.com/Epiconcept-Paris/deidcm) - Bibliothèque Python de pseudonymisation DICOM : nettoyage des attributs et suppression par OCR des textes incrustés sur les clichés. Développée pour la mammographie (deep.piste), utilisable sur d'autres modalités. MIT.

## Plateformes ouvertes

- [Jupyter](https://jupyter.org/) - Une plateforme d'analyse pour les datascientist.
- [Marimo](https://marimo.io/) - une alternative à Jupyter très appréciée à Brest.
- [JupyterLite](https://chu-brest.github.io/jupyter-lite) - Une instance client only de jupyter lite avec duckdb et pola.rs
- [LinkR](https://linkr.interhop.org/) - Plateforme open source de data science sur EDS permettant à cliniciens et data scientists de collaborer.
- [Clinical-Contract](https://artheioupfat.github.io/clinical-contract/) - Plateforme open source permettant de rédiger des Datacontracts ainsi que de vérifier la conformité d'un fichier de données 
- [Orthanc](https://www.orthanc-server.com/) - Outils permettant d'interroger le PACS.
- [Cohorte360](https://docs.cohort360.org/) - Solution utilisée à l'APHP
- [Fhir-server](https://www.health-samurai.io/fhir-server) - Une base de données orientée FHIR.
- [LibreDataHub](https://interhop.org/) - Environnement de data science hébergeable en interne (HDS) pour l'apprentissage et l'analyse de données de santé (InterHop).
- [OHDSI Broadsea](https://github.com/OHDSI/Broadsea) - Déploiement conteneurisé de la suite d'outils OHDSI.
- [OHDSI ATLAS](https://github.com/OHDSI/Atlas) - Interface web de définition de cohortes et d'analyses sur des données OMOP.
- [Goupile](https://interhop.org/projets/goupile) - Editeur de formulaire pour le reccueil de données pour la recherche.
- [LibreDataHub](https://libredatahub.org/) - Plateforme datascience ouverte 
- [Termose](https://chu-brest.github.io/termose/) - Explorateur de terminologie SMT.

## Plateformes propriétaires

- [Arkhn](https://www.arkhn.com/fr/eds) - une solution d'EDS assez moderne proposant des fonctionnalités basé sur des LLM/   
- [Codoc](https://www.codoc.co/fr) - Une suite d'applications et une solution d'entrepôt de données de santé pour démocratiser l'usage de la donnée médicale dans les établissements de santé. 
- [Ehop](https://www.enovacom.com/solution/ehop-lentrepot-de-donnees-dedie-a-la-reutilisation-de-donnees-de-vie-reelles) - Une solution d'EDS basé sur Oracle, orienté recherche documentaires. La transformation des données est faite en XSLT.
- [Consore](https://www.consore.coexya.eu/consore) - Moteur de recherche médical dédié à la cancérologie

## Jeux de données

- [MIMIC-IV](https://physionet.org/content/mimiciv/) - Base de données de réanimation en accès contrôlé (PhysioNet), de référence pour la recherche.
- [eICU Collaborative Research Database](https://physionet.org/content/eicu-crd/) - Données multicentriques de soins critiques.
- [Open DAMIR](https://www.data.gouv.fr/datasets/open-damir-base-complete-sur-les-depenses-dassurance-maladie-interregimes) -base complète sur les dépenses d'assurance maladie interrégimes
- [medtrajectory_datagen](https://gitlab.inria.fr/tguyet/medtrajectory_datagen) - Générateur de bases synthétiques et réalistes respectant le schéma de la base principale du SNDS, sans contrainte de diffusion. Idéal pour l'enseignement et le test de solutions logicielles
  
## SNDS 

- [sndskit](https://github.com/Epiconcept-Paris/sndskit) - sndskit est un package Python qui sert de moteur de recherche dans les données du SNDS. On y déclare les codes CIM-10, ATC et CCAM qui nous intéressent, et il retrouve pour chaque patient les dates de diagnostics, traitements et actes correspondants (séjours, ALD, SSR, causes de décès).
- [snds_omop](https://gitlab.com/healthdatahub/boas/hdh/snds_omop) - Script SQL en DBT permettant la conversion du schéma du SNDS en schéma OMOP.
- [sndsTools](https://github.com/SNDStoolers/sndsTools) - Package R permet d'extraire des données de recours aux soins du SNDS pour une population donnée.
- [Cartographie des pathologies et des dépenses (G12)](https://gitlab.com/healthdatahub/boas/cnam/cartographie-des-pathologies) - Implémentation R officielle CNAM des algorithmes de repérage d'une soixantaine de pathologies « tops » dans le SNDS (~300 variables indicatrices). GPLv3, mise à jour à chaque version.
- [Elixhauser](https://gitlab.com/healthdatahub/boas/cemka/elixhauser) - Macro SAS de calcul du score de comorbidité d'Elixhauser (31 catégories, scores brut / AHRQ / van Walraven) à partir du PMSI MCO.
- [Combicancer](https://gitlab.com/healthdatahub/boas/institut-curie/combicancer) - Pipeline PySpark de nettoyage et de reformatage OMOP-like du SNDS natif (graphe de jointures, sortie Parquet, quality checks).
  
## Cadre réglementaire & gouvernance

- [Référentiel EDS de la CNIL](https://www.cnil.fr/) - Cadre de conformité (délibération n° 2021-123) pour la constitution d'un entrepôt de données de santé.
- [Presentation juridique sur la constitution des EDS](https://girci-idf.fr/wp-content/uploads/2023/10/20230704_Webinaire-Juridique_Constitution-d_un-EDS.pdf) - Si vous ne comprenez rien à la réglementation. Très bon document. 
- [Cartographie des EDS en France (CNIL)](https://www.cnil.fr/fr/explorez-la-cartographie-des-entrepots-de-donnees-de-sante-en-france) - Recensement des EDS déclarés sur le territoire.
- [Health Data Hub](https://www.health-data-hub.fr/) - Plateforme nationale des données de santé.
- [Entrepôts de données EDS (Ministère de la Santé)](https://sante.gouv.fr/systeme-de-sante/numerique-en-sante/sih/entrepots-de-donnees-eds/) - Cadre institutionnel et appels à projets.

## Ressources, formations & documentation
- [Interhop](https://interhop.org/) - InterHop.org promeut et développe l'utilisation du logiciel libre et open source pour la recherche en santé.
- [Starter kit EDS (Health Data Hub)](https://www.health-data-hub.fr/starter-kit-EDS) - Boîte à outils pour monter un EDS de bout en bout.
- [Documentation collaborative du SNDS](https://documentation-snds.health-data-hub.fr/) - Référence sur les données du SNDS et leur transformation OMOP.
- [Traitement des données PMSI avec R](https://guillaumepressiat.github.io/pmeasyr-book/) - Livret d'exemples d'analyses PMSI avec `pmeasyr`.
- [Bibliothèque Ouverte d'Algorithmes en Santé (BOAS)](https://www.health-data-hub.fr/bibliotheque-ouverte-algorithmes-sante) - Catalogue public d'algorithmes en santé (SNDS, imagerie, NLP) avec fiches détaillées : méthodologie, validation, maintenance, lien vers le dépôt.

## Qualité des données

- [OHDSI Achilles](https://github.com/OHDSI/Achilles) - Caractérisation et profilage d'une base OMOP CDM.
- [OHDSI DataQualityDashboard](https://github.com/OHDSI/DataQualityDashboard) - Exécution systématique de milliers de contrôles qualité sur un CDM OMOP (framework Kahn).
- [CdmInspection](https://github.com/EHDEN/CdmInspection) - Rapport d'inspection EHDEN d'une base OMOP, utilisé pour la certification.
- [Extract Metadata](https://gitlab.com/healthdatahub/boas/hdh/extract_metadata) - Extraction de métadonnées tabulaires et DICOM.

## Contribuer

Les contributions sont les bienvenues !


> Cette liste suit les principes des [awesome lists](https://github.com/sindresorhus/awesome). Sauf mention contraire, son contenu est diffusé sous licence [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
