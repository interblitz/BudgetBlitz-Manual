.. include:: termins.rst
.. _chapter_import:

Импорт данных
=============

Настройки импорта уведомлений
-----------------------------

Настройки импорта уведомлений играют важную роль в процессе импорта уведомлений. Если банк меняет
структуру уведомлений, то вместе со структурой меняются и настройки импорта. В этом случае Вы можете
загрузить обновление настроек или отредактировать настройки самостоятельно, см. главу :ref:`chapter_notifications`.

.. image:: images/updateimporttunes-010-select-actions.png
  :width: 25%
.. image:: images/updateimporttunes-020-select-import.png
  :width: 25%
.. image:: images/updateimporttunes-030-select-import-sms-tunes.png
  :width: 25%

Для загрузки обновлений выберите пункт меню |menu_actions_import_sms_import_settings|.

.. image:: images/updateimporttunes-040-select-import-tunes-updated.png
  :width: 25%
.. image:: images/updateimporttunes-050-select-import-tunes-new.png
  :width: 25%
.. image:: images/updateimporttunes-060-select-import-tunes-no-updates.png
  :width: 25%

Приложение покажет доступные обновления. Здесь же можно загрузить настройки для новых банков.

.. image:: images/updateimporttunes-070-select-actions.png
  :width: 25%
.. image:: images/updateimporttunes-080-select-active_profile.png
  :width: 25%
.. image:: images/updateimporttunes-085-select-notifications.png
  :width: 25%

.. image:: images/updateimporttunes-090-check-use_exchange_when_wifi.png
  :width: 25%

Возможно, что приложение не покажет доступные настройки импорта уведомлений. В этом случае проверьте, что
в настройках включен обмен настройками импорта SMS.

SMS и Push уведомления
----------------------

По умолчанию |бб| автоматически импортирует SMS и Push уведомления. Тем не менее, в приложении есть возможность
в любой момент импортировать вручную SMS и push-уведомления. Для этого откройте справочник |meta_dir_sms|, |meta_dir_push| или
специальный диалог импорта:

#. Откройте диалог импорта.
#. Выберите счет, для которого нужно импортировать SMS. В счете должны быть указаны идентификатор и настройка импорта SMS.
#. Отметьте галочками SMS для импорта.
#. Нажмите |button_import|. Кнопка будет доступна, если есть отмеченные SMS.
#. Проверьте результат в списке операций.
#. Проблемы, возникшие при импорте, можно увидеть в журнале событий.

.. image:: images/manualsmsimport-010-select-actions.png
  :width: 25%
.. image:: images/manualsmsimport-020-select-import.png
  :width: 25%
.. image:: images/manualsmsimport-030-select-import-sms.png
  :width: 25%

.. image:: images/manualsmsimport-040-select-account.png
  :width: 25%
.. image:: images/manualsmsimport-050-move-next.png
  :width: 25%
.. image:: images/manualsmsimport-060-import-sms.png
  :width: 25%

.. image:: images/manualsmsimport-070-view-transactions.png
  :width: 25%
.. image:: images/manualsmsimport-080-view-events.png
  :width: 25%

CSV файлы
---------

Приложение |бб| может загрузить из файлов в формате |csv| операции и справочники
|meta_dir_accounts|, |meta_dir_categories|, |meta_dir_contractors|, |meta_dir_projects|, |meta_dir_persons| и |meta_dir_locations|.
Справочники могут быть загружены как из файла с операциями, так и из отдельного
файла.

Программа автоматически определяет разделитель колонок, который может быть одним из символов ";", ",", "|", "/", "\\".

Первая строка файла должна содержать имена колонок, регистр не имеет значения. Помимо этого, имена
колонок могут быть заданы в любой другой строке, тогда они будут иметь силу для последующих строк.

Имена колонок должны быть в списке имен, которые поддерживает приложение. Колонка, имя которой не поддерживается
приложением, игнорируется. Для справочников и операций списки различаются, и приведены ниже.

Справочники
~~~~~~~~~~~

Возможен импорт справочников |meta_dir_accounts|, |meta_dir_categories|, |meta_dir_contractors|, |meta_dir_projects|, |meta_dir_persons| и |meta_dir_locations|.
Поддерживается импорт древовидных данных, для этого полный путь к элементу должна быть указан в колонке Name с разделителем "/", "\\" или другим.
Сам разделитель можно указать в диалоге импорта. Например, из строки:

  Расходы/Прочие

будут созданы группа Расходы и элемент Прочие, принадлежащий группе Расходы.

Поддерживаются имена колонок (если в таблице указано несколько имен, то в файле должно
использоваться только одно из перечисленных в таблице):

.. list-table:: Формат CSV файла с элементами справочника
   :widths: 7 5 30
   :header-rows: 1

   * - Имя
     - Обязательный
     - Комментарий
   * - Name
     - Да
     - Имя справочника
   * - Comment, Note
     - Нет
     - Примечание
   * - Currency
     - Нет
     - Валюта (только для счетов)
   * - Balance
     - Нет
     - Начальный остаток (только для счетов)


Если строка не содержит обязательных колонок, или значение обязательной колонки не задано, то такая строка будет пропущена.

Пример файла::

  "Name";"Comment"
  "Расходы";
  "Расходы\Прочие";
  "Расходы\Прочие\Ремонт"; "Прочий ремонт"


Операции
~~~~~~~~

Возможен импорт фактических и плановых операций, сплитов, а также переводов. В последнем случае из одной
строки файла создаются две операции. Названия элементов справочников можно указывать с учетом иерархии, например:

  Расходы/Прочие

При импорте операции с такой категорией дополнительно будут найдены или созданы группа Расходы и элемент Прочие,
принадлежащий группе Расходы.

По-умолчанию, без изменения CSV файла, поддерживается импорт файлов, созданных в приложениях:

* AbilityCash
* AnMoney
* Bluecoins
* Financisto
* Дзен-мани
* Handy Money
* Cash Organizer (расширение файла txt)
* 1C: Деньги (`Обработка для выгрузки справочников и операций <https://github.com/interblitz/BudgetBlitz-Manual/releases/download/import/bz1CMoneyExport_v1_00.epf>`_)

Поддерживаются имена колонок (если в таблице указано несколько имен, то в файле должно
использоваться только одно из перечисленных в таблице):

.. list-table:: Формат CSV файла с операциями
   :widths: 7 5 30
   :header-rows: 1

   * - Имя
     - Обязательный
     - Комментарий
   * - id
     - Нет
     - Идентификатор операции, если указан, то будет выполнен поиск существующей операции
   * - account, incomeAccountName, Income account, Счёт, Счет
     - Да
     - Наименование или номер счета
   * - date, Дата
     - Да
     - Дата в одном из форматов, см. :ref:`chapter_app_supported_formats`
   * - time
     - Нет
     - Время в одном из форматов, см. :ref:`chapter_app_supported_formats`
   * - amount, income, Income amount, Сумма, Amount Split, Сумма сплита
     - Да
     - Сумма операции (может содержать валюту и разделители групп разрядов), десятичный разделитель может быть точкой или запятой, может быть суммой в валюте операции или суммой в валюте счета
   * - original amount, Сумма в валюте операции
     - Нет
     - Сумма в валюте операции, если указана, то курс операции вычисляется автоматически
   * - rate, exchange rate, Обменный курс
     - Нет
     - Курс операции
   * - currency, incomeCurrencyShorttitle, Валюта
     - Нет
     - Валюта операции, если не указано, то используется в валюта счета, может быть валютой счета или валютой операции
   * - original currency, Валюта операции
     - Нет
     - Валюта операции
   * - payer, payee, contractor, контрагент, получатель
     - Нет
     - Наименование плательщика или получателя платежа
   * - category, categoryName, Категория
     - Нет
     - Наименование категории
   * - project
     - Нет
     - Наименование проекта
   * - person, unit
     - Нет
     - Наименование персоны/подразделения
   * - location, place
     - Нет
     - Наименование места
   * - notes, note, comment, Примечания, Note Split, Примечание сплита
     - Нет
     - Примечание
   * - planned, plan
     - Нет
     - Фактическая (0), или плановая (1) операция. Если колонка не задана, создается фактическая операция
   * - detail, split
     - Нет
     - Операция (0), или детализация операции (1). По умолчанию используется значение 0
   * - Тип
     - Нет
     - Знак операции, если не указан, знак определяется суммой
   * - Х
     - Х
     - Вторая операция из одной строки
   * - outcomeAccountName, Expense account
     - Да
     - Счет
   * - outcome, Expense amount
     - Да
     - Сумма
   * - outcomeCurrencyShorttitle
     - Нет
     - Валюта

Если строка не содержит обязательных колонок, или значение обязательной колонки не задано, то такая
строка будет пропущена.

Если строка содержит не все обязательные колонки, но при этом задано значение обязательной колонки amount, то такая
строка считается детализацией операции и приложение создает сплит.

Сплит прикрепляется к последней строке, которая не является сплитом.

Для справочников |meta_dir_accounts|, |meta_dir_categories|, |meta_dir_contractors|, |meta_dir_projects|, |meta_dir_persons| и |meta_dir_locations|
поддерживается импорт древовидных данных, для этого полный путь к элементу должен быть указан в наименовании с разделителем "/", "\\" или другим.
Разделитель можно указать в диалоге импорта.

Пример файла, сформированного в приложении AbilityCash::

  "Executed";"Locked";"Date";"Balance correction";"Income account";"Income amount";"Income balance";"Expense account";"Expense amount";"Expense balance";"Comment";
  "+";;01.11.2021 09:00:00;"+";"Card 1234";500;100;;;;"Some notes";

Пример файла, сформированного в приложении Bluecoins::

  "Тип,""Дата"",""Установить время"",""Название"",""Сумма"",""Валюта"",""Обменный курс"",""Название группы категорий"",""Категория"",""Счёт"",""Примечания"",""Ярлыки"",""Статус"""
  "Доход,""2021-11-01 11:00:00"",""11:00"",""-"",""500,0"",""UAH"",""1,0000000000"",""Работа"",""Разное"",""Card"","""  ","",Нет"""

Пример файла со сплитами без колонки detail::

  "id";"date";"time";"account";"amount";"currency";"original amount";"original currency";"category";"parent";"payee";"location";"project";"note"
  "1213";"2021-11-01";"04:04:00";"Card";"-800.00";"SEK";"";"";"SPLIT";"";"Магазин";"";"No project";""
  "1214";"~";"";"Card";"-400.08";"SEK";"";"";"Food";"";"Магазин";"";"No project";"Еда"
  "1215";"~";"";"Card";"-400.68";"SEK";"";"";"Goods";"";"Магазин";"";"No project";"Хозтовары"

Пример файла со сплитами с колонкой detail::

  "id";"date";"time";"account";"amount";"currency";"original amount";"original currency";"category";"parent";"payee";"location";"project";"note";"detail"
  "1213";"2021-11-01";"04:04:00";"Card";"-800.00";"SEK";"";"";"SPLIT";"";"Магазин";"";"No project";"";"0"
  "1214";"2021-11-01";"";"Card";"-400.00";"SEK";"";"";"Food";"";"Магазин";"";"No project";"Еда";"1"
  "1215";"2021-11-01";"";"Card";"-400.00";"SEK";"";"";"Goods";"";"Магазин";"";"No project";"Хозтовары";"1"

Для импорта:

#. Откройте диалог импорта.
#. Выберите файл для импорта.
#. Нажмите |button_next| и отметьте галочками строки для импорта.
#. Нажмите |button_import|. Кнопка будет доступна, если есть отмеченные строки.
#. Проверьте результат в списке операций.
#. Проблемы, возникшие при импорте, можно увидеть в журнале событий.

.. image:: images/csvimport-030-select-import-csv.png
  :width: 25%
.. image:: images/csvimport-040-select-file-and-options.png
  :width: 25%

OFX файлы
---------

|бб| поддерживает импорт |OFX| файлов. Поддерживается спецификация начиная с версии 2.1.1. Для импорта:

#. Откройте диалог импорта.
#. Выберите файл для импорта.
#. Нажмите |button_next| и отметьте галочками строки для импорта.
#. Нажмите |button_import|. Кнопка будет доступна, если есть отмеченные строки.
#. Проверьте результат в списке операций.
#. Проблемы, возникшие при импорте, можно увидеть в журнале событий.

.. image:: images/ofximport-030-select-import-ofx.png
  :width: 25%
.. image:: images/ofximport-040-select-file-and-options.png
  :width: 25%

Электронные чеки
----------------

|бб| поддерживает импорт электронных чеков. Возможен импорт чеков:

#. В формате JSON из приложения Проверка чеков ФНС России (возможен импорт одного чека или набора чеков).
#. В формате JSON по ссылке на https://consumer.oofd.kz (Казахстан, ОФД Казахтелеком).
#. http-ссылки на чеки в формате HTML в сервисе platformaofd.ru (авторизация не требуется).
#. Из текста электронного письма Ozon с чеком. Возможно объединение чеков по одному заказу.
#. Из QR кода на бумажном чеке. В этом случае будет создана операция на сумму и дату, указанные в QR коде. QR код необходимо сканировать и распознать в любом стороннем приложении.
#. В формате XML из личного кабинета на cabinet.tax.gov.ua для Украины.
#. Из сервиса распознавания чеков www.eagle-doc.com.

Для импорта из сторонних приложений:

#. Откройте стороннее приложение.
#. Выберите нужные данные, нажмите Поделиться / Отправить / Передать или другую подобную по смыслу кнопку.
#. В качестве получателя укажите |бб|.
#. Далее следуйте инструкциям на экране.

Для импорта из буфера обмена:

#. Откройте диалог импорта.
#. Скопируйте данные из буфера обмена в диалог.
#. Далее следуйте инструкциям на экране.

Проблемы, возникшие при импорте, можно увидеть в журнале событий.
