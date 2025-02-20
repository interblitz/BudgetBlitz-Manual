.. include:: termins.rst
.. _chapter_api:

Интеграция со сторонними приложениями
=====================================

|бб| можно интегрировать с другими приложениями. Например, можно совместить приложение с голосовым
ассистентом и просто надиктовывать операции или автоматизировать создание или заполнение новых операций при помощи
приложения `Tasker`_.

.. _`Tasker`: https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm

-------------------------------------
Создание операций из текстовой строки
-------------------------------------

Чтобы создать новую операцию в |бб| достаточно отправить широковещательный интент. Получив такой
интент, приложение проанализирует сообщение и создаст новую операцию по алгоритму, аналогичному распознавания SMS
и push-уведомлений.

Параметры интента:

Class = |var_intent_convert_text_to_transaction|

Extras:

#. |var_timestampMillis|: Тип long, дата и время новой операции в миллисекундах. Значение может быть не указано, тогда используются текущие дата и время.
#. |var_address|: Тип String, адресат сообщения, может быть не указан.
#. |var_message|: Тип String, текстовое сообщение, из которого приложение создаст новую операцию. Сообщение по своей структуре должно быть аналогично SMS. Обязательный параметр.

.. _sub_chapter_rest_api:

--------
REST API
--------

|бб| поддерживает `REST API`_. API позволяет создавать новые объекты, справочники и операции, а также редактировать и удалять существующие. Используя API
можно создавать свои дополнения и приложения.

.. _`REST API`: https://github.com/interblitz/BudgetBlitz-Api

Для работы с `REST API`_ и просмотра документации необходимо включить удаленный доступ, см. :ref:`chapter_remote_access`.
Документация к API доступна через `Swagger`_. После загрузки страницы в адресной строке `Swagger`_ укажите http://[server]:[port]/api/v1/docs.json.
В качестве сервера (server) и порта (port) необходимо указать значения, которые выводятся при включении удаленного доступа.

.. _`Swagger`: https://interblitz.github.io/BudgetBlitz-Api/swagger/

Примеры приложений можно посмотреть на `github.com`_. В примерах также нужно указать адрес к |бб| в виде http://[server]:[port].

.. _`github.com`: https://github.com/interblitz/BudgetBlitz-Api

-----------
Intents API
-----------

Помимо простого API для создания операций из текста |бб| предоставляет расширенный Intents API.
Intents API  состоит из двух частей, событий и запросов данных,.и построен на базе REST API.
По умолчанию Intents API выключен. В настройках можно указать, какая часть API должна быть включена.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Intents API: Часть 1, События
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

События возникают при записи элементов справочников и операций. При возникновении события |бб| отправляет интент тем пакетам,
которые указаны в настройках. В интенте передается:

Action = |var_action_api_event_ITEM_ONCHANGE|

Extras:

#. |var_collection| - наименование коллекции, для которой произошло событие
#. |var_id| - идентификатор объекта, для которого произошло событие

При импорте уведомлений в Extras дополнительно передаются

#. |var_notification| - текст уведомления
#. |var_address| - адрес уведомления (номер телефона или наименование пакета)
#. |var_amount| - сумма операции
#. |var_currency| - валюта операции

Для получения дополнительных данных, которых нет в интенте, следует отправить запрос.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Intents API: Часть 2, Запросы
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Для запроса данных следует отправить Intent:

Class = |var_intent_api_request|

Action = |var_action_api_request|

Extras:

#. |var_method| - одно из значений: GET, POST, DELETE
#. |var_path| - путь к данным
#. |var_body| - данные в формате JSON
#. |var_package| - полное имя пакета, которому следует вернуть ответ, если не указано - ответ не будет возвращен
#. |var_class| - класс пакета, которые примет ответ, можно не указывать.

Также в Extras можно указать любые дополнительные данные. Все заданные в запросе данные Extras вернутся обратно  в ответе.

В ответ на запрос отправляется Intent:

Action = |var_action_api_response|

Extras:

#. |var_collection| - наименование коллекции, для которой отправляется ответ
#. |var_response| - ответ в формате JSON

Параметры |var_method|, |var_path|, |var_body|, |var_collection|, |var_response| соответствуют REST API. Документация к ним доступна через `Swagger`_.
Подробней см. :ref:`sub_chapter_rest_api`.
