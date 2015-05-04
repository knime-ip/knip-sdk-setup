KNIP SDK
==============
This repository collects the tools to facilitate the development of KNIME Nodes in the context of KNIME Image Processing (KNIP).

### KNIP SDK vs. KNIME SDK
The KNIME SDK still bases on Eclipse Indigo, which is kind of buggy and not as feature-rich as the 4.x versions of Eclipse. Therefore
the KNIME Image Processing SDK (KNIP SDK), provides [Eclipse Target Definitions](https://wiki.eclipse.org/PDE/Target_Definitions) and a launch configuration, which can be used to develop KNIME and especially KNIME Image Processing nodes with Eclipse 4.x.

### Target Definitions
We provide two different target definitions, aimed at two different kinds of users.
* __knip-sdk-full__:
For people who want to develop plugins for KNIP and need a KNIME instance with KNIP and all dependencies installed.
* __knip-sdk-dev__: For people who work directly on KNIP and have the KNIP source code checked out in their workspace. It contains KNIME and all needed dependencies for developing KNIP itself.

If you need additional plugins you can easily edit the software sites in the target definitions and select the ones you need.  

### How-To
1. Download and install [Eclipse 4.x] (http://eclipse.org/home/index.php)
- Install the __Eclipse Plug-in Development Enviroment__ plugin from the __Eclipse Project__ update-site
- Clone this repository using git clone https://github.com/knime-ip/knip-sdk-setup
- Import the contained projects (File -> Import -> General -> Existing Projects into Workspace
- Double-click on the either the ``knip-sdk-full.target`` or the ``knip-sdk-dev.target`` file, which you will find in the ``org.knime.knip.sdk`` project.
- Wait until eclipse has resolved the target platform and click on __Set as Target Platform__ (upper-right corner)
- The ``knip-launch-configuration`` should now be available to you in the debug and run configuration dialogs (under Eclipse Application).
- The debug configuration assumes you have 2GB RAM available, if you want to use a different amount just  change the value of the ``-Xmx2g`` vm argument in the _Arguments_ tab of the ``knip-launch-configuration``.
