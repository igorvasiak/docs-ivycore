========
LogUtils
========

Overview
--------

    * :ref:`EditorLog`
    * :ref:`Get Help <**GET HELP**>`

**UTILITIES**
-------------

EditorLog
---------

These methods create messages only while running the game in the editor. That means if you try to use these logs in a build, they won't be logged.

* ``EditorLog(string message, Object context)``
    * Logs a standard message to the console.
* ``EditorLogWarning(string message, Object context)``
    * Logs a warning message to the console.
* ``EditorLogError(string message, Object context)``
    * Logs an error message to the console.
* ``EditorLogException(Exception exception, Object context)``
    * Logs an exception to the console.

.. code-block:: csharp
    :linenos:

    using NutTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public bool canMove;
        public Transform target;

        void MyMethod()
        {
            if (target == null)
            {
                NutLogUtils.EditorLogError("Target is null, can't proceed with the operation!");
                return;
            }

            // Doing a thing...

            if (canMove)
            {
                // Do the thing...
            }
            else
                NutLogUtils.EditorLogWarning("Can't move! Is this intentional behavior?");
        }
    }

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help from the community, suggest new features, and vote on future updates!

.. seealso::

    * :ref:`NutArrayUtils and NutListUtils <arrayutils-and-listutils>`
    * :ref:`NutColorUtils <colorutils>`
    * :ref:`NutIOUtils <ioutils>`
    * :ref:`NutTextureUtils <textureutils>`