=========================
ParticleSystem Extensions
=========================

You can avoid the pain of changing values on the particle system with these extensions. Think of when you want to change a single value in the Particle System - it's a beureaucratic process that has to ve repeated every single time you want to modify something. Repetitive code is considered bad for a number of reasons. Bugs are way more common, and it's much harder to manage so much repeated code in many places. Issues and errors slip through much easier than in a properly managed code. More extensions and other features will be added in the future. Visit the Roadmap to know more.
    
Overview
--------

    * :ref:`GetStartColor`
    * :ref:`SetStartColor`
    * :ref:`Get Help <GET HELP>`

**EXTENSIONS**
--------------

GetStartColor
-------------

Retrieves the main.startColor property of the ParticleSystem.

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public ParticleSystem particleSystem;

        void MyMethod()
        {
            ParticleSystem.MinMaxGradient start_color = particleSystem.GetStartColor();
        }
    }

SetStartColor
-------------

There are many variants of the above mentioned methods. They do all the work of changing the starting color values in the particle system for you.

* ``SetStartColor(ParticleSystem.GradientMinMax grad)``
    
Sets the main.startColor property.

* ``SetStartColorConstant(Color color)``

Sets the main.startColor.constant property.

* ``SetStartGradientConstant(Gradient grad)``

Sets the main.startColor.gradient property.

* ``SetStartGradientMax(Gradient max)``

Sets the main.startColor.gradientMax property.

* ``SetStartGradientMin(Gradient min)``

Sets the main.startColor.gradientMin property.

* ``SetStartGradientMinMax(Gradient min, Gradient max)``

Sets both the main.startColor.gradientMax and main.startColor.gradientMin properties.

* ``SetStartColorMax(Color max)``

Sets the main.startColor.colorMax property.

* ``SetStartColorMin(Color min)``

Sets the main.startColor.colorMin property.

* ``SetStartColorMinMax(Color min, Color max)``

Sets both the main.startColor.colorMin and main.startColor.colorMax properties.

* ``SetStartColorMode(ParticleSystemGradientMode mode)``

Sets the startColor.mode property of the system's main module to the given color. 

.. code-block:: csharp
    :linenos:

    using NutTools;
    using UnityEngine;

    public class MyClass: MonoBehaviour
    {
        public ParticleSystem particleSystem;

        void MyMethod()
        {
            particleSystem.SetStartColorConstant(Color.yellow); // Single extension example.
            particleSystem.SetStartColorMin(Color.green)
                          .SetStartColorMode(ParticleSystemGradientMode.TwoColors); // Chaining example.
        }
    }

****

**GET HELP**
------------

`Join this Discord server <https://discord.gg/CvG3p7Q>`_ to get help from the community, suggest new features, and vote on future updates!

.. seealso::
    
    * :ref:`Array and List Extensions <array-and-list>`
    * :ref:`GameObject and Component Extensions <gameobject-and-component>`
    * :ref:`Physics Extensions <physics>`
    * :ref:`Texture Extensions <texture>`
    * :ref:`Value Extensions <value>`