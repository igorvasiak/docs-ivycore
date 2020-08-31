====================
NutTextureExtensions
====================

Overview
--------

    * :ref:`CopyTo`
    * :ref:`MakeBlackAndWhite`
    * :ref:`ShiftRandomPixelsTowards`
    * :ref:`ShiftTowards`

**METHODS**
-----------

CopyTo
------

* ``Texture2D CopyTo(this Texture2D texture, Texture2D target)``

Copies all data from the former texture to the target one. Returns the target texture.

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public Texture2D texture;

        void MyMethod()
        {
            Texture2D copy_tex = new Texture2D(texture.width, texture.height);
            texture.CopyTo(copy_tex);
        }
    }

MakeBlackAndWhite
-----------------

* ``Texture2D MakeBlackAndWhite(BrightnessMode brightnessMode = BrightnessMode.AverageBrightness)``

Colors the given texture with the brightness value of each pixel, resulting in a black and white image.

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public Texture2D texture;

        void MyMethod()
        {
            Texture2D copy_tex = new Texture2D(texture.width, texture.height);
            texture.CopyTo(copy_tex);
                   .MakeBlackAndWhite();
            // Do the thing with "copy_tex".
        }
    }

ShiftRandomPixelsTowards
------------------------

* ``ShiftRandomPixelsTowards(this Texture2D texture, Color targetColor)``

Shifts a random amount of pixels in the texture to a color with random intensity.

* ``ShiftRandomPixelsTowards(this Texture2D texture, Color targetColor, float t)``

Shifts a random amount of pixels in the texture to a color with the given intensity ("**t**").

* ``ShiftRandomPixelsTowards(this Texture2D texture, Color targetColor, float t, int iterations)``

Shifts random pixels from the texture to a color with the given intensity ("**t**"). Iterations tells how many pixels will be altered. Altered pixels may be altered again.

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public Texture2D texture;

        void MyMethod()
        {
            Texture2D copy_tex = new Texture2D(texture.width, texture.height);
            texture.CopyTo(copy_tex);
                   .ShiftRandomPixelsTowards(Color.white, .5f, 10000);
        }
    }

ShiftTowards
------------

* ``ShiftTowards(this Texture2D texture, Color targetColor, float t)``

Shifts the entire texture towards a color with the given intensity ("**t**").

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public Texture2D texture;

        void MyMethod()
        {
            Texture2D copy_tex = new Texture2D(texture.width, texture.height);
            texture.CopyTo(copy_tex);
                   .ShiftTowards(Color.white, .5f, 10000);
        }
    }

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help from the community, suggest new features, and vote on future updates!

.. seealso::
    
    * :ref:`Array and List Extensions <array-and-list>`
    * :ref:`GameObject and Component Extensions <gameobject-and-component>`
    * :ref:`ParticleSystem Extensions <particlesystem>`
    * :ref:`Physics Extensions <physics>`
    * :ref:`Value Extensions <value>`