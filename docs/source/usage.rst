Usage
=====

.. _installation:

Installation
------------

On Fedora, to install dependencies with dnf:

.. code-block:: console

   $ sudo dnf install gcc gcc-c++ make cmake -y
   $ sudo dnf install rocminfo rocm-opencl rocm-clinfo rocm-hip rocm-hip-devel amd-smi -y
   $ sudo dnf install python3 python3-devel -y
   $ sudo dnf install libasan libubsan -y
   $ sudo dnf install doxygen -y

To clone the repository with submodules (pybind11):

.. code-block:: console

   $ git clone https://github.com/kocatepedogu/quick-symbolic-regression.git
   $ cd quick-symbolic-regression
   $ git submodule update --init --recursive

To compile the project with CMake:

.. code-block:: console

   cmake .
   $ make -j$(nproc)
   $ export PYTHONPATH=$(pwd)

