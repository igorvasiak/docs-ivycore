======
NutGUI
======

A collection of custom fields to improve your custom editors. It has everything NutGUILayout has.

Overview
--------

    * :ref:`BigHeader`
    * :ref:`DrawTexture`
    * :ref:`Splitter`
    * :ref:`SubHeader`
    * :ref:`Get Help <**GET HELP**>`

**METHODS**
-----------

BigHeader
---------

* ``BigHeader(Rect rect, string title)``
* ``BigHeader(Rect rect, GUIContent content)``

Draws a big header identical to the BigHeader attribute.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public override void OnInspectorGUI()
        {
            Rect rect = EditorGUILayout.GetControlRect();
            NutGUI.BigHeader(rect, "A BIG TITLE!", "A smaller title.");
            // Some code...
        }
    }

IMAGE GOES HERE!

DrawTexture
-----------

* ``DrawTexture(Rect rect, Texture2D texture)``

Draws a texture within a rect.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        Texture2D _tex;

        public override void OnInspectorGUI()
        {
            Rect rect = EditorGUILayout.GetControlRect();
            rect.height = rect.width = 50f;
            NutGUI.DrawTexture(rect, _tex);
            // Some code...
        }
    }

IMAGE GOES HERE!

Splitter
--------

* ``Splitter(Rect rect)``
* ``Splitter(Rect rect, Color color)``

Draws a separator line on the screen within the given rect.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public override void OnInspectorGUI()
        {
            Rect rect = EditorGUILayout.GetControlRect();
            rect.height = 1f;
            NutGUI.Splitter(rect, Color.red);
            // Some code...
        }
    }

IMAGE GOES HERE!

SubHeader
---------

* ``SubHeader(Rect rect, string title)``
* ``SubHeader(Rect rect, GUIContent content)``

Draws a gray header identical to the SubHeader attribute.

.. code-block:: csharp
    :linenos:

    using NutEditor;
    using UnityEditor;
    using UnityEngine;

    [CustomEditor(typeof(MyClass))]
    public class MyClassEditor : Editor
    {
        public override void OnInspectorGUI()
        {
            Rect rect = EditorGUILayout.GetControlRect();
            NutGUI.SubHeader(rect, "A Sub Header");
            // Some code...
        }
    }

IMAGE GOES HERE!

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help from the community, suggest new features, and vote on future updates!

.. seealso::

    * :ref:`Attributes`
    * :ref:`NutGUILayout`
    * :ref:`NutGUIUtility`