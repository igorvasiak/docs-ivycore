==========
Extensions
==========

.. toctree::
    :titlesonly:

    extensions/array-and-list

Extensions are a great way of extending classes and structs by artificially introducing methods into them. While they may look like local methods, they are actually static methods declared in another script.

Most of the extensions included in the Ivy Core library are chainable. That means you can call many extensions for the same type in sequence, like this:

.. code-block:: csharp
    :linenos:

    using IvyCore;
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

Extensions are also a great way of bypassing boilerplate code. Many of the extensions in this library were created thinking of that. Boilerplate code is often the cause of bugs. Ideally, it should be avoided as much as possible. The main goal of Ivy Core's extensions is not only to help to deal with boilerplate code but also to eliminate it completely.