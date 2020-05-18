===============
IvyTextureUtils
===============

Utilities created to help handling textures on general situations.

Overview
--------

    * :ref:`CreateBaseTexture`
    * :ref:`CreateRandomNoiseTexture`
    * :ref:`Get Help <**GET HELP**>`

**METHODS**
-----------

CreateBaseTexture
-----------------

* ``Texture2D CreateBaseTexture(Color color)``
* ``Texture2D CreateBaseTexture(Color color, int width, int height)``
* ``Texture2D CreateBaseTexture(Color color, Vector2Int size)``

Creates a base texture with the provided color and size. The texture will be automatically sized to one by one if no size is given.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public SpriteRenderer wall;

        void MyMethod()
        {
            Texture2D tex = CreateBaseTexture(Color.white, 128, 128)
                            .ShiftRandomPixelsTowards(Color.cyan);
            Sprite.Create();
        }
    }

CreateRandomNoiseTexture
------------------------

* ``Texture2D CreateRandomNoiseTexture(int width, int height, bool blackAndWhite = false)``
* ``Texture2D CreateRandomNoiseTexture(Vector2Int size, bool blackAndWhite = false)``

Creates a texture with the given size filled with random colors.

.. code-block:: csharp
    :linenos:

    using IvyTools.Utilities;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public SpriteRenderer wall;

        void MyMethod()
        {
            Texture2D tex = CreateRandomNoiseTexture(128, 128, false)
                            .MakeBlackAndWhite();
            Sprite.Create(tex, new Rect(0f, 0f, 128f, 128f), new Vector2(0.5f, 0.5f), 100.0f);
        }
    }

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help, suggest new features, and vote on future updates!

.. seealso::

    - IvyTextureExtensions
    - Sprite.Create