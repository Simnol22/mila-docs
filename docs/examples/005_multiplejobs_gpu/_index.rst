005 - Multiple Jobs On Single GPU
====================


**Prerequisites**
Make sure to read the following sections of the documentation before using this
example:

* :ref:`pytorch_setup`
* :ref:`001 - Single GPU Job`

The full source code for this example is available on `the mila-docs GitHub
repository.
<https://github.com/mila-iqia/mila-docs/tree/pytorch_distributed_training_examples/docs/examples/distributed/005_multiplejobs_gpu>`_

Before chosing the number of tasks you want to include, you should run the code bellow which has 
`--ntasks=1 and --ntasks-per-gpu=1`. You can then connect to your compute node via `ssh` and with
the `nvidia-smi -l 2`, you should receive information about how much VRAM is your task using, and
how much is available on the GPU. You can then use this information to decide how many tasks you
want to run on a single GPU.

**job.sh**

.. literalinclude:: examples/005_multiplejobs_gpu/job.sh
    :language: bash


**main.py**

.. literalinclude:: examples/005_multiplejobs_gpu/main.py
    :language: python


**Running this example**


.. code-block:: bash

    $ sbatch job.sh
