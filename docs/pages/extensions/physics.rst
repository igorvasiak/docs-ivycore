==================
Physics Extensions
==================

Overview
--------

    * :ref:`ClampVelocity`
    * :ref:`Get Help <GET HELP>`  

**EXTENSIONS**
--------------

ClampVelocity
-------------

* ``ClampVelocity(float min, float max)``
* ``ClampVelocity(Vector2 min, Vector2 max)`` - **Rigidbody2D-Only**
* ``ClampVelocity(Vector3 min, Vector3 max)`` - **Rigidbody-Only**

Clamps the Rigidbody's velocity. There are some variants for this method.

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

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!

.. seealso::
    
    * :ref:`Array and List Extensions <array-and-list>`
    * :ref:`GameObject and Component Extensions <gameobject-and-component>`
    * :ref:`ParticleSystem Extensions <particlesystem>`
    * :ref:`Texture Extensions <texture>`
    * :ref:`Value Extensions <value>`