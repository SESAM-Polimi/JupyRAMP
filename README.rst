.. image:: https://img.shields.io/gitter/room/RAMP-project/RAMP
   :target: https://gitter.im/RAMP-project/community

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://github.com/psf/black

.. image:: https://badge.fury.io/py/rampdemand.svg
    :target: https://badge.fury.io/py/rampdemand

.. image:: https://readthedocs.org/projects/rampdemand/badge/?version=latest
    :target: https://rampdemand.readthedocs.io/en/latest/?badge=latest
    :alt: Documentation Status

.. image:: https://github.com/RAMP-project/RAMP/blob/main/docs/source/_static/RAMP_logo_basic.png?raw=true
   :width: 300


*An open-source bottom-up stochastic model for generating multi-energy load profiles* (`RAMP Website <https://rampdemand.org>`_ , `RAMP Documentation <https://rampdemand.readthedocs.io/en/latest/?badge=latest>`_)


What is RAMP
============
RAMP is an open-source software suite for the stochastic simulation of any user-driven energy demand time series based on few simple inputs.

The project aims to provide synthetic data wherever metered data does not exist, such as when designing systems in remote areas. Check out the `documentation <https://rampdemand.readthedocs.io/en/latest/?badge=latest>`_ and learn more on the RAMP world from our `website <https://rampdemand.org>`_!

.. image:: https://github.com/RAMP-project/RAMP/blob/main/docs/figures/Example_output.jpg?raw=true
   :width: 600

Recommended installation method
===============================

RAMP has been successfully installed and used on macOS, Windows and Linux.

The easiest way to make RAMP software working is to use the free conda package manager which can install the current and future RAMP
dependencies in an easy and user friendly way.

To get conda, `download and install "Anaconda Distribution" <https://www.anaconda.com/products/individual>`_, or `"miniconda" <https://docs.conda.io/en/latest/miniconda.html>`_ which is lighter.
You can install RAMP using pip, conda or from source code.

Installing through pip
----------------------
1. To install the RAMP software, we suggest to create a new environment by running the following command in the *Anaconda prompt*:

.. code-block:: python

   conda create -n ramp python=3.8


2. If you create a new environment for RAMP, you'll need to activate it each time before using it, by writing
the following line in the *Anaconda Prompt*:

.. code-block:: python

   conda activate ramp

3. Now you can use pip to install `rampdemand` on your environment as follow:

.. code-block:: python

  pip install rampdemand


Installing through the source code
----------------------------------
You can also install RAMP from the source code! To do so, you first need to download the source code, which can be done in two ways:

* You can use git to clone the repository via:

.. code-block:: bash

   git clone https://github.com/RAMP-project/RAMP.git

* Or, you may download the source code directly from:

`"RAMP GitHub Repository" <https://github.com/SESAM-Polimi/RAMP-Jupyter>`_.

In this second case, the source code will be downloaded as a zip file, so you'll need to extract the files.

After downloading the source code using any of abovementioned methods, you'll need to use your **anaconda prompt** to install it. There are two options again:

* You may follow the first two steps mentioned in **Installing through pip**. Then, change the directory in the prompt to the folder where the source code is saved (where you can find the *setup.py* file). To install the RAMP software, you may then use:

.. code-block:: bash

   python setup.py install

* Alternatively, without taking any prior action, simply change the directory in the prompt to the folder where the source code is saved and then use:

.. code-block:: bash

   conda env create -f environment.yml

Quick Start
===========

To start using the RAMP Jupyter Notebook interface in this repository, follow these steps:

1. **Install Jupyter Notebook:** Ensure that Jupyter Notebook is installed in your environment. You can install it by running ``pip install jupyter notebook`` in your command line.

2. **Launch Jupyter Notebook:** Launch Jupyter by typing ``jupyter notebook`` in your command line.

3. **Open the Notebook:** In the online Jupyter interface, navigate to *ramp/Jupyter Notebooks/* and open **RAMP Example Village - Excel.ipynb**.


How It Works
============

The RAMP Jupyter Notebook is designed to simulate electrical load profiles using your data provided in an Excel format. Below is a step-by-step guide on how to use the notebook:

Step 1 - Upload Excel File
--------------------------
To begin, upload your Excel file that contains detailed data on appliance usage and other necessary parameters for simulation. Detailed instructions are provided in the notebook on how to structure your Excel file correctly.

Step 2 - Set Simulation Parameters
----------------------------------
Set your simulation's start and end dates using the date picker widgets. These parameters will define the period over which the simulation will run.

Step 3 - Execute the Simulation
-------------------------------
Start the simulation by clicking the ``Run Simulation`` button. The notebook will process the data from the uploaded Excel file and generate electrical load profiles for each category included in your data across the specified period.

Step 4 - Review Results
-----------------------
Once the simulation is complete, the results will be displayed in the notebook. This includes daily and cumulative load profiles, showing the energy consumption patterns of different user categories outlined in your Excel file.

Detailed Steps in the Notebook
------------------------------

1. **Initialization:** Select and upload your Excel file to initialize the simulation.

2. **Profile Simulation:** Configure the number of simulation days and initiate the process. Monitor progress through the displayed progress bar.

3. **Visualizing Results:** Post-simulation, visualize daily average load curves and load profile variability.

4. **Analyzing Key Metrics:** Review and analyze key energy metrics like daily energy consumption and peak power.

5. **Exporting the Results:** Finally, export the simulation results into an Excel file named "Load demand results.xlsx" for further analysis and reporting.

Caution
=======

.. warning::
   Do not modify the critical code blocks unless you are confident about the changes. These blocks are essential for the functionality of the notebook and may depend on specific library versions or data structures.


Example Input Files
-------------------
Three different input files are provided as examples representing three different categories of appliances that can be modeled with RAMP. To review the files, navigate to the *ramp/Jupyter Notebooks/Excel Input Files* folder in this repository. The files are named as follows:

- **input_file_1.xlsx**
  This file represents the most basic electric appliances, such as lightbulbs, radios, TVs, fridges, and other electric appliances. It is based on the files used for the first RAMP publication. See the publication here: `first RAMP publication <https://doi.org/10.1016/j.energy.2019.04.097>`__.

- **input_file_2.xlsx**
  This file shows how to model user-driven thermal loads, exemplified by a "shower" appliance. The nominal power for thermal appliances can be provided externally as a ".csv" file (in this case, ``shower_P.csv``). This accounts for variations in groundwater temperature throughout the year. It is based on the input file used for this publication: `thermal appliance publication <https://doi.org/10.3390/app10217445>`__.

- **input_file_3.xlsx**
  This file provides an example of how to model electric cooking appliances, featuring two types of meals: short and repetitive (e.g., breakfast) and main meals (e.g., lunch, dinner). Main meals vary daily, with households randomly choosing among three types each day. This variability is modeled with the ``user preference`` and ``preference index``, which allow for daily stochastic variation in meal type preferences. This input file is referenced in this publication: `cooking appliance publication <https://doi.org/10.1109/PTC.2019.8810571>`__.




Contributing
============
This project is open-source. Interested users are therefore invited to test, comment or contribute to the tool. Submitting issues is the best way to get in touch with the development team, which will address your comment, question, or development request in the best possible way. We are also looking for contributors to the main code, willing to contribute to its capabilities, computational-efficiency, formulation, etc.

To contribute changes:

#. Fork the project on GitHub
#. Create a feature branch (e.g. named "add-this-new-feature") to work on in your fork
#. Add your name to the `AUTHORS <https://github.com/RAMP-project/RAMP/blob/development/AUTHORS>`_ file
#. Commit your changes to the feature branch
#. Push the branch to GitHub
#. On GitHub, create a new pull request from the feature branch

When committing new changes, please also take care of checking code stability by means of the `qualitative testing <https://github.com/RAMP-project/RAMP/blob/development/CONTRIBUTING.md>`_ functionality.


How to cite
===========
Please cite the original Journal publication if you use RAMP in your research:

*F. Lombardi, S. Balderrama, S. Quoilin, E. Colombo, Generating high-resolution multi-energy load profiles for remote areas with an open-source stochastic model, Energy, 2019,*
`https://doi.org/10.1016/j.energy.2019.04.097 <https://doi.org/10.1016/j.energy.2019.04.097>`_

More information
================
Want to know more about the possible applications of RAMP, the studies that relied on it and much more? Then take a look at the `RAMP Website <https://rampdemand.org>`_!

License
=======
Copyright 2019-2023 RAMP, contributors listed in **Authors**

Licensed under the European Union Public Licence (EUPL), Version 1.2-or-later; you may not use this file except in compliance with the License.

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an **"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND**, either express or implied. See the License for the specific language governing permissions and limitations under the License.


.. note::

   This project is under active development!
