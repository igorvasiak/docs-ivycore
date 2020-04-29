===========
Register<T>
===========

Register is a generic dictionary-based collection that facilitates entry management. A common use for it might be static register-oriented classes, such as for example ObjectArchetypeRegister from the Elery Object Pooler tool.. You might want to see how to create a static register.

You should be careful if you use the Register everywhere for the same reason as you should be careful with a Dictionary. I'm not saying not to do it, just that it might be a bit of a memory-intensive situation. Why to use a Register instead of a generic Dicitionary? It has dictionary management pre coded, has also the LastRetrieved property, which is basically a one-item history, and a GetMultiple method which retrieves multiple entries in an array.

Overview
--------

    * :ref:`Methods <**METHODS**>` 
        * :ref:`AddRegister <T AddRegister(string identifier, T item)>`
        * :ref:`Clear`
        * :ref:`Contains <bool Contains(string identifier)>`
        * :ref:`Get <T Get(string identifier)>`
        * :ref:`GetMultiple <T[] GetMultiple(params string[] identifiers)>`
        * :ref:`TryAddRegister <bool TryAddRegister(string identifier, T item)>`
        * :ref:`TryGet <bool TryGet(string identifier, out T item)>`
        * :ref:`TryGetMultiple <bool TryGetMultiple(string[] identifiers, out T[] item)>`
        * :ref:`TryUnregister <bool TryUnregister(string identifier, out T item)>`
        * :ref:`Unregister <T Unregister(string identifier)>`
    * :ref:`Properties <**PROPERTIES**>` 
        * :ref:`LastRetrieved <T LastRetrieved>`
        * :ref:`IsNull, IsEmpty, and IsNullOrEmpty <bool IsNull, bool IsEmpty, and bool IsNullOrEmpty>`
        * :ref:`Empty and Null` 

**METHODS**
-----------

T AddRegister(string identifier, T item)
----------------------------------------

AddRegister adds an item to the Register if the given key isn't there already and returns the provided item. It's an implementation of «Dictionary.Add()».

.. code-block:: csharp
    :linenos:
    
    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Start()
        {
            reg.AddRegister("some key", obj);
        }
    }

Clear
-----

Clears all references from the Register but the LastRetrieved property.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Start()
        {
            reg.Clear();
        }
    }

bool Contains(string identifier)
--------------------------------

Returns if the identifier provided is registered.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Update()
        {
            if (reg.Contains("some key"))
            {
                // Do stuff…
            }
        }
    }

T Get(string identifier)
------------------------

Returns the object associated to the identifier string if it is present inside the Register.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Update()
        {
            GameObject game_object = reg.Get("some key");
            if (game_object != null)
            {
                // Do stuff…
            }
        }
    }

T[] GetMultiple(params string[] identifiers)
--------------------------------------------

Returns an array with the objects associated to the provided identifiers that can be found inside the Register.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Update()
        {
            GameObject[] game_objects = reg.GetMultiple("some key", "another key");
            if (game_objects != null)
            {
                // Do stuff…
            }
        }
    }

bool TryAddRegister(string identifier, T item)
----------------------------------------------

TryAddRegister adds an item to the Register if the given key isn't there already and returns the success state of the operation. It's an implementation of «Dictionary.Add()».

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Start()
        {
            if (reg.TryAddRegister("some key", obj))
            {
                // Do stuff…
            }
        }
    }

bool TryGet(string identifier, out T item)
------------------------------------------

Gets the item relative to the identifier and returns the success state of the operation.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Start()
        {
            if (reg.TryGet("some key", out T g_obj))
            {
                // Do stuff…
            }
        }
    }

bool TryGetMultiple(string[] identifiers, out T[] item)
-------------------------------------------------------

Gets the items relative to the identifiers that exist and returns the success state of the operation.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Start()
        {
            string[] keys = new string[] { "some key", "another key" }
            if (reg.TryGetMultiple(keys, out GameObject[] objs))
            {
                // Do stuff…
            }
        }
    }

bool TryUnregister(string identifier, out T item)
-------------------------------------------------

Tries to remove an entry 

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void Start()
        {
            if (reg.TryUnregister("some key"))
            {
                // Do stuff…
            }
        }
    }

T Unregister(string identifier)
-------------------------------

Removes an item from the Register if the given key is available.  It's an implementation of «Dictionary.Remove»

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject obj;
        Register<GameObject> reg = new Register<GameObject>();

        void OnDestroy()
        {
            reg.Unregister("some key");
        }
    }

**PROPERTIES**
--------------

T LastRetrieved
---------------

It's the last item you retrieved from the register. It cannot be cleared or set. It returns default if no item has been retrieved so far.

bool IsNull, bool IsEmpty, and bool IsNullOrEmpty
-------------------------------------------------

Tell if the internal dictionary is null or empty.

Empty and Null
--------------

Empty and Null representations of Register.

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