Lab Variables
-------------

The lab will make use of unique environment variables to provide access to Azure and isolate student environments. Students will use this account to log into Azure and also to create a Service Principle for Ansible to use.

=============== ===================================================================
Variable Name   Variable Value
=============== ===================================================================
AZURE_USERNAME  Account name for each student (i.e. student1@f5demo.onmicrosft.com)
AZURE_PW
=============== ===================================================================

Set Variables
--------------

The following will store the environment variables that will be used throughout the lab.

Export your Azure userneme and password variables.
These credentials will be used to create an Azure Service Principle and to provide unique names for infrastructure that you create in the shared subscription. Replace the AZURE_USERNAME and AZURE_PW values below with the username and password assigned to you at the start of the lab.

Copy and paste the commands below to accomplish the steps above (replacing the example values with the values provided by your instructor).

.. code-block:: bash

 export AZURE_USERNAME=student1@f5demo.onmicrosoft.com
 export AZURE_PW=ABC123
 printenv

The ``printenv`` command will echo all your environment variables.  Look for AZURE_USERNAME and AZURE_PW. Confirm the exported variables are correct.


Create Service Principle
-------------------------

.. code-block:: bash

   cd ~/f5-azure-automation-lab/scripts/
   ./spCreate.sh


The results should look like the image below.

.. image:: /_static/spCreate-results.png
    :scale: 100%


Cut and paste the Service Principle export commands from teh above commands and verify using the command below.

.. code-block: bash

printenv | grep AZURE

.. TODO:: FIX AZURE_STUDENT VAR


The results should look like the image below.

.. image:: /_static/export-results.png
    :scale: 100%


Deploy BIG-IP Stack
--------------------

.. code-block:: bash

   cd ~/f5-azure-automation-lab/bigipClusterCreate/
   ansible-playbook site.yml
