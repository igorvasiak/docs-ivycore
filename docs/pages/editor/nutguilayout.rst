============
NutGUILayout
============

Overview
--------

    * :ref:`BigHeader`
    * :ref:`BigTitleLabel`
    * :ref:`GrayTitleLabel`
    * :ref:`RangeArrayField`
    * :ref:`SplitHeader`
    * :ref:`Splitter`
    * :ref:`SubHeader`
    * :ref:`TitleLabel`
    * :ref:`TopHeader`
    * :ref:`Get Help <**GET HELP**>`

**METHODS**
-----------

BigHeader
---------

* ``BigHeader(string title)``
* ``BigHeader(GUIContent content)``

Draws a big header identical to the BigHeader attribute.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            NutGUILayout.BigHeader("A Big Title");
            // ...
        }
    }

BigTitleLabel
-------------

* ``BigTitleLabel(string text, string subtitle = null)``
* ``BigTitleLabel(GUIContent content, GUIContent subtitle = null)``

Draws a big-sized title label.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            NutGUILayout.BigTitleLabel("A Big Title", "A Smaller Title");
            // ...
        }
    }

GrayTitleLabel
--------------

* ``GrayTitleLabel(string text, params GUILayoutOptions[] options)``
* ``GrayTitleLabel(GUIContent content, params GUILayoutOptions[] options)``

Draws a small gray-colored title label.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            NutGUILayout.BigHeader("A Big Title");
            // ...
        }
    }

RangeArrayField
---------------

* ``RangeArrayField(string label, ref float[] value, float min, float max, float standard)``

Draws a non-reorderable array of floats as ranges.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            MyClass my_class = target as MyClass;
            NutGUILayout.RangeArrayField("Array", my_class.percentages, 0f, 100f, 50f);
            // ...
        }
    }

SplitHeader
-----------

* ``SplitHeader(string leftText, float leftTextWidth, string rightText)``

Draws a double-sided header with two titles.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            NutGUILayout.SplitHeader("A Big Title", 180f, "A Smaller Title");
            // ...
        }
    }

Splitter
--------

* ``Splitter(Color color)``
* ``Splitter(float thickness = 1)``
* ``Splitter(float thickness, Color color)``
* ``Splitter(float xOffset, float thickness, Color color)``

Draws a separator line on the screen.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            // ...
            NutGUILayout.Splitter();
            // ...
        }
    }

SubHeader
---------

* ``SubHeader(string title)``
* ``SubHeader(GUIContent content)``

Draws a small header identical to the SubHeader attribute.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            NutGUILayout.SubHeader("A Small Title");
            // ...
        }
    }

TitleLabel
----------

* ``TitleLabel(string text, params GUILayoutOptions[] options)``
* ``TitleLabel(GUIContent content, params GUILayoutOptions[] options)``

Draws a medium-sized title lable.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            NutGUILayout.BigHeader("A Title");
            // ...
        }
    }

TopHeader
---------

* ``TopHeader(string header, string subtitle = null)``

Draws a small title and a small subtitle (if any) over a light background.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public void OnInspectorGUI()
        {
            NutGUILayout.TopHeader("A Top Title", "A Top Subtitle");
            // ...
        }
    }

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help from the community, suggest new features, and vote on future updates!

.. seealso::

    * :ref:`NutGUI`
    * :ref:`NutGUIUtility`