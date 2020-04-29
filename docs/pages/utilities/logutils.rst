========
LogUtils
========

Overview
--------

    * :ref:`EditorLog`

**UTILITIES**
-------------

EditorLog
---------

These methods create messages only while running the game in the editor. That means if you try to use these logs in a build, they won't be logged.

* **EditorLog(string message, Object context)** - Logs a standard message to the console.
* **EditorLogWarning(string message, Object context)** - Logs a warning message to the console.
* **EditorLogError(string message, Object context)** - Logs an error message to the console.
* **EditorLogException(Exception exception, Object context)** - Logs an exception to the console.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public bool canMove;
        public Transform target;

        void MyMethod()
        {
            if (target == null)
            {
                IvyLogUtils.EditorLogError("Target is null, can't proceed with the operation!");
                return;
            }

            // Doing a thing...

            if (canMove)
            {
                // Do the thing...
            }
            else
                IvyLogUtils.EditorLogWarning("Can't move! Is this intentional behavior?");
        }
    }

****

**OTHER UTILITIES**
--------------------

.. toctree::
    :titlesonly:
    :maxdepth: 1

    IvyArrayUtils and IvyListUtils <arrayutils-and-listutils>
    IvyIOUtils <ioutils>
    IvyLogUtils <logutils>

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!