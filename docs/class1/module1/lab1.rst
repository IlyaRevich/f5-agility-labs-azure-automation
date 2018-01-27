Connecting to the Lab
----------------------

.. important:: Your student account, password will be announced at the start of the lab.

- Though the environment runs on a shared Azure subscription, every student will build and work in a dedicated resource group.
- For this lab, a Ravello Windows 10 remote desktop jump host will be provided as a consistent starting point.

See :ref:`Connecting to the Lab Environment` for directions on connecting to the lab environment.

You may find it easier to follow this lab by opening this document in web browser to ease the process of copy and pasting text.

Run Docker
-------------

From your open Putty Window in your Windows jumphost, launch the f5-super-netops docker container.

Cut and past the command below to accomplish the steps above.

.. code-block:: bash

   docker run -p 8080:80 -p 2222:22 -it -e SNOPS_AUTOCLONE=0 f5devcentral/f5-super-netops-container:base

This command will launch  in interactive mode, map port 22 on the container with 2222 on the host, and port 80 on the container with 8080 on the host.

You should see the resulting screen.

.. image:: /_static/snops-launched.png
  :scale: 50%

Initialize your Lab Environment
-------------------------------

This will install Ansible and the Azure CLI tools which are both required for the lab.

You will (instructions provided below)

- Change to your home directory.
- Clone the git repository for this lab.
- Change to the working directory.
- Run the start script.

Copy and paste the commands below to accomplish the steps above.

.. code-block:: bash

   cd ~
   git clone https://github.com/stjbrown/f5-azure-automation-lab.git
   cd ~/f5-azure-automation-lab
   source start
