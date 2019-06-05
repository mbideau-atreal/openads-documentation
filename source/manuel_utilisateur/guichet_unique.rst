.. _guichet_unique:

##############
Guichet unique
##############

.. _guichet_unique_menu:

Le menu
#######

.. image:: guichet_unique_menu.png

.. _guichet_unique_nouvelle_demande:

Les nouvelles demandes
######################

==================
Saisir une demande
==================

Une demande peut être de deux natures différentes : elle peut concerner soit un
nouveau dossier ou soit un dossier existant.

.. image:: guichet_unique_nouvelle_demande_schema.png

.. _guichet_unique_nouvelle_demande_nouveau_dossier:

Pour un nouveau dossier
=======================

(:menuselection:`Guichet Unique --> Nouvelle demande --> Nouveau Dossier`)

La demande va donner lieu à la création d'un nouveau dossier d'autorisation.
La première étape est donc la sélection du type de dossier d'autorisation qui a
été déposé.
On sélectionne ensuite le type de dossier d'autorisation détaillé.
Enfin, on sélectionne le type de demande. 



.. _guichet_unique_nouvelle_demande_dossier_en_cours:

Pour un dossier en cours
========================

(:menuselection:`Guichet Unique --> Nouvelle demande --> Dossier en cours`)

La demande va se rattacher à un dossier d'autorisation en cours de traitement,
les dossiers affichés sont donc acceptés ou en cours d'instruction.
Après avoir sélectionné le dossier existant sur lequel on souhaite créer une nouvelle demande, on sélectionne le type de demande. 

.. _guichet_unique_liste_type_demande:

Liste des types de demande
==========================

Les types de demande proposés, en plus d'être filtrés sur le type de dossier d'autorisation détaillé (soit sélectionnés dans le cas d'une nouvelle demande, soit récupérés depuis le dossier d'instruction ciblé) sont récupérés de plusieurs façons défini dans le :ref:`paramétrage des types de dossier d'instruction<parametrage_dossiers_dossier_instruction_type>` et dans le :ref:`paramétrage des types de demande<parametrage_dossiers_demande_type>` :

* qui ne créé pas de nouveau dossier d'instruction et dont l'état du dossier d'instruction ciblé fait partie des états autorisés,
* qui créé de nouveau dossier d'instruction, dont l'état du dossier d'instruction ciblé fait partie des états autorisés et dont le dossier d'autorisation est accordé,
* qui créé de nouveau dossier d'instruction, dont les types des dossiers d'instruction en cours sur le dossier d'autorisation ciblé accordé, sont identiques à la liste des types de dossier d'instruction compatibles,
* qui créé de nouveau dossier d'instruction, dont les types des dossiers d'instruction en cours sur le dossier d'autorisation ciblé en cours d'instruction, sont identiques à la liste des types de dossier d'instruction compatibles et dont le dossier d'instruction initial n'est pas de compétence *commune*.

.. note::

    * L'identifiant de l'autorité compétente représentant *la commune* doit obligatoirement être **1**.
    * L'identifiant de l'état de dossier d'autorisation représentant *l'accord* doit obligatoirement être **2**.
    * L'identifiant de l'état de dossier d'autorisation représentant *l'instruction en cours* doit obligatoirement être **1**.


Saisie commune (nouveau dossier ou dossier existant) de la nouvelle demande
===========================================================================

Après la sélection du type de la demande,le reste de la saisie consiste en la saisie des informations suivantes :

* la date de la demande
* la ou les références cadastrales
* la localisation et la superficie du terrain
* le pétitionnaire principal 
* un éventuel délégataire
* le ou les éventuels co-demandeurs
* la présence ou non d'au moins une parcelle temporaire parmi la ou les référence(s) cadastrale(s) saisie(s)

Toutes les informations ne sont pas nécessairement disponibles pour la saisie,
en effet si la saisie concerne un nouveau dossier alors la saisie du
pétitionnaire est nécessaire alors que si la demande concerne un dossier
existant les informations du pétitionnaire sont déjà préremplies et il n'est
donc pas nécessaire de les saisir.

Sous le bloc **Demandeurs**, un bloc affiche la liste des documents obligatoires paramétrés pour le type de demande considéré (voir :ref:`parametrage_dossiers_demande_type` pour paramétrer cette liste de document).



.. _guichet_unique_nouvelle_demande_recepisse:

=====================
Imprimer un récépissé
=====================

(:menuselection:`Guichet Unique --> Nouvelle demande --> Récépissé`)

Lors de la validation de la nouvelle demande, si l'utilisateur n'a pas eu le
temps d'imprimer le récépissé de demande (car il a changé d'écran un peu
rapidement ou pour toute autre raison), cet écran permet de rechercher la
demande qui vient d'être saisie pour en imprimer le récépissé.

Recherche de la demande
=======================

Un listing de toutes les demandes permet de visualiser les informations
principales. Ce listing est trié par défaut par ordre décroissant de date de
demande donc les demandes du jour doivent apparaître en premier.


Visualisation de la demande et édition du récépissé
===================================================

Un écran récapitule les informations saisies lors de la demande et une action
est disponible dans le portlet d'action contextuelle pour permettre d'éditer le
récépissé.


.. _guichet_unique_nouvelle_demande_petitionnaire_frequent:

Le lien du récépissé de la demande ouvre le document depuis le stockage au format PDF.

===================================
Lister les pétitionnaires fréquents
===================================

(:menuselection:`Guichet Unique --> Nouvelle demande --> Pétitionnaire Fréquent`)

Il est possible d'ajouter un pétitionnaire redondant dans la liste des
pétitionnaires fréquents pour éviter de saisir ses informations à chaque nouvelle entrée,
en cochant le champ "Sauvegarder (pétitionnaire fréquent)" avant de valider.

Pour retrouver un pétitionnaire fréquent, il suffit de taper les trois premières 
lettres de son nom ou de son prénom dans les champs adéquats et de cliquer sur
l'îcone de la loupe "Chercher un pétitionnaire".


.. _guichet_unique_affichage_reglementaire:

L'affichage réglementaire
#########################

Dans les conditions prévues par arrêté du ministre chargé de l'urbanisme, un
affichage au public (aussi appelé registre) de tous les dossiers d'instruction
en cours est obligatoire. Le guichet unique doit pouvoir imprimer une
attestation de cet affichage réglementaire pour un dossier d'instruction
particulier à la demande d'un usager.

.. important::

   Pour l'administrateur : l'événement d'instruction créé sur chaque dossier
   qui permet de générer l'attestation d'affichage doit être paramétré, c'est
   l'identifiant de l'événement en question qui doit être paramétré dans
   l'enregistrement 'id_affichage_obligatoire' depuis l'écran 
   :menuselection:`Administration --> Paramètre`. Si le paramétrage ou
   l'événement n'existe pas alors un message prévient l'utilisateur :
   
   .. image:: guichet_unique_affichage_reglementaire_message_erreur_parametrage.png

.. _guichet_unique_affichage_reglementaire_registre:

====================
Imprimer le registre
====================

(:menuselection:`Guichet Unique --> Affichage Réglementaire --> Registre`)

Cet écran permet d'imprimer le registre d'affichage réglementaire des dossiers
d'instruction en cours. La validation de ce traitement ajoute sur chacun des
dossiers d'instruction concernés un événement d'instruction spécifique
(uniquement si c'est la première édition du dossier d'instruction) qui offre la
possibilité d'imprimer une attestation d'affichage.

.. image:: guichet_unique_affichage_reglementaire_registre_formulaire.png


.. _guichet_unique_affichage_reglementaire_attestation:

======================
Imprimer l'attestation
======================

(:menuselection:`Guichet Unique --> Affichage Réglementaire --> Attestation`)

Cet écran permet d'imprimer l'attestation d'affichage réglementaire d'un dossier
d'instruction. Pour le faire, il suffit de saisir le numéro du dossier
d'instruction dans le formulaire puis de cliquer sur le bouton valider.

.. image:: guichet_unique_affichage_reglementaire_attestation_formulaire.png

Une fois le formulaire validé, trois cas de figure sont possibles :

* soit l'identifiant saisi ne correspond à aucun dossier d'instruction existant :
  
  .. image:: guichet_unique_affichage_reglementaire_attestation_message_dossier_inexistant.png

* soit le dossier d'instruction existe mais ne possède pas d'attestation
  d'affichage :
  
  .. image:: guichet_unique_affichage_reglementaire_attestation_message_dossier_jamais_affiche.png

* soit le dossier d'instruction existe et possède une attestation d'affichage,
  on obtient alors un lien vers le fichier pdf de l'attestation permettant de
  l'imprimer :
  
  .. image:: guichet_unique_affichage_reglementaire_attestation_message_lien_attestation.png

Le lien de l'attestation d'affichage réglementaire d'un dossier d'instruction ouvre le document depuis le stockage au format PDF.
