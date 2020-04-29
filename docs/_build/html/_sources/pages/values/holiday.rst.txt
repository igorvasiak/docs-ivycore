=======
Holiday
=======

Overview
--------

    * :ref:`Fields <**FIELDS**>`
    * :ref:`Methods <**METHODS**>`
        * :ref:`Get <Holiday Get(Holiday.Kind type)>`
        * :ref:`IsHoliday <bool IsHoliday(Holiday holiday)>`
    * :ref:`Properties <**PROPERTIES**>`
        * :ref:`Pre-Defined Holidays`
    * :ref:`Other Values <**OTHER VALUES**>`
    * :ref:`Get Help <**GET HELP**>`
    
**FIELDS**
----------

.. table::
    :widths: auto

    ====================   =========   ====================================================================================
    Type                   Name        Description
    ====================   =========   ====================================================================================
    string                 name        *The name of the Holiday.*
    Holiday.Kind           kind        *The kind of holiday. For example, if it is Custom, a Christmas, or Nothing at all.*
    Holiday.YearWrapMode   wrapMode    *Defines how the holiday will behave during the year.*
    System.DateTime        startDate   *The date at which the holiday starts.*
    System.DateTime        endDate     *The date at which the holiday ends.*
    ====================   =========   ====================================================================================

**METHODS**
-----------

Holiday Get(Holiday.Kind type)
------------------------------

Returns the Holiday that best corresponds the given HolidayType.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEditor;

    public class MyClass: MonoBehaviour
    {
        Holiday.Kind holidayKind = Holiday.Kind.Christmas;

        public void MyMethod()
        {
            Holiday holiday = Get(holiday); // Returns Holiday.Christmas.
            // Do something with "holiday" now...
        }
    }

bool IsHoliday(Holiday holiday)
-------------------------------

Verifies if a specific holiday is going on.

.. note::
    This method won't correctly capture an EndAndBeginning holiday whose startDate renders to a period possibly before the endDate.

    For example, a holiday that happens from April of this year and lasts to May of the next year won't behave properly.

    The same is true for a BeginningAndEnd holiday whose startDate is a period **after** the endDate.

    So, a holiday that happens from May of this year to April of the next year may not behave properly.

    And, when using no wrap, any holiday that crosses the New Year's Eve won't behave as either.

    An event from April of this year to May of the next year will be treated as an April to May of the same year event, and an event that ranges from December to January will just be discarded, because of how I'm handling holidays.

    I do have plans for future improvements to the overall Holiday behavior.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        Holiday holiday;

        public void MyMethod()
        {
            if (IsHoliday(holiday))
            {
                // Do something amazing!
            }
        }
    }

**PROPERTIES**
--------------

Pre-Defined Holidays
--------------------

.. topic:: Carnaval

    The true Carnaval is February the 24th and 25th. It here starts on February 20th, and ends on February 27th.

.. topic:: Christmas

    Christmas, the 25th of December, in this case has a one-month-long duration. It goes from December the 15th to January the 6th.

.. topic:: Easter

    Easter, originally the second Sunday of April, here lasts from April the 1st to April 30th.

.. topic:: Halloween

    Originally the 31th of October, it begins on the 20th of October and lasts until November the 10th.

.. topic:: KidsDay

    The 12th of October, it lasts from the 1st of October to the 15th of October.

.. topic:: NewYear

    The last night of the year to the dawn of the next, it here lasts eleven days. From the 26th of December to January the 6th.

.. topic:: StPatrickDay

    March the 17th, it here lasts from the 15th to the 31st of March.

.. topic:: Valentine

    Valentine, February the 14th, ranges from February the 10th to February the 17th.

****

**OTHER VALUES**
----------------

.. toctree::
    :maxdepth: 1

    holiday
    register

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!