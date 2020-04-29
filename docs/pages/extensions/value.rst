================
Value Extensions
================

Mathematics-oriented extensions that allow for better vector logic, distance and direction calculation out of the box, castless conversion between vectors and much more. All extensions here are chainable.

Overview
--------

    * :ref:`Add and Sub`
    * :ref:`ClosestPoint`
    * :ref:`Dir and Dist`
    * :ref:`InversePoint`
    * :ref:`Logic`
    * :ref:`ToVec`
    * :ref:`WithX/Y/Z/W`
    * :ref:`Other Extensions <**OTHER EXTENSIONS**>`
    * :ref:`Get Help <**GET HELP**>`

**EXTENSIONS**
--------------

Add and Sub
-----------

* **Add(int/float/double/decimal v)** - Adds the value (v) to all parameters of the vector.
* **Sub(int/float/double/decimal v)** - Subtracts the value (v) drom all parameters of the vector.

Add and Sub are available to all vectors, including VectorInts.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        void MyMethod()
        {
            Vector2 vec2 = new Vector2(1f, 1f);
            vec2.Add(2f);
            vec2.Sub(2f);
        }
    }

ClosestPoint
------------

Returns the closest point in an array of floats, ints, and vectors.

* **ClosestPoint(params Vector4[] points)**
* **ClosestPoint(params Vector3[] points)**
* **ClosestPoint(params Vector3Int[] points)**
* **ClosestPoint(params Vector2[] points)**
* **ClosestPoint(params Vector2Int[] points)**
* **ClosestPoint(params int[] points)**
* **ClosestPoint(params float[] points)**
* **ClosestPoint(params double[] points)**
* **ClosestPoint(params decimal[] points)**

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public Transform[] objs;

        void MyMethod()
        {
            3f.ClosestPoint(-3f, 5f); // Returns 5.
            transform.ClosestPoint(objs); // Returns the closest transform.
        }
    }

Dir and Dist
------------

* **Dir, Dir2, and Dir4(other)** - Dir methods return the direction from point a to b (non normalized).
* **Dist, Dist2, and Dist4(other, bool sqr = true)** - Dist methods return the square distance between two points.

You can call them from components, vectors, and GameObjects.

.. code-block:: csharp
    :linenos:
    
    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public GameObject other;

        void MyMethod()
        {
            float sqr_dist = this.Dist(other);
            float dist = this.Dist(other, false); // False forces the method to return the true distance.
            Vector3 dir = this.Dir(other);
        }
    }

InversePoint
------------

* **InversePointUp()** - transform.InverseTransformPoint(transform.up)
* **InversePointDown()** - transform.InverseTransformPoint(-transform.up)
* **InversePointRight()** - transform.InverseTransformPoint(transform.right)
* **InversePointLeft()** - transform.InverseTransformPoint(-transform.right)
* **InversePointForward()** - transform.InverseTransformPoint(transform.forward)
* **InversePointBackward()** - transform.InverseTransformPoint(-transform.forward)

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public Transform[] transforms = new Transform[0];

        void MyMethod()
        {
            Vector3 inverse_up = transform.InversePointUp();
        }
    }

Logic
-----

* **bool GreaterAny(this Vector a, Vector b)** - Returns if any axis from a is greater than any axis from b.
* **bool LessAny(this Vector a, Vector b)** - Returns if any axis from a is lesser than any axis from b.
* **bool GreaterAll(this Vector a, Vector b)** - Returns if all axis from a are greater than all axis from b.
* **bool LessAll(this Vector a, Vector b)** - Returns if all axis from a are lesser than all axis from b.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {       
        void MyMethod()
        {
            Vector3 a = new Vector3(5f, 6f, 1f);
            Vector3 b = new Vector3(6f, 2f, 3f);
            a.GreaterAny(b); // Returns true.
            b.LessAll(a); // Returns false.
        }
    }

ToVec
-----

Converts values to vectors, and vectors into other vectors.

To Vector 4

* **ToVec4(this Vector3 vec, float w)** - Returns a Vector4 with the xyz fields from vec's values and w field from, well, w. It defaults to zero.
* **ToVec4(this Vector3Int vec, float w)** - Returns a Vector4 with the xyz fields from vec's values and w field from, well, w. It defaults to zero.
* **ToVec4(this Vector2 vec, float z, float w)** - Returns a Vector4 with the xy fields from vec's values and zw field from z and w. It defaults both to zero.
* **ToVec4(this Vector2Int vec, float z, float w)** - Returns a Vector4 with the xy fields from vec's values and zw field from z and w. It defaults both to zero.
* **ToVec4(this decimal v)** - Returns a Vector4 with the xyzw fields set to v.
* **ToVec4(this double v)** - Returns a Vector4 with the xyzw fields set to v.
* **ToVec4(this float v)** - Returns a Vector4 with the xyzw fields set to v.
* **ToVec4(this byte v)** - Returns a Vector4 with the xyzw fields set to v.
* **ToVec4(this int v)** - Returns a Vector4 with the xyzw fields set to v.
 

To Vector 3

* **ToVec3(this Vector4 vec)** - Returns a Vector3 with the xyz fields from vec's xyz and discards w.
* **ToVec3(this Vector3Int vec)** - Returns a Vector3 with the xyz fields from vec's values.
* **ToVec3(this Vector2 vec, float z)** - Returns a Vector3 with the xy fields from vec's values and z field from z . It defaults to zero.
* **ToVec3(this Vector2Int vec, float z)** - Returns a Vector3 with the xy fields from vec's values and z field from z . It defaults to zero.
* **ToVec3(this decimal v)** - Returns a Vector3 with the xyz fields set to v.
* **ToVec3(this double v)** - Returns a Vector3 with the xyz fields set to v.
* **ToVec3(this float v)** - Returns a Vector3 with the xyz fields set to v.
* **ToVec3(this byte v)** - Returns a Vector3 with the xyz fields set to v.
* **ToVec3(this int v)** - Returns a Vector3 with the xyz fields set to v.
 

To Vector 3 Int

* **ToVec3Int(this Vector4 vec)** - Returns a Vector3Int with the xy fields from vec's xy and discards z and w.
* **ToVec3Int(this Vector3 vec)** - Returns a Vector3Int with the xy fields from vec's values and discards z.
* **ToVec3Int(this Vector2 vec, int z)** - Returns a Vector3Int with the xy fields from vec's values and z field from z. It defaults to zero.
* **ToVec3Int(this Vector2Int vec, int z)** - Returns a Vector3Int with the xy fields from vec's values and z field from z. It defaults to zero.
* **ToVec3Int(this decimal v)** - Returns a Vector3Int with the xy fields set to v.
* **ToVec3Int(this double v)** - Returns a Vector3Int with the xy fields set to v.
* **ToVec3Int(this float v)** - Returns a Vector3Int with the xy fields set to v.
* **ToVec3Int(this byte v)** - Returns a Vector3Int with the xy fields set to v.
* **ToVec3Int(this int v)** - Returns a Vector3Int with the xy fields set to v.
 

To Vector 2

* **ToVec2(this Vector4 vec)** - Returns a Vector2 with the xy fields from vec's xy and discards z and w.
* **ToVec2(this Vector3 vec)** - Returns a Vector2 with the xy fields from vec's values and discards z.
* **ToVec2(this Vector3Int vec)** - Returns a Vector2 with the xy fields from vec's values and discards z.
* **ToVec2(this Vector2Int vec)** - Returns a Vector2 with the xy fields from vec's values.
* **ToVec2(this decimal v)** - Returns a Vector2 with the xy fields set to v.
* **ToVec2(this double v)** - Returns a Vector2 with the xy fields set to v.
* **ToVec2(this float v)** - Returns a Vector2 with the xy fields set to v.
* **ToVec2(this byte v)** - Returns a Vector2 with the xy fields set to v.
* **ToVec2(this int v)** - Returns a Vector2 with the xy fields set to v.
 

To Vector 2 Int

* **ToVec2Int(this Vector4 vec)** - Returns a Vector2Int with the xy fields from vec's xy and discards z and w.
* **ToVec2Int(this Vector3 vec)** - Returns a Vector2Int with the xy fields from vec's values and discards z.
* **ToVec2Int(this Vector3Int vec)** - Returns a Vector2Int with the xy fields from vec's values and discards z.
* **ToVec2Int(this Vector2 vec)** - Returns a Vector2Int with the xy fields from vec's values.
* **ToVec2Int(this decimal v)** - Returns a Vector2Int with the xy fields set to v.
* **ToVec2Int(this double v)** - Returns a Vector2Int with the xy fields set to v.
* **ToVec2Int(this float v)** - Returns a Vector2Int with the xy fields set to v.
* **ToVec2Int(this byte v)** - Returns a Vector2Int with the xy fields set to v.
* **ToVec2Int(this int v)** - Returns a Vector2Int with the xy fields set to v.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {    
        void MyMethod()
        {
            5f.ToVec3();
            2.ToVec2Int();
            transform.position.ToVec4(2f, 4f);
            3m.ToVec2();
            10d.ToVec4();
        }
    }

WithX/Y/Z/W
-----------

Return a new vector with the respective field set to the provided value. They support all vector types: Vector2, Vector2Int, Vector3, Vector3Int, and Vector4. They don't set the vector extended, but rather return a new vector with that value applied.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        void MyMethod()
        {
            Vector3 vector = Vector3.zero;
            Debug.Log(vector.SetX(5f).SetZ(2f)); // Prints "5, 0, 2".
            Debug.Log(vector); // Prints "0, 0, 0".
            vector = vector.SetX(5f).SetZ(2f)
            Debug.Log(vector); // Prints "5, 0, 2".
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