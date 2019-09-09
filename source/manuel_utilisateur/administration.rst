.. _administration:

##############
Administration
##############

Libellés
########

.. _administration_collectivite:

=================
Les collectivités
=================

(:menuselection:`Administration --> Collectivité`)

Édition des collectivités présentes dans l'application.

.. _parametrage_parametre:

==============
Les paramètres
==============

(:menuselection:`Administration --> Paramètre`)

Édition des paramètres disponibles dans l'application.

Une convention de nommage existe. Il faut préfixer par :

* **ged\_** les paramètres spécifiques à la GED ;
* **erp\_** les paramètres spécifiques à ERP ;
* **option\_** les paramètres spécifiques aux options ;
* **id\_** les paramètres contenant un numéro d'identifiant ;
* **sig\_** les paramètres spécifiques au systeme d'information géographique ;
* **param_courriel_de_notification_commune\_** les paramètres spécifiques aux notifications par courriel aux communes ;
* **rapport_instruction\_** les paramètres spécifiques au rapport d'instruction.

Utilisation des options :

* **option_sig** : la valeur par défaut est *aucun*. Les valeurs possibles sont
  *sig_externe*, *sig_interne* ou *aucun*.
* **option_referentiel_arrete** : la valeur par défaut est *false*. Les valeurs 
  possibles sont *true* ou *false*.
* **option_localisation** : la valeur par défaut est *false*. Les valeurs possibles 
  sont *true* ou *false*.
* **option_erp** : la valeur par défaut est *false*. Les valeurs possibles sont 
  *true* ou *false*.
* **option_contrainte_di** : la valeur par défaut est *aucun*, exemple 
  d'utilisation "liste_groupe=g1,g2...;liste_ssgroupe=sg1,sg2...;service_consulte=t".
  Toutes les options sont optionnelles.
  Les options liste_groupe et liste_ssgroupe peuvent contenir une valeur unique 
  ou plusieurs valeurs séparées par une virgule, sans espace.
  La dernière option service_consulte permet d'ajouter une condition sur le champ
  du même nom. Il peut prendre t (Oui) ou f (Non) comme valeur.
* **option_afficher_division** : la valeur par défaut est *false*. Les valeurs 
  possibles sont *true* ou *false*.
* **option_arrondissement** : la valeur par défaut est *false*. Les valeurs 
  possibles sont *true* ou *false*.
  Cette option indique si la commune est divisée en arrondissements.
* **option_instructeur_division_numero_dossier** : la valeur par défaut est *false*. Les valeurs possibles sont *true* ou *false*. Cette option indique si le numéro de dossier tient compte de la division de l'instructeur auquel il est affecté.
* **option_portail_acces_citoyen** : permet d'activer ou de désactiver l'accès au :ref:`portail citoyen <portail_citoyen>`.
* **option_notification_piece_numerisee** : permet d'activer ou de désactiver l'ajout de :ref:`message de notification <instruction_dossier_message>`.
* **option_date_depot_demande_defaut** : permet d'afficher (*true*) ou non (*false*) la date du jour dans le champ de la date de dépôt lors de l'ajout d'une demande. La valeur par défaut est *true*.
* **option_simulation_taxes** : permet d'activer (*true*) ou non (*false*) :ref:`la simulation des taxes <instruction_simulation_taxes>` sur les dossiers d'instruction.
* **option_previsualisation_edition** : permet d'activer (*true*) ou non (*false*) :ref:`la prévisualisation des éditions <previsualisation_edition>` sur les événements d'instruction du dossier.
* **option_final_auto_instr_tacite_retour** : permet d'activer (*true*) ou désactiver (*false*) la finalisation automatique des instructions dites tacites (ajoutées automatiquement suite à des délais dépassés) ou dites retours (ajoutées automatiquement suite au suivi des dates).
* **option_ws_synchro_contrainte** : permet d'activer (*true*) ou désactiver (*false*) le :ref:`web service<web_services_ressource_maintenance_synchro_contrainte>` de synchronisation des contraintes depuis le SIG. 
* **option_trouillotage_numerique** : permet d'activer (*true*) ou désactiver (*false*) le trouillotage automatique des :ref:`pièces ajoutées à un dossier d'instruction<instruction_document_numerise_add>`. 
* **option_suppression_dossier_instruction** : permet d'activer (*true*) ou non (*false*) la suppression des dossiers d'instruction non instruits.
* **option_redaction_libre** : permet d'activer (*true*) ou non (*false*) la rédaction libre.

.. note::

  La suppression d'une option entraîne la désactivation des fonctionnalités liées 
  à l'option.

Utilisation des paramètres de notification :

* **param_courriel_de_notification_commune** : paramètre commune listant les adresses mails de notification (une par ligne).
* **param_courriel_de_notification_commune_objet_depuis_instruction** : paramètre communauté spécifiant l'objet du courriel.
* **param_courriel_de_notification_commune_modele_depuis_instruction** : paramètre communauté (écrasable par la commune) spécifiant le modèle du corps du courriel.


.. _parametrage_parametre_identifiants:

Utilisation des paramètres d'identification :

* **id_evenement_bordereau_avis_maire_prefet** : paramètre définissant l'identifiant de l'événement à appliquer aux dossiers d'instruction faisant l'objet d'un bordereau d'envoi des avis du Maire au Préfet, doit être paramétré sur la collectivité de niveau 2 pour une configuration multi-communes.
* **id_datd_filtre_reqmo_dossier_dia** : paramètre définissant l'identifiant du type détaillé de dossier d'autorisation des dossiers d'instruction à retourner dans la requête mémorisée de :ref:`l'exports statistique des DIA <reqmo_export_dia>`. Il est possible d'ajouter plusieurs valeur à condition qu'elles soient séparées par des virgules.
* **id_avis_consultation_tacite** : paramètre définissant l'identifiant de l'avis de consultation pour le caractère tacite. Notamment utilisé pour la récupération et l'identification des pièces recommandées lors de la :ref:`constitution du dossier final <instruction_document_numerise_constituer_dossier_final>`.
* **id_affichage_obligatoire** : paramètre définissant l'identifiant de l'événement d'instruction d'attestation d'affichage suite au dépôt. Cet événement est appliqué automatiquement sur tous les dossiers en cours lors de l'impression du registre d'affichage réglementaire et c'est son édition qui est retourné lors de l'impression d'attestation réglementaire. Il est également utilisé par l'action permettant d'afficher l'attestation d'affichage depuis la fiche d'un dossier d'instruction.

.. _parametrage_parametre_mails_services_consultes:

Configuration des mails envoyés automatiquement aux services consultés :

* **services_consultes_lien_interne** : contient un lien d'accès en interne à openADS qui sera affiché dans le mail.
* **services_consultes_lien_externe** : contient un lien d'accès en externe à openADS qui sera affiché dans le mail.

.. note::

  Il est possible de renseigner des variables de remplacement dans l'objet et le corps du courriel :

  * **<DOSSIER_INSTRUCTION>** pour le numéro du dossier (objet et corps) ;
  * **<ID_INSTRUCTION>** pour l'identifiant unique de l'événement d'instruction (corps uniquement) ;
  * **<URL_INSTRUCTION>** pour le lien direct vers l'événement d'instruction (corps uniquement).
  
  Dans certains cas de figure, l'adresse **<URL_INSTRUCTION>** ne fonctionne pas. Si vous ne souhaitez pas faire appel à la génération automatique du lien, il faut écrire manuellement :

  **<a href="** *[LIEN]* **">** *[LIEN]* **</a>**

  en remplaçant *[LIEN]* par :

  *[SITE_WEB]***/app/index.php?module=form&direct_link=true&obj=dossier_instruction&action=3&direct_field=dossier&direct_form=instruction&direct_action=3&direct_idx=<ID_INSTRUCTION>**

  où *[SITE_WEB]* est l'adresse de la racine du logiciel (par exemple https://openads.maville.fr).


Gestion Des Utilisateurs
########################

.. _administration_profil:

===========
Les profils
===========

(:menuselection:`Administration --> Gestion Des Utilisateurs --> Profil`)

Édition des profils présents dans l'application.

.. _administration_droit:

==========
Les droits
==========

(:menuselection:`Administration --> Gestion Des Utilisateurs --> Droit`)

Édition des droits présents dans l'application.

.. _administration_utilisateur:

================
Les utilisateurs
================

(:menuselection:`Administration --> Gestion Des Utilisateurs --> Utilisateur`)

Édition des utilisateurs présents dans l'application.

.. _administration_annuaire:

==========
L'annuaire
==========

(:menuselection:`Administration --> Gestion Des Utilisateurs --> Annuaire`)

Gestion des utilisateurs grâce à un LDAP.


Gestion de la confidentialité des dossiers
##########################################

Par défaut dans openADS, tous les dossiers sont visibles par tous les
utilisateurs, du moment que l'utilisateur est de la même collectivité que le
dossier ou si l'utilisateur est affecté à la collectivité de niveau 2.

Selon le besoin, il est possible d'avoir des dossiers dits confidentiels qui
sont ajoutables, consultables et modifiables seulement par certains utilisateurs
ou groupes d'utilisateurs.

Afin de rendre confidentiels certains dossiers, il faut d'abord paramétrer le 
:ref:`type de dossier de dossier d'autorisation <parametrage_dossiers_dossier_autorisation_type>`
comme confidentiel et choisir en tant que groupe le groupe d'utilisateurs qui
aura accès aux dossiers de ce type.
Chaque profil d'utilisateur est lié à un ou plusieurs groupes, avec un
paramètre définissant l'accès aux dossiers confidentiels de ces groupes. Si un
profil a accès aux dossiers confidentiels d'un groupe, alors tous les
utilisateurs avec ce profil auront accès aux dossiers confidentiels de ce groupe.
Il est également possible de redéfinir ces accès attribués à tous les
utilisateurs d'un profil, en paramétrant par utilisateur les groupes auxquels
il a accès. Cela permet d'ajouter ou de retirer des accès à un utilisateur en
particulier.

.. NOTE:: Le paramétrage de groupe par utilisateur prend entièrement le pas sur le paramétrage du profil. Du moment qu'un groupe a été ajouté à l'utilisateur, les groupes paramétrés sur le profil n'ont plus d'effet pour cet utilisateur. Chaque groupe auquel l'utilisateur a accès doit donc être ajouté à l'utilisateur.

Prenons en exemple le type de dossier d'autorisation "Déclaration d'intention
d'aliéner", lié au groupe ADS. En choisissant le paramètre confidentiel *Non*,
il sera alors visible par tous les utilisateurs.
Passons maintenant le paramètre confidentiel à *Oui*. Le dossier devient alors
seulement visible aux utilisateurs du groupe ADS ayant accès aux dossiers
confidentiels.
Disons que nous avons un profil *Instructeur* lié au groupe ADS (avec accès aux
dossiers confidentiels), et un profil *Visualisation DA et DI* qui est lié
au groupe ADS (sans accès aux confidentiels).
De fait, tous les utilisateurs avec le profil *Instructeur* pourront accéder aux
dossiers déclaration d'intention d'aliéner, mais pas les utilisateurs
*Visualisation DA et DI*.

Paramétrage par défaut du profil *Visualisation DA et DI* :

.. image:: administration_om_profil_groupe.png

Si on souhaite faire une exception pour un utilisateur ayant le profil
*Visualisation DA et DI*, on peut donner lui donner l'accès aux dossiers
confidentiels sans impacter les autres utilisateurs avec ce profil. Il suffit,
depuis le paramétrage de l'utilisateur, de le lier une nouvelle fois au groupe
ADS avec cette fois l'accès aux dossiers confidentiels de ce groupe. Ce
paramétrage du groupe directement par utilisateur prenant le pas sur le
paramétrage par profil, cet utilisateur pourra avoir accès aux dossiers DIA,
mais pas les autres utilisateurs avec le profil *Visualisation DA et DI*.

Illustration du paramétrage pour cet utilisateur :

.. image:: administration_om_utilisateur_groupe.png

.. NOTE:: Les groupes auxquels l'utilisateur est attaché sont visibles dans le widget :ref:`Infos profil<widget_infos_profil>`.

Tableaux de Bord
################


.. _administration_widget:

===========
Les widgets
===========

(:menuselection:`Administration --> Tableaux De Bord --> Widget`)

Un widget, contraction de window (fenêtre) et gadget, est un composant du
tableau de bord proposant des informations.

Son paramètrage nécessite la saisie de quatre champs :

* **libellé** : le titre du widget
* **type** : *file* lorsqu'il s'agit d'un script ou *web* lorsqu'il s'agit d'un
  appel à un web service
* **script** ou **lien** selon respectivement le type *file* ou *web* : nom du
  script ou URL du web service
* **arguments** ou **texte** selon respectivement le type *file* ou *web* :
  paramètres du script ou texte du widget (iframe, JavaScript, AJAX ...)

Seuls les widgets de type *file* sont utilisés dans openADS.

Les arguments sont déclarés ainsi :

::

  argument1=valeur1
  argument2=valeur2

Les scripts disponibles sont les suivants :

.. _administration_widget_consultation_retours:

consultation_retours
====================

Ce widget permet d'afficher le nombre de retours de consultation marqués comme 'non lu' pour les dossiers de l'utilisateur correspondant au filtre paramétrable. Un lien *Voir +* permet d'accéder au listing complet. Les informations fonctionnelles sont disponibles :ref:`ici<widget_consultation_retours>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*, *division* et *instructeur*

.. _administration_widget_commission_mes_retours:

commission_mes_retours
======================

Ce widget permet d'afficher le nombre de retours de commission marqués comme
'non lu' pour les dossiers de l'utilisateur correspondant au filtre
paramétrable. Un lien *Voir +* permet d'accéder au listing complet. Les
informations fonctionnelles sont disponibles
:ref:`ici<widget_commission_mes_retours>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*,
  *division* et *instructeur*

.. _administration_widget_dossiers_limites:

dossiers_limites
================

Ce widget permet d'afficher les dossiers d'instruction dont la date limite est dans moins de X jours. Seuls les 10 premiers résultats sont affichés. Un lien *Voir +* permet d'accéder au listing complet. Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossiers_limites>`.

Trois arguments facultatifs sont paramétrables :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*, *division* et *instructeur*
* **nombre_de_jours** [par défaut *15*] - délai en jours avant la date limite à partir de laquelle on souhaite voir apparaître les dossiers
* **codes_datd** [par défaut tous les types sont affichés] - liste des types de dossiers à afficher séparés par un point-virgule. exemple : *PCI;PCA;DPS;CUa;CUb*
* **restreindre_aux_tacites** [par défaut il n'y a pas de restriction concernant le caractère tacite] - prend comme valeur *true* (affiche seulement les dossiers d'instruction dont le caractère tacite est actif) ou *false* (pas de restriction concernant le caractère tacite)


.. _administration_widget_messages_retours:

messages_retours
================

Ce widget permet d'afficher le nombre de messages en attente de lecture pour les dossiers de l'utilisateur correspondant au filtre paramétrable. Un lien *Voir +* permet d'accéder au listing complet. Les informations fonctionnelles sont disponibles :ref:`ici<widget_messages_retours>`.

Deux arguments facultatifs sont paramétrables :

* **contexte** [par défaut *standard*] - les contextes disponibles sont *standard* et *contentieux*
* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*, *division* et *instructeur*


.. _administration_widget_dossiers_evenement_incomplet_majoration:

dossiers_evenement_incomplet_majoration
=======================================

Ce widget présente les dossiers les plus récents (10 max.) sur lesquels ont été appliqué un événement de majoration ou d'incomplétude avec une date d'envoi de lettre RAR renseignée pour cet événement, et dont la date de retour RAR de l'événement n'a pas été complétée. Un lien "Voir tous les dossiers évènement incomplet ou majoration sans RAR" permet d'accéder au listing complet. Les informations fonctionnelles sont disponibles  :ref:`ici<widget_dossiers_evenement_incomplet_majoration>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*, *division* et *instructeur*


.. _administration_widget_nouvelle_demande_nouveau_dossier:

nouvelle_demande_nouveau_dossier
================================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_nouvelle_demande_nouveau_dossier>`.

Un argument facultatif est paramétrable :

* **contexte** [par défaut *standard*] - les contextes disponibles sont *standard* et *contentieux*.


.. _administration_widget_dossier_contentieux_recours:

dossier_contentieux_recours
===========================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_recours>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun* et *instructeur*.


.. _administration_widget_dossier_contentieux_infraction:

dossier_contentieux_infraction
==============================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_infraction>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun* et *instructeur*.


.. _administration_widget_dossier_contentieux_contradictoire:

dossier_contentieux_contradictoire
==================================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_contradictoire>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*, *instructeur* et *division*.


.. _administration_widget_dossier_contentieux_ait:

dossier_contentieux_ait
=======================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_ait>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*, *instructeur* et *division*.


.. _administration_widget_dossier_contentieux_audience:

dossier_contentieux_audience
============================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_audience>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*, *instructeur* et *division*.


.. _administration_widget_dossier_contentieux_clotures:

dossier_contentieux_clotures
============================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_clotures>`.

Un argument facultatif est paramétrable :

* **filtre** [par défaut *instructeur*] - les filtres disponibles sont *aucun*, *instructeur* et *division*.


.. _administration_widget_dossier_contentieux_inaffectes:

dossier_contentieux_inaffectes
==============================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_inaffectes>`.

Deux arguments facultatifs sont paramétrables :

* **filtre** [par défaut *aucun*] - les valeurs disponibles sont *aucun* et *division* ;
* **dossier_encours** [par défaut *true*] - les valeurs disponibles sont :

    * *true* affiche seulement les infractions dont l'état est considéré comme en cours d'instruction ;
    * *false* affiche toutes les infractions.


.. _administration_widget_dossier_contentieux_alerte_visite:

dossier_contentieux_alerte_visite
=================================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_alerte_visite>`.

Deux arguments facultatifs sont paramétrables :

* **filtre** [par défaut *instructeur*] - les valeurs disponibles sont *aucun*, *instructeur* et *division* ;
* **dossier_encours** [par défaut *true*] - les valeurs disponibles sont :

    * *true* affiche seulement les infractions dont l'état est considéré comme en cours d'instruction ;
    * *false* affiche toutes les infractions.


.. _administration_widget_dossier_contentieux_alerte_parquet:

dossier_contentieux_alerte_parquet
==================================

Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_contentieux_alerte_parquet>`.

Deux arguments facultatifs sont paramétrables :

* **filtre** [par défaut *instructeur*] - les valeurs disponibles sont *aucun*, *instructeur* et *division* ;
* **dossier_encours** [par défaut *true*] - les valeurs disponibles sont :

    * *true* affiche seulement les infractions dont l'état est considéré comme en cours d'instruction ;
    * *false* affiche toutes les infractions.

.. _administration_widget_rss:

rss
===

Ce widget permet d’afficher X informations ayant pour origine X flux RSS 2.0.
Les informations fonctionnelles sont disponibles :ref:`ici<widget_rss>`.

Trois arguments sont paramétrables :

* **urls** - il est possible de renseigner un seul ou plusieurs urls, dans le cas de multiple urls alors les séparés par une virgule
* **mode** [par défaut *server_side*] - prend comme valeur server_side (Récupération du flux à partir du serveur Applicatif) ou client_side (Récupération du flux par le coté Client).
* **max_item** - prend comme valeur un nombre entier, détermine le nombre d'information que le widget affichera.


.. _administration_widget_dossier_consulter:

dossier_consulter
=================

Ce widget permet d’afficher les X derniers dossiers consultés.
Un lien *Voir +* permet d'afficher le listing complet de dossiers visité au sein du widget qui est limité à 20 dossiers.
Les informations fonctionnelles sont disponibles :ref:`ici<widget_dossier_consulter>`.

Un argument est paramétrable :

* **nb_dossiers** - prend comme valeur un nombre entier, determine le nombre de dossier affiché dans le widget. Par défaut il sera égale à 5. Le nombre maximal de dossier consultés visibles dans le widget est de 20.

.. _administration_widget_derniers_dossiers_deposes:

derniers_dossiers_deposes
=========================

Ce widget présente une métrique des derniers dossiers déposés correspondant aux paramètres définis.
Un lien *Voir +* permet d'afficher le listing complet des dossiers déposés, selon les paramètres du widget. 
Les informations fonctionnelles sont disponibles :ref:`ici<widget_derniers_dossiers_deposes>`.

Ce widget est par défaut affiché sur le tableau de bord des profils DIVISIONNAIRE. 

Les arguments suivants sont paramétrables :

* **nombre_de_jours** [par défaut *15*] - délai en jours avant la date du jour. Intervalle dans lequel est comprise la date de dépôt des dossiers qu'on souhaite prendre en compte.

* **codes_datd** [par défaut tous les types sont affichés] - liste des types de dossiers à afficher séparés par un point-virgule. exemple : *PCI;PCA;DPS;CUa;CUb*

* **filtre_depot** [par défaut *aucun*] - indique le type de dépôt dont sont issus les dossiers pris en compte par le widget. Les filtres disponibles sont *depot_electronique*, *guichet* et *aucun*.

* **filtre** [par défaut *division*] - les filtres disponibles sont *aucun*, *division* et *instructeur*.

* **restreindre_msg_non_lus** [par défaut *false*] - paramètre l'apparition de l'indicateur de message dans la colonne *message* du listing. *false*: si au moins un message manuel est présent sur le dossier. *true*: si au moins un message manuel NON LU est présent sur le dossier.


.. _administration_composition:

===========
Composition
===========

(:menuselection:`Administration --> Tableaux De Bord --> Composition`)

Menu de composition du tableau de bord des utilisateurs.

Options Avancées
################


.. _administration_sousetat:

==============
Les sous-états
==============

(:menuselection:`Administration --> Options Avancées --> Sous États`)

Les sous-états des requêtes SQL.

.. _administration_omrequete:

===============
Les requêtes om
===============

(:menuselection:`Administration --> Options Avancées --> Om Requête`)

Les requêtes SQL des éditions.

.. _administration_import:

===========
Les imports
===========

(:menuselection:`Administration --> Options Avancées --> Import`)

Import des données au format CSV.

(:menuselection:`Administration --> Options Avancées --> Import spécifique`)

Import spécifique
=================

Ce menu permet d'accéder au module d'import des données au format ADS 2007.

Depuis le formulaire :

- importer le fichier csv
- choisir le séparateur (, ou ;)
- valider le formulaire d'import

.. NOTE:: L'encodage du fichier csv à importer doit être ISO-8859-15.
          
          Seuls les séparateurs , ou ; sont admis.
          
          Les références cadastrales doivent être séparées par une virgule.
  
Une fois le chargement terminé un récapitulatif des traitements effectués est affiché, dans celui-ci un fichier de rejet est disponible.

.. NOTE:: Si dans un dossier une date de decision est définie mais qu'il n'a pas de nature de decision alors le dossier est implicitement accordé.
.. NOTE:: Le suffixe "P0" est ajouté à la fin de chaque numéro de dossier initial seulement si le suffixe est activé pour le type de dossier d'instruction importé.

Ce fichier de rejet contient toutes les lignes du csv importées qui sont en erreur. Les erreurs sont ajoutées en fin de ligne dans une nouvelle colonne.

Exemple d'erreurs typiques :

- Le code INSEE n'est pas paramétré : un code INSEE doit être défini pour chaque commune dans les paramètres.
- Dossiers non clôturés (pas de date d'accord/rejet/refus et de date de décision).
- Mauvais format des références cadastrales.
- Dossier avec date de décision mais pas de nature de décision.

Après correction ce ficher de rejet peut être ré-importé.

Des dossiers importés peuvent être mis à jour hors d'openADS, lors du prochain import les données du dossiers et des données techniques (CERFA) seront mises à jour. Attention, les demandeurs ne sont pas mis à jour.

Description des colonnes du CSV :

+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Colonne | Nom de la colonne                   | Type    | Obligatoire | Description                                                                                                                                                                                    | Choix possibles                                                                                                                                                                 |
+=========+=====================================+=========+=============+================================================================================================================================================================================================+=================================================================================================================================================================================+
| 1       | Type                                | texte   | Oui         | Code des types de dossiers d'autorisations                                                                                                                                                     | AZ, AT, AC, ST, CH, CX, CS, CA, DF, DT, MH, DP, CO, FA, IN, LT, NR, TP, PA, PC, PI, PD, RE, RD, SC, CI, CUb, CUa, DPS                                                           |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 2       | Numéro                              | texte   | Oui         | Identifiant du dossier                                                                                                                                                                         |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 3       | Initial                             | texte   | Non         | Identifiant du dossier initial                                                                                                                                                                 |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 4       | INSEE                               | entier  | Oui         | Code INSEE de la commune sur 5 caractères                                                                                                                                                      | Le code INSEE doit être paramétré pour chaque commune (Administration → Paramètres)                                                                                             |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 5       | Commune                             | texte   | Non         | Nom de la commune                                                                                                                                                                              | Les commune doivent être créées (Administration → Collectivité)                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 6       | Autonome                            | Oui/Non | Non         |                                                                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 7       | Projet                              | texte   | Non         | Description du projet d'urbanisme /!\ Attention : quelle que soit la nature de la DP/DPS (construction, démolition ou aménagement), ce texte se mettra dans la description de la construction. |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 8       | Destination                         | texte   | Non         | Affectation de la construction (choix multiples)                                                                                                                                               | Habitation, Hébergement hôtelier, Bureaux, Commerce, Artisanat, Industrie, Exploit. agricole ou forestière, Entrepôt, Service public ou d'intérêt général                       |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 9       | Nb logements                        | integer | Non         | Nombre de logements                                                                                                                                                                            |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 10      | Surface terrain                     | décimal | Non         | Surface du terrain                                                                                                                                                                             |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 11      | SHON existante                      | décimal | Non         | SHON existante                                                                                                                                                                                 |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 12      | SHON construite                     | décimal | Non         | SHON construite                                                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 13      | SHON transformation SHOB            | décimal | Non         | SHON transformation SHOB                                                                                                                                                                       |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 14      | SHON changement destination         | décimal | Non         | SHON changement destination                                                                                                                                                                    |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 15      | SHON démolie                        | décimal | Non         | SHON démolie                                                                                                                                                                                   |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 16      | SHON supprimée                      | décimal | Non         | SHON supprimée                                                                                                                                                                                 |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 17      | Architecte                          | Oui/Non | Non         | Soumis à architecte O/N                                                                                                                                                                        |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 18      | Demandeur                           | texte   | Oui         | Nom du demandeur                                                                                                                                                                               |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 19      | Opposition CNIL                     | Oui/Non | Non         |                                                                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 20      | Adresse demandeur                   | texte   | Non         | Adresse principale du demandeur                                                                                                                                                                | L'adresse du demandeur doit être de la forme : [adresse (90 caractères max)] [code postal (5 chiffre)] [commune (30 caractères max)]                                            |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 21      | Localisation                        | texte   | Non         | Adresse de la construction                                                                                                                                                                     | L'adresse doit être de la forme : [adresse (90 caractères max)] [code postal (5 chiffre)] [commune (30 caractères max)]                                                         |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 22      | Références cadastrales              | texte   | Non         | Références cadastrales (séparées par ",")                                                                                                                                                      | Format des références : 0 à 4 chiffres, 1 à 2 lettres (obligatoires), 1 à 4 chiffres (obligatoire). Chaque partie est séparée par un tiret. Exemple : 123-AA-0123, AB-0123, ... |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 23      | Lotissement                         | Oui/Non | Non         | Rattachement à un lotissement                                                                                                                                                                  |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 24      | AFU                                 | Oui/Non | Non         | Statut d'Association foncière urbaine                                                                                                                                                          |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 25      | Détail ZAC AFU                      | texte   | Oui         | Description opération d'aménagement de type AFU                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 26      | Autorité                            | texte   | Oui         | Code de l'autorité référente au dossier                                                                                                                                                        | COM, ETATMAIRE, ETAT                                                                                                                                                            |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 27      | Etat                                | texte   | Non         | État du dossier                                                                                                                                                                                | retire, annule, accepte_tacite, accepter, rejeter, Sursis_a_statuer, terminer, refuse_tacite, refuse                                                                            |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 28      | Centre instructeur                  | texte   | Non         | Centre instructeur                                                                                                                                                                             |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 29      | Instructeur                         | texte   | Non         | Nom de l'intructeur                                                                                                                                                                            |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 30      | Liquidateur                         | texte   | Non         | Nom du liquidateur                                                                                                                                                                             |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 31      | Complexité                          | texte   | Oui         | Niveau d'enjeu du dossier (Forte/Moyenne/Faible)                                                                                                                                               |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 32      | Dépôt en mairie                     | date    | Oui         | Date de dépôt en mairie                                                                                                                                                                        |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 33      | Réception DDE                       | date    | Non         | Date de réception par le service instructeur de la DDE                                                                                                                                         |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 34      | Complétude                          | date    | Non         | Date de réception des pièces complémentaires demandées                                                                                                                                         |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 35      | Notification majoration             | date    | Oui         | Date de notification de la majoration si dossier complet                                                                                                                                       |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 36      | DLI                                 | date    | Non         | Date limite d'instruction                                                                                                                                                                      |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 37      | Date envoi demande de pièces        | date    | Non         | Date envoi demande de pièces                                                                                                                                                                   |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 38      | Date notification demande de pièces | date    | Non         | Date notification demande de pièces                                                                                                                                                            |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 39      | Date envoi délai majoration         | date    | Non         | Date envoi délai majoration                                                                                                                                                                    |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 40      | Date notification délai majoration  | date    | Non         | Date notification délai majoration                                                                                                                                                             |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 41      | Service consulté                    | texte   | Non         | Services extérieurs consultés                                                                                                                                                                  |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 42      | Proposition service                 | texte   | Non         | Proposition du service consulté                                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 43      | Date proposition service            | date    | Non         | Date de proposition du service consulté                                                                                                                                                        |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 44      | Date transmission proposition       | date    | Non         | Date de transmission de l'arrêté du service instructeur                                                                                                                                        |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 45      | Date instruction terminée           | date    | Non         | Date instruction terminée                                                                                                                                                                      |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 46      | Date accord tacite                  | date    | Non         | Date accord tacite                                                                                                                                                                             |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 47      | Date de rejet tacite                | date    | Non         | Date de rejet tacite                                                                                                                                                                           |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 48      | Date de refus tacite                | date    | Non         | Date de refus tacite                                                                                                                                                                           |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 49      | Date de décision                    | date    | Oui         | Date de décision                                                                                                                                                                               |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 50      | Date notification décision          | date    | Non         | Date notification décision                                                                                                                                                                     |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 51      | Nature décision                     | texte   | Oui         | Nature de la décision                                                                                                                                                                          | Defavorable, Favorable, Annulation, Refus tacite, Sursis a statuer, Accord Tacite, Favorable avec Reserves, Rejet tacite, Annulation par tribunal                               |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 52      | Récolement                          | texte   | Non         |                                                                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 53      | DOC                                 | date    | Non         | Date de déclaration d'ouverture de chantier                                                                                                                                                    |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 54      | DAACT                               | date    | Non         | Date d'achèvement et de conformité des travaux                                                                                                                                                 |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 55      | Type Evolution                      | texte   | Non         | Type d'évolution de l'autorisation (Prorogation, Retrait à l'initative du pétitionnaire, Transfert)                                                                                            |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 56      | Statut Evolution                    | texte   | Non         | État de l'évolution en cours (Évolution en cours, Décision notifiée au demandeur)                                                                                                              |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 57      | Type dernières taxes                | texte   | Non         |                                                                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 58      | Statut dernières taxes              | texte   | Non         | Non taxable, Taxe initiale, Dégrèvement, Exonération, Procès verbal                                                                                                                            |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 59      | Type dernière RAP                   | texte   | Non         |                                                                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 60      | Statut dernière RAP                 | texte   | Non         | Non taxable, Taxe initiale, Dégrèvement, Exonération, Procès verbal                                                                                                                            |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 61      | EPCI                                | texte   | Non         |                                                                                                                                                                                                |                                                                                                                                                                                 |
+---------+-------------------------------------+---------+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+


.. _administration_generateur:

=============
Le générateur
=============

(:menuselection:`Administration --> Options Avancées --> Générateur`)

Le générateur de fichiers de l'application.

.. _administration_synchronisation_contrainte:

===============================
Synchronisation des contraintes
===============================

(:menuselection:`Paramétrage Dossiers --> Dossiers --> Synchronisation Des Contraintes`)

Le principe
===========

Ce menu permet de synchroniser les contraintes du SIG avec celles de l'application.
openADS va récupérer l'ensemble des contraintes du SIG, et les comparer avec les
contraintes déjà présentes dans la base de données de l'application, sur la base de leur
identifiant unique de contrainte. Les contraintes présentes sur le SIG ne seront pas
modifiées par openADS.
Les informations suivantes de la contrainte sont récupérées du SIG : 

* identifiant
* groupe
* sous-groupe
* libelle
* texte

.. image:: contrainte_synchronisation.png

* **X contrainte(s) ajoutée(s)** : Nombre de contraintes importées dans openADS à partir du SIG.
* **X contrainte(s) modifiée(s)** : Nombre de contraintes déjà présentes dans openADS, mises à jour avec les dernières informations du SIG.
* **X contrainte(s) archivée(s)** : Nombre de contraintes n'existant plus dans le SIG, archivées dans openADS.

Les contraintes référencées comme venant du SIG
===============================================

Lorsque des contraintes sont importées dans openADS via la synchronisation des
contraintes, elles sont marquées comme ayant été importées à partir du SIG (champ **Référence SIG** à *Oui*).

Quand on effectue une nouvelle synchronisation des contraintes, 3 cas de figure se
présentent :

* La contrainte existe sur le SIG mais pas dans openADS : elle est ajoutée.
* La contrainte existe sur le SIG ET dans openADS : les champs **libellé**, **groupe** et **sous-groupe** seront écrasés avec les valeurs du SIG, le **texte** est écrasé seulement si une valeur est renseignée dans le SIG.
* La contrainte n'existe plus sur le SIG, mais est toujours présente dans openADS : elle est archivée en mettant la date du jour de la synchronisation dans le champ **date de fin de validité**.

Les contraintes n'étant pas référencées comme venant du SIG
===========================================================

Les contraintes créées manuellement dans l'application ne sont pas référencées
comme provenant du SIG.

Quand une synchronisation des contraintes est lancée, ces contraintes sont ignorées et
restent dans le même état, même si elles ont le même groupe, sous-groupe, libellé ou texte 
qu'une contrainte importée du SIG. Des contraintes peuvent donc être en doublon.

.. _administration_geolocalisation_auto:

======================================================
Géolocalisation automatique des dossiers d'instruction
======================================================
(:menuselection:`Administration --> Options Avancées --> Géolocalisation des dossiers`)


Le principe
===========

Ce menu permet de lancer la géolocalisation automatique sur chacun des dossiers d'instruction vérifiant toutes les caractéristiques suivantes:

* il n'y a pas de parcelle temporaire sur le dossier d'instruction.
* aucune valeur n'est affectée au centroïde.

Dans ce cas là, la géolocalisation effectue un calcul de l'emprise puis un calcul du centroïde.

Ce procédé peut-être déclenché manuellement ou via un :ref:`web-service<web_services_ressource_maintenance_geolocalisation_auto>`.


L'utilisation
=============

Le formulaire affiche le nombre de dossier d'instruction à traiter.

Il suffit de cliquer sur le bouton pour lancer le traitement.

.. image:: administration_geolocalisation_auto.png


Les messages de retour
======================

A la fin du traitement, un message est affiché à l'utilisateur.

Il contient les éléments suivants, classés par collectivité:

* le nombre de dossiers traités avec succès ;
* le nombre de dossiers en erreur suite à :

  * une parcelle non-existante ;
  * le calcul de l'emprise impossible ;
  * le calcul du centroïde impossible.
