====================
NutTextureExtensions
====================

Overview
--------

    * :ref:`ApplyFilterMode` (*No documentation yet*)
    * :ref:`ApplyWrapModes` (*No documentation yet*)
    * :ref:`CopyTo`
    * :ref:`CreateDuplicate` (*No documentation yet*)
    * :ref:`CreateDuplicateWithNewTexture` (*No documentation yet*)
    * :ref:`CreateDuplicateWithOldTexture` (*No documentation yet*)
    * :ref:`GetNormalizedPivot` (*No documentation yet*)
    * :ref:`GetTextureArea` (*No documentation yet*)
    * :ref:`MakeBlackAndWhite`
    * :ref:`LerpRandomPixels`
    * :ref:`LerpPixels`

**METHODS**
-----------

CopyTo
------

* ``Texture2D CopyTo(this Texture2D origin, Texture2D destination)``

Copies all data from the former texture to the target one. Returns the target texture.

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass : MonoBehaviour
    {
        public Texture2D origin;

        void MyMethod()
        {
            Texture2D destination = new Texture2D(origin.width, origin.height);
            origin.CopyTo(destination);
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

    public class MyClass : MonoBehaviour
    {
        public Texture2D origin;

        void MyMethod()
        {
            Texture2D destination = new Texture2D(origin.width, origin.height);
            origin.CopyTo(destination);
                  .MakeBlackAndWhite();
        }
    }

LerpRandomPixels
----------------

* ``LerpRandomNumberOfRandomPixelsByNPercent(this Texture2D texture, Color targetColor)``

Linearly interpolates a random number of random pixels towards the target color by a random percentage.
Iteration count and the amount each pixel will be shifted are both random.

* ``LerpRandomNumberOfRandomPixels(this Texture2D texture, Color targetColor, float t)``

Linearly interpolates a random number of random pixels towards the target color by "t".
Iteration count is random.

* ``LerpRandomPixels(this Texture2D texture, Color targetColor, float t, int iterations)``

Shifts random pixels towards the target color by "t". Iterations tells how many pixels will be altered. Altered pixels may be altered again.

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass : MonoBehaviour
    {
        public Texture2D origin;

        void MyMethod()
        {
            Texture2D destination = new Texture2D(origin.width, origin.height);
            origin.CopyTo(destination);
                  .LerpRandomPixels(Color.white, .5f, 10000);
        }
    }

LerpColors
----------

* ``LerpColors(this Texture2D texture, Color targetColor, float t)``

Linearly interpolates the texture's colors to the "targetColor" by "t".

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass : MonoBehaviour
    {
        public Texture2D origin;

        void MyMethod()
        {
            Texture2D destination = new Texture2D(origin.width, origin.height);
            origin.CopyTo(destination);
                  .LerpColors(Color.white, .5f, 10000);
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