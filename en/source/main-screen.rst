.. include:: termins.rst
.. _chapter_main_screen:

Главный экран
=============

Описание
--------

Главный экран |бб| содержит сводку по портфелям и счетам. Если в приложении используется несколько
типов портфелей, то на экране будет выведено несколько сводок. В примерах ниже рассматривается вариант с
одним типом портфеля |item_personal|.

В сводке отображаются остатки по каждому счету и всему портфелю в целом. Если для счета задан кредитный лимит,
то также отображается доступная сумма.

Ниже остатков расположены фактические и планируемые суммы расходов и доходов. Также отдельно выводятся суммы переводов,
если таковые были в выбранном периоде.

.. image:: images/mainscreen-010-main-screen.png
  :width: 25%
.. image:: images/mainscreen-014-main-screen-swipe-left.png
  :width: 25%
.. image:: images/mainscreen-015-main-screen-transactions.png
  :width: 25%


Кроме того, слева от набора сводок отображается список операций, в котором отображаются операции без разделения
на типы портфелей.

Выбор периода
-------------

Период можно изменить при помощи редактора периодов, который расположен в верхней части экрана. Редактор
поддерживает жесты перелистывания и выбора.

.. image:: images/mainscreen-089-main-screen-dates-range-swipe-left.png
  :width: 25%
.. image:: images/mainscreen-090-main-screen-dates-range-swipe.png
  :width: 25%
.. image:: images/mainscreen-100-main-screen-dates-range-spinner.png
  :width: 25%

Настройки
---------

Настройки сводки расположены в нижней части экрана. В настройках можно изменить группировку, заданную по умолчанию,
отредактировать фильтр и изменить период. В фильтре можно задать отбор по портфелям, счетам, валютам и отключить
отображение плана.

В следующем примере задается фильтр по счетам.

.. image:: images/mainscreen-020-main-screen-bottom-sheet-opening.png
  :width: 25%
.. image:: images/mainscreen-030-main-screen-bottom-sheet-open.png
  :width: 25%
.. image:: images/mainscreen-040-main-screen-filter.png
  :width: 25%

.. image:: images/mainscreen-050-main-screen-filter-account.png
  :width: 25%
.. image:: images/mainscreen-060-main-screen-filter-apply.png
  :width: 25%
.. image:: images/mainscreen-065-main-screen-filter-applied.png
  :width: 25%

Теперь на главном экране отображается только счет |item_cash|.

Сохранение настроек
-------------------

Измененные настройки можно сохранить для последующего использования. Для этого следует выбрать
|spinner_list_view_settings| и создать новую настройку. Значения фильтра будут автоматически
скопированы. Остается указать название настройки, например |value_summary_one_account|, и
нажать |button_save|.

.. image:: images/mainscreen-070-main-screen-select-new-setting.png
  :width: 25%
.. image:: images/mainscreen-080-main-screen-setting-save.png
  :width: 25%

Приложение позволяет иметь одновременно несколько сохраненных настроек и
при запуске загружает для главного экрана последнюю использованную настройку.
