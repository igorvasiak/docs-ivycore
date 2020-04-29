==================
Physics Extensions
==================

Overview
--------

    * :ref:`ClampVelocity`
    * :ref:`Other Extensions <OTHER EXTENSIONS>`
    * :ref:`Get Help <GET HELP>`  

**EXTENSIONS**
--------------

ClampVelocity
-------------

Clamps the Rigidbody's velocity. There are some variants for this method.

* **ClampVelocity(float min, float max)**
* **ClampVelocity(Vector2 min, Vector2 max)** - Rigidbody2D-only.
* **ClampVelocity(Vector3 min, Vector3 max)** - Rigidbody-only.

.. code-block:: csharp
    :linenos:
    
    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        Rigidbody rbody;
        Rigidbody2D rbody2d;

        void MyMethod()
        {
            // ...
            rbody.ClampVelocity(-3f, 3f);
            rbody2d.ClampVelocity(new Vector2(-3f, -5f), new Vector2(3f, 5f));
            // ...
        }
    }

****

**OTHER EXTENSIONS**
--------------------

.. toctree::
    :titlesonly:
    :maxdepth: 1

    Array and List Extensions <array-and-list>
    GameObject and Component Extensions <gameobject-and-component>
    ParticleSystem Extensions <particlesystem>
    Physics Extensions <physics>
    Value Extensions <value>

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!