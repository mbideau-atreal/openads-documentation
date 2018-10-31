.. _service_trouillotage_numerique:

#################################
Service de Trouillotage numérique
#################################


Lorsque :ref:`l'option correspondante <parametrage_parametre>` est activée, la configuration d'un service de trouillotage numérique permet l'utilisation du service sur les documents .PDF numérisés, avant leur stockage. 

Ainsi, à :ref:`l'ajout d'une pièce<instruction_document_numerise_add>`, le traitement de trouillotage est déclenché.



Configuration
#############

*Activation de l'option dans l'interface* :

L'option suivante permet d'activer l'option de trouillotage numérique à l'ajout d'un document numérisé.

om_parametre

- **option_trouillotage_numérique** -> true

.. _configuration_trouillotage_numerique:

*Configuration de l'URL du service de trouillotage* :


``dyn/services.inc.php``

.. code-block:: php

    //
    $STAMP_WS_URL_ = 'http://url_du_service_de_trouillotage/';

