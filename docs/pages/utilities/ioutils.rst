==========
IvyIOUtils
==========

Overview
--------

* :ref:`GetIndexedPath`
* :ref:`LoadSprite`
* :ref:`LoadToNullSprite and TryLoadToNullSprite`
* :ref:`LoadTexture`
* :ref:`LoadToNullTexture and TryLoadToNullTexture`
* :ref:`Get Help <**GET HELP**>`

**UTILITIES**
-------------

GetIndexedPath
--------------

* ``string GetIndexedPath(string path, string fileName, string extension, int index)``

Returns the path of the file with an index that hasn't been used yet.
For example, if you pass the values to get the indexed path of «file.txt», and it already exists, you'll get «file 1.txt».
If many more already exist, you'll get the next possible index.
It looks for the file name recursively, recalling itself as many times as needed.

.. code-block:: csharp
    :linenos:
    
    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        void MyMethod()
        {
            byte[] bytes = File.ReadAllBytes("C:\Users\joe\Desktop\image.png");

            // If image.png already exists it'll return image 1.png.
            File.WriteAllBytes(IvyIOUtils.GetIndexedPath("C:\Users\joe\Desktop\", "image", "png"), bytes);

            // If image 5.png already exists it'll return image 6.png, or keep calling until it finds an unused name.
            File.WriteAllBytes(IvyIOUtils.GetIndexedPath("C:\Users\joe\Desktop\", "image", "png", 5), bytes);
        }
    }

LoadSprite
----------

* ``Sprite LoadSprite(string path, int width, int height)``

Loads the sprite located at "path" with the provided resolution.

.. code-block:: csharp
    :linenos:

    using IvyTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        void MyMethod()
        {
            Sprite sprite = IvyIOUtils.LoadSprite("C:\Users\joe\Desktop\image.png", 512, 512);
        }
    }

LoadToNullSprite and TryLoadToNullSprite
----------------------------------------

* ``Texture2D LoadToNullSprite(ref Sprite sprite, string path, int width, int height)``

Loads the image and sets sprite if sprite is null. It returns sprite even if not null.

* ``bool TryLoadToNullSprite(ref Sprite sprite, string path, int width, int height)``

Loads the image and sets sprite if sprite is null. It returns wether tex has been set or not.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        void MyMethod()
        {
            Sprite sprite = null;
            IvyIOUtils.LoadToNullSprite(ref sprite, "C:\Users\joe\Desktop\image.png", 512, 512);

            if (IvyIOUtils.TryLoadToNullSprite(ref sprite , "C:\Users\joe\Desktop\image.png", 512, 512))
            {
                // Do stuff…
            }
        }
    }

LoadTexture
-----------

* ``Texture2D LoadTexture(string path, int width, int height)``

Loads the image located at "path" with the provided resolution.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        void MyMethod()
        {
            Texture2D tex = IvyIOUtils.LoadTexture("C:\Users\joe\Desktop\image.png", 512, 512);
        }
    }

LoadToNullTexture and TryLoadToNullTexture
------------------------------------------

* ``Texture2D LoadToNullTexture(ref Texture2D tex, string path, int width, int height)``

Loads the texture and sets tex if tex is null. It returns tex even if not null.

* ``bool TryLoadToNullTexture(ref Texture2D tex, string path, int width, int height)``

Loads the texture and sets tex if tex is null. It returns wether it set tex or not.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        void MyMethod()
        {
            Texture2D tex = null;
            IvyIOUtils.LoadToNullTexture(ref tex, "C:\Users\joe\Desktop\image.png", 512, 512);

            if (IvyIOUtils.TryLoadToNullTexture(ref tex, "C:\Users\joe\Desktop\image.png", 512, 512))
            {
                // Do things…
            }
        }
    }

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!

.. seealso::

    * :ref:`IvyArrayUtils and IvyListUtils <arrayutils-and-listutils>`
    * :ref:`IvyColorUtils <colorutils>`
    * :ref:`IvyLogUtils <logutils>`
    * :ref:`IvyTextureUtils <textureutils>`