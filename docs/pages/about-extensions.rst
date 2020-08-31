==========
Extensions
==========

Extensions are a great way of extending classes and structs by artificially introducing methods into them. While they may look like local methods, they are actually static methods declared in another script.

Most of the extensions included in the Nut Library library are chainable. That means you can call many extensions for the same type in sequence, like this:

.. code-block:: csharp
    :linenos:

    using NutCore;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject[] array;

        public void MyMethod()
        {
            GameObject obj = array.SetActiveAll(false)
                                  .UnparentAll()
                                  .AtOrDefault(20);
        }
    }

Extensions are also a great way of bypassing boilerplate code. Many of the extensions in this library were created thinking of that. Boilerplate code is often the cause of bugs. Ideally, it should be avoided as much as possible. The main goal of Nut Library's extensions is not only to help to deal with boilerplate code but also to eliminate it completely.

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help from the community, suggest new features, and vote on future updates!

.. seealso::
    :maxdepth: 1

    extensions/array-and-list
    extensions/gameobject-and-component
    extensions/particlesystem
    extensions/physics
    extensions/value