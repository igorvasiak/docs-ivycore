===================================
GameObject and Component Extensions
===================================

These extensions are quality of life features for Components and GameObjects. Currently there are only a few extensions, but in the future more features will make their way into Ivy Core. These extensions are chainable.

.. contents::

Parent and Unparent
-------------------

There are many variations of these extensions. They are chainable, as can be seen in the example below.

* **Parent(Transform parent)** - Sets the object's parent to «parent».
* **Unparent()** - Sets the object's parent to the scene of the root, which is essentially «null».
* **SetActive(bool state)** - Component-only. Sets the component GameObject's active state.
* **ParentAndSetActive(Transform parent, bool state)** - Sets both the object's parent and active state.
* **UnparentAndSetActive(bool state)** - Sets the object's parent to «null» and the active state to «state».

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        public Transform parent;

        void MyMethod()
        {
            obj.Parent(parent);
            this.Unparent(); // "this" is a component in this case (MyClass), so it's also possible to use extensions like this.
            obj.ParentAndSetActive(transform, false);
            obj.UnparentAndSetActive(true);
            parent.SetActive(true); // Transform is a component as well, so it's possible to call SetActive on it too.
            this.SetActive(false)
                .Parent(parent); // Chained command example.
        }
    }

CompareParent
-------------

bool CompareParent(GameObject/Component other) - Compares the parents of both objects and returns true if they match eachother.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;

        void MyMethod()
        {
            if (this.CompareParent(obj))
            {
                // Do stuff…
            }
        }
    }

Other Extensions
----------------

.. toctree::
    :titlesonly:

    Array and List Extensions <array-and-list>
    GameObject and Component Extensions <gameobject-and-component>
    ParticleSystem Extensions <particlesystem>
    Physics Extensions <physics>
    Value Extensions <value>

Get Help
--------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!