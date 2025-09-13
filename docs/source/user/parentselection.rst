Parent Selection
================

.. _parentselection:

Fitness Proportional Selection
------------------------------

This selection strategy selects individuals for reproduction based on their fitness.
Individuals with higher fitness have a higher probability of being selected.
This strategy is also known as roulette wheel selection.

Fitness values are in the range [0, +infinity], so the selection probabilities are simply calculated by
dividing each fitness value by the sum of all fitness values.

.. code-block:: python3

   selection=FitnessProportionalSelection()

Rank Selection
--------------

This selection strategy selects individuals for reproduction based on their rank.
Individuals are first sorted based on their fitness, and the selection probability is
determined by their order in the sorted array.

The calculation of selection probabilities is done by the formula

.. math::

   P(i) = \frac{1}{n} \left(1 + sp \left(1 - \frac{2(i-1)}{n-1}\right)\right)

where i is the rank of the individual, n is the population size, and sp is the selection pressure. The `sp` parameter (selection pressure) controls the steepness of the selection curve and should have a value in the range [0, 1]. Selection pressure outside this range leads to some probability values being negative, which is undefined behavior.

.. code-block:: python3

   selection=RankSelection(sp=0.9)