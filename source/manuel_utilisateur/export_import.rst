.. _export_import:

###############
Export / Import
###############

.. _export_sitadel:

Export SITADEL
##############

(:menuselection:`Export / Import --> Export SITADEL`)

Ce menu sert à générer un export SITADEL.

=============
Configuration
=============

Au préalable, il faut vérifier que certains paramètres (:menuselection:`Administration --> Paramètre`) 
soient correctement configurés et ceci pour la collectivité réalisant l'export (en cas d'EPCI la collectivité de niveau 2) :

* **region** : doit contenir le code insee de la région, c'est-à-dire du service destinataire de l'export, sur deux caractères (exemple pour l'Ile-de-France = 11)
* **commune** : doit contenir le code insee de la commune référente pour l'export, c'est-à-dire du service expéditeur sur trois caractères (la plus grosse des communes en cas d'EPCI)
* **departement** : doit contenir le code insee du département dans lequel se trouve le service instructeur, sur 3 caractères (exemples : 001 à 095, 02A, 02B, 971...974)

==========================
Fonctionnement de l'export
==========================

Il suffit de saisir la période pour laquelle vous souhaitez exporter les mouvements des dossiers au format SITADEL.
Les champs à renseigner sont :

* la date de début de la période souhaitée ;
* la date de fin de la période souhaitée ; 
* un numéro d'ordre d'envoi.

La période se base sur la date de dernière modification des dossiers. Cette date est mise à jour à chaque instruction et à chaque changement dans les données techniques (CERFA) sur les dossiers d'instruction.
Le numéro d'ordre d'envoi est le numéro de version de votre export.

Les dossiers déjà exportés pour SITADEL n'apparaîtront plus dans les prochains exports. Ils seront à nouveau affichés lorsqu’au moins une des données utilisées par SITADEL sera différente du dernier export.

========
Résultat
========

Deux fichiers sont générés :

* l'export SITADEL à envoyer au pôle statistiques de votre région ;
* un fichier contenant les incohérences détectées dans les données.

Ce second fichier n'a qu'un but informatif. Il indique quel dossier et quelle 
information est incohérente.

Charge reste à l'utilisateur d'agir, ou non, en fonction du contenu de ce fichier.

Voici la liste exhaustive des messages qui peuvent être contenus dans ce fichier :

**La SHON existante avant travaux et la SHON démolie sont nulles alors cela devrait être une nouvelle construction.**
    → La nature du projet ou les surfaces saisies sont incorrectes

**La SHON existante avant travaux ne doit pas être supérieure à la SHON démolie.**
    → Les surfaces saisies ne sont pas correctes

**La SHON demolie s'accompagne obligatoirement de la SHON existante avant travaux.**
    → Les surfaces saisies ne sont pas correctes

**Les SHON globales supprimées par changement de destination ou de sous-destination et créées par le même changement doivent être égales.**
    → Les surfaces saisies ne sont pas correctes

**Les SHON créées par changement de destination ou de sous-destination s'accompagnent obligatoirement de SHON existante avant travaux non nulle.**
    → Les surfaces saisies ne sont pas correctes

**Un nombre de logements démolis strictement positif doit s'accompagner obligatoirement de SHON démolie.**
    → La surface démolie n'a pas été renseignée alors qu'elle aurait dû

**Un nombre de logements créés strictement positif doit s'accompagner obligatoirement de SHON créées ou de SHON créées par changement de destination ou de sous-destination ayant pour destination l'habitation.**
    → La surface créée/créée par changement n'a pas été renseignée alors qu'elle aurait dû

**La SHON créée ou créée par changement de destination ou de sous-destination concernant le service public ou l'interet collectif doit obligatoirement s'accompagner du choix de destination des constructions.**
    → La répartition des surfaces n'a pas été renseignée alors qu'elle aurait dû

**La destination principale du logement mise à residence principale ou residence secondaire doit obligatoirement s'accompagner d'un mode d'utilisation à occupation personnelle.**
    → Le mode d'utilisation du logement n'a pas été renseigné

**Le nombre total de logements créés doit être égal à la somme des nombres de logements créés ventilés par type de financement.**
    → La somme total des logements par type de financement ne correspond pas au nombre total saisi

**Le nombre total de logements créés doit être egal à la totalisation de la repartition des logements par nombre de pièces.**
    → La somme total des logements par nombre de pièce ne correspond pas au nombre total saisi

**Une ouverture de chantier ne peut concerner qu'un permis autorisé.**
    → Deux DOC ont été déposées

**La date d'ouverture de chantier doit être supérieure a la date d'autorisation.**
    → La date de dépôt du P0 doit être supérieure à la date de dépôt de la DOC

**Un achèvement de chantier ne peut concerner qu'un permis autorisé.**
    → Deux DAACT ont été déposées

**Un achèvement de chantier ne peut concerner qu'un permis sur lequel un chantier a été ouvert.**
    → La DOC n'a pas été déposée avant la DAACT

**La date d'achevement de travaux doit etre supérieure à la date d'ouverture des travaux.**
    → La date d'ouverture de chantier doit être inférieure à la date d'achèvement des travaux

======================
Historique des exports
======================

Tous les exports SITADEL et les fichiers d'incohérence sont historisés dans le tableau disponible sur le formulaire d'export SITADEL.

Par défaut les fichiers sont triés par date de fin de la période décroissante.

Les fichiers sont également filtrés par la collectivité de l'utilisateur connecté. En cas d'une configuration en multi-collectivités, les utilisateurs de niveau 2 accèdent à l'historique de toutes les collectivités.


.. _versement_archives:

Versement aux archives
######################

(:menuselection:`Export / Import --> Versement aux archives`)

Cette fonctionnalité permet d'importer automatiquement le numéro de versement
aux archives des dossiers depuis un fichier CSV.

==========================
Les interfaces utilisateur
==========================

Il y a deux interfaces :

Le formulaire de saisie
=======================

Cette interface permet de saisir les informations concernant l'importation des
numéros de versement aux archives des dossiers.

.. image:: versement_archive_formulaire.png

Les informations à saisir sont :

* **insee** : code INSEE à cinq chiffres. Si ce champ est renseigné, seulement
  les dossiers ayant le même code INSEE seront traités,
* **fichier** : fichier csv comportant les données de mise à jour du numéro de
  versement,
* **séparateur** : sélection du caractère utilisé pour la séparation des 
  colonnes dans le fichier csv (';' ou ',').

Le message de résultat
======================

Cette interface permet d'avoir un résumé des actions effectuées par rapport au
fichier csv.

.. image:: versement_archive_resultat.png

Le message indique :

* le nombre de ligne lues : total des lignes ayant subi un taitement,
* le nombre de ligne acceptées : total des lignes dont la mise à jour a été
  correctement effectuée,
* le nombre de ligne rejetées : total des lignes qui n'ont pas pu être traitées
  (voir :ref:`versement_archives_liste_statut_ligne`),
* le nombre de ligne ignorées : total des lignes qui n'ont pas été traitées car 
  le code INSEE renseigné dans le formulaire n'est pas le même que celui de la 
  ligne,
* la possiblité de télécharger le fichier CSV avec le détail pour chaque ligne.

==================
Format des données
==================

.. _versement_archives_format_donnees_entree:

Format des données en entrée
============================

Chaque ligne du fichier CSV en entrée doit respecter le format suivant :
Les champs doivent être séprarés par des ';'.
Le dernier champ de la ligne n'est pas suivi du séparateur ';' mais de la fin de
ligne.

* **Code insee** sur cinq caractères numériques,
* **Année** sur deux caractères,
* **Type du dossier d'autorisation** sur deux caractères alphanumérique
  (Exemple : PC, PA, etc...),
* **Numéro du dossier** sur cinq caractères maximum,
* **Numéro de version** sur deux caractères maximum,
* **Numéro de versement** sur trois ou quatre caractères numériques et suivi de 
  la lettre 'W' (Exemple : 1025W),
* **Numéro d'article** de 1 à 999999999999999.

Exemple de fichier CSV correct en entrée :

03185;08;PC;1;0;1025W;111111

03185;08;RU;1;0;1025W;222222

01234;08;AT;1;0;1025W;333333

01234;12;PC;1;0;1025W;444444

Format des données en sortie
============================

Le fichier téléchargeable lors de la fin du traitement est le même CSV qu'en
entrée avec une colonne en plus qui précise le traitement fait sur la ligne.

.. _versement_archives_liste_statut_ligne:

==========================
Liste des statuts de ligne
==========================

Voici la liste des statuts possible pour une ligne du fichier CSV :

* **ligne rejetée : nombre de séparateur incorrect.** Indique que la ligne peut 
  être mal formatée, notamment au niveau du nombre de colonness,
* **ligne rejetée : contenu non conforme.** Indique que certaines données sont 
  non conforme aux spécifications 
  (voir :ref:`versement_archives_format_donnees_entree`),
* **ligne ignorée : code insee différent de celui indiqué dans le formulaire.**,
* **ligne rejetée : dossier inexistant dans l'application.**,
* **ligne acceptée : dossier mis à jour.**,

=====================
Exemple d'utilisation
=====================

Avec comme code INSEE fournis : 01234.

Fichier CSV en entrée :

03185;08;PC;1;0;1025W;111111

03185;08;RU;1;0;1025W;222222

01234;08;AT;1;0;1025W;333333

01234;12;PC;1;0;1025W;444444

mmmmmmmjjjjjkkkklllll

aa;aa;aa;aa;aa;aa;aa


Fichier CSV en sortie :

03185;08;PC;1;0;1025W;111111;"ligne ignorée : code insee différent de celui indiqué dans le formulaire."

03185;08;RU;1;0;1025W;222222;"ligne ignorée : code insee différent de celui indiqué dans le formulaire."

01234;08;AT;1;0;1025W;333333;"ligne rejetée : dossier inexistant dans l'application."

01234;12;PC;1;0;1025W;444444;"ligne acceptée : dossier mis à jour."

mmmmmmmjjjjjkkkklllll;"ligne rejetée : nombre de séparateur incorrect."

aa;aa;aa;aa;aa;aa;aa;"ligne rejetée : contenu non conforme."


Statistiques à la demande
#########################

Ce menu permet d'exporter des dossiers d'instruction selon plusieurs critères et avec des
détails différents.

=======================
dossier_depots_division
=======================

Tous les dossiers.

* Filtre

  * date de dépôt

* Tri

  * code de division
  * date de dépôt
  * nom d'instructeur

* Aucun choix de champ à afficher n'est proposé. Tous les champs suivants seront récupérés.

* Champs

  * n° de dossier
  * division
  * date de dépôt
  * pétitionnaire principal
  * localisation

.. note::

  * La saisie des dates est obligatoire.

=================
dossier_detaillee
=================

Tous les dossiers.

* Filtre

  * date de dépôt
  * type de dossier d'autorisation

* Tri

  * date de décision
  * date de dépôt

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * numéro de dossier
  * date de dépôt
  * date d'ouverture de chantier
  * date de demande
  * date achèvement
  * date prévue de recevabilité
  * destination des surfaces
  * petitionnaire principal
  * localisation
  * référence cadastrale
  * date de décision
  * shon
  * architecte
  * affectation_surface
  * nature des travaux
  * nature du financement
  * nombre de logements
  * autorité compétente
  * décision

.. note::

  * La saisie des dates et du type de dossier d'autorisation est obligatoire.

==========================
dossier_detaillee_accordes
==========================

Dossiers qui ont reçu un avis *Favorable*.

* Filtre

  * date de décision
  * type de dossier d'autorisation

* Tri

  * date de décision
  * date de dépôt

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * numéro de dossier
  * date de dépôt
  * date d'ouverture de chantier
  * date de demande
  * date achèvement
  * date prévue de recevabilité
  * destination des surfaces
  * petitionnaire principal
  * localisation
  * référence cadastrale
  * date de décision
  * shon
  * architecte
  * affectation_surface
  * nature des travaux
  * nature du financement
  * nombre de logements
  * autorité compétente
  * décision

.. note::

  * La saisie des dates et du type de dossier d'autorisation est obligatoire.

========================
dossier_detaillee_detail
========================

Dossiers de type CU.

* Filtre

  * date de décision

* Tri

  * date de décision
  * date de dépôt

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * numéro de dossier
  * date de dépôt
  * date d'ouverture de chantier
  * date de demande
  * date achèvement
  * date prévue de recevabilité
  * destination des surfaces
  * petitionnaire principal
  * localisation
  * référence cadastrale
  * date de décision
  * shon
  * architecte
  * affectation_surface
  * nature des travaux
  * nature du financement
  * nombre de logements
  * autorité compétente
  * décision

.. note::

  * La saisie des dates est obligatoire.
  * Les dossiers pour lesquels il n'y a pas eu de décision n'apparaîtront pas dans les résultats.

=========================
dossier_detaillee_refuses
=========================

Dossiers qui ont reçu un avis *Défavorable*.

* Filtre

  * date de décision
  * type de dossier d'autorisation

* Tri

  * date de décision
  * date de dépôt

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * numéro de dossier
  * date de dépôt
  * date d'ouverture de chantier
  * date de demande
  * date achèvement
  * date prévue de recevabilité
  * destination des surfaces
  * petitionnaire principal
  * localisation
  * référence cadastrale
  * date de décision
  * shon
  * architecte
  * affectation_surface
  * nature des travaux
  * nature du financement
  * nombre de logements
  * autorité compétente
  * décision

.. note::

  * La saisie des dates et du type de dossier d'autorisation est obligatoire.

==================
dossier_infraction
==================

Tous les dossiers dont le type de dossier d'autorisation est *Infraction*.

* Filtre

  * technicien affecté
  * arrondissement du terrain
  * date de réception

* Aucun choix de tri n'est proposé. Les dossiers sont classés automatiquement par date de réception puis par ordre alphabétique de leur référence.

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * N° de dossier
  * Contrevenant
  * Localisation
  * Arrondissement
  * Technicien
  * Date de transmission au parquet
  * Date de première visite

.. note::

  * La saisie des dates ainsi que la sélection du technicien et de l'arrondissement sont obligatoires.

============================
dossier_premiers_depots_dttm
============================

Tous les dossiers.

* Filtre

  * date de dépôt
  * type de dossier d'instruction

* Tri

  * date de dépôt

* Aucun choix de champ à afficher n'est proposé. Tous les champs suivants seront récupérés.

* Champs

  * N° de dossier
  * Date de dépôt
  * Pétitionnaire principal
  * Localisation

.. note::

  * La saisie des dates et du type de dossier d'instruction est obligatoire.
  * Les dossiers pour lesquels il n'y a pas eu de décision n'apparaîtront pas dans les résultats.

===============
dossier_recours
===============

Tous les dossiers dont le type de dossier d'autorisation est *Recours*.

* Filtre

  * type de procédure (contentieux / gracieux)
  * date de recours

* Aucun choix de tri n'est proposé. Les dossiers sont classés automatiquement par date de recours puis par ordre alphabétique de leur référence.

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * N° de dossier
  * Type de procédure
  * Date de recours
  * Pétitionnaire
  * Requérant
  * Juriste
  * Arrondissement
  * Nombre de logements
  * Nombre de logements sociaux

.. note::

  * La saisie des dates ainsi que la sélection du type de procédure sont obligatoires.

==================
dossier_simplifiee
==================

Tous les dossiers.

* Filtre

  * date de dépôt
  * type de dossier d'autorisation

* Tri

  * date de dépôt
  * année
  * version

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * numéro de dossier
  * date de dépôt
  * petitionnaire principal
  * localisation
  * shon
  * libellé de la destination
  * hauteur de la construction

.. note::

  * La saisie des dates et du type de dossier d'autorisation est obligatoire.

===========================
dossier_simplifiee_accordes
===========================

Dossiers qui ont reçu un avis *Favorable*.

* Filtre

  * date de décision
  * type de dossier d'autorisation

* Tri

  * date de décision
  * date de dépôt

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * numéro de dossier
  * date de décision
  * petitionnaire principal
  * localisation
  * shon
  * libellé de la destination
  * hauteur de la construction

.. note::

  * La saisie des dates et du type de dossier d'autorisation est obligatoire.

==========================
dossier_simplifiee_deposes
==========================

Dossiers en cours de type *Initial*.

* Filtre

  * date de dépôt
  * type de dossier d'autorisation

* Tri

  * date de dépôt

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * numéro de dossier
  * date de dépôt
  * petitionnaire principal
  * localisation
  * shon
  * libellé de la destination
  * hauteur de la construction

.. note::

  * La saisie des dates et du type de dossier d'autorisation est obligatoire.

==========================
dossier_simplifiee_refuses
==========================

Dossiers du type de dossier d'autorisation sélectionné qui ont reçu un avis *Défavorable*.

* Filtre

  * date de décision

* Tri

  * date de dépôt
  * date de décision

* Les champs suivants sont par défaut affichés. On peut les désélectionner un à un.

* Champs

  * numéro de dossier
  * date de dépôt
  * petitionnaire principal
  * localisation
  * shon
  * libellé de la destination
  * hauteur de la construction

.. note::

  * La saisie des dates est obligatoire.

==========================================
dossier_transmission_dttm_signature_prefet
==========================================

Dossiers du type de dossier d'instruction sélectionné.

* Filtre

  * date de retour de signature

* Aucun choix de tri n'est proposé. Les dossiers sont classés automatiquement par ordre alphabétique de leur référence.

* Aucun choix de champ à afficher n'est proposé. Tous les champs suivants seront récupérés.

* Champs

  * N° de dossier
  * date de retour signature
  * pétitionnaire principal
  * localisation

.. note::

  * La saisie des dates est obligatoire.
  * Les dossiers pour lesquels il n'y a pas eu de retour de signature du Préfet n'apparaîtront pas dans les résultats.

==================
statistiques_usage
==================

Ces statistiques évoluées permettent d'exporter les données de l'instruction de tous les dossiers.

* Filtre

  * date de dépôt
  * date de décision

* Aucun choix de tri n'est proposé. Les dossiers sont classés automatiquement par ordre alphabétique de leur référence.

* Aucun choix de champ à afficher n'est proposé. Tous les champs suivants seront récupérés.

* Champs

  * référence du dossier d'instruction
  * référence du dossier d'autorisation
  * commune du dossier
  * division du dossier
  * code du type de DA détaillé
  * libellé du type de DA détaillé
  * code du type de DI
  * libellé du type de DI
  * identifiant de l'instructeur
  * nom de l'instructeur
  * division de l'instructeur
  * direction de l'instructeur
  * date de dépôt
  * date de limite d'instruction
  * date de décision
  * état du dossier
  * nombre total d'événements d'instructions du dossier
  * nombre total de consultations du dossier
  * simulation de taxes (part communale)
  * simulation de taxes (part départementale)
  * simulation de taxes (total)

.. note::

  * La saisie des dates est facultative.
  * Si l'on filtre par date de décision, les dossiers pour lesquels il n'y a pas eu de décision n'apparaîtront pas dans les résultats.
  * Si l'utilisateur n'est pas rattaché à la communauté, seuls les dossiers de sa commune sont listés.

.. _reqmo_export_dia:

==========
export_dia
==========

Ces statistiques évoluées permettent d'exporter les données de l'instruction des déclarations d'intention d'aliéner (DIA).
Seulement les dossiers ayant une décision font partie de l'export.

* Filtre

  * date de décision

* Aucun choix de tri n'est proposé. Les dossiers sont classés automatiquement par ordre alphabétique de leur numéro de dossier.

* Les champs suivants sont par défaut affichés. Il est possible de les désélectionner.

* Champs

  * numéro de dossier
  * date de dépôt
  * demandeur
  * description du bien
  * surface construite au sol
  * surface utile ou habitable
  * usage
  * nombre de niveaux
  * nombre d'appartements
  * nombre d'autre locaux
  * vente en lot de volumes
  * vente en lot de volumes (précision)
  * locaux dans un batiment en copropriété
  * locaux dans un batiment en copropriété (précision)
  * en cas d'indivision, quote-part du bien vendu
  * références cadastrales
  * adresse du terrain : numéro de voie
  * adresse du terrain : voie
  * adresse du terrain : lieu-dit
  * adresse du terrain : localité
  * adresse du terrain : code postal
  * adresse du terrain : bp
  * adresse du terrain : cedex
  * prix de vente
  * acquéreur
  * commune de résidence de l'acquereur
  * état du dossier
  * collectivité (dans le cas où l'utilisateur est d'une collectivité de niveau 2)

.. note::

  * La saisie des dates de décision est facultative.
  * Si l'utilisateur n'est pas rattaché à la communauté, seuls les dossiers de sa commune sont listés.
  * Cette requête à besoin du paramètre :ref:`id_datd_filtre_reqmo_dossier_dia <parametrage_parametre_identifiants>`.
