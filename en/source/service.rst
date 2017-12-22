.. include:: termins.rst
.. _chapter_service:

Service
=======

Generally the app |bb| do not need any service. But when you notice
the app becomes slower service actions can help.

.. image:: images/service-010-select-actions.png
  :width: 25%
.. image:: images/service-020-select-service.png
  :width: 25%
.. image:: images/service-030-select-iitems.png
  :width: 25%

Shrinking database frees unused space, rebuilds the database file, repacking it into a minimal
amount of disk space. This contributes to speed up the app. Shrinking database runs
`VACUUM`_ command.

.. _`VACUUM`: https://sqlite.org/lang_vacuum.html

Shrinking does not affect to files that app contains except database.

Reindexing database is useful when you notice drastic drop in of the app performance.
Reindexing runs `REINDEX`_ command.

.. _`REINDEX`: https://sqlite.org/lang_reindex.html

.. warning::
  Do not forget making backups, especially before service. Ensure you remember encryption password if you have. Otherwise restoring data could be impossible.
