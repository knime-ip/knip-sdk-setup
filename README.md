KNIP SDK
==============
This repository collects the tools to facilitate the development of KNIME Nodes in the context of KNIME Image Processing (KNIP).

### KNIP SDK vs. KNIME SDK
The KNIME SDK still bases on Eclipse Indigo, which is kind of buggy and not as feature-rich as the 4.x versions of Eclipse. Therefore
the KNIME Image Processing SDK (KNIP SDK), provides [Eclipse Target Definitions](https://wiki.eclipse.org/PDE/Target_Definitions) and a launch configuration, which can be used to develop KNIME and especially KNIME Image Processing nodes with Eclipse 4.x.

### Target Definitions
We provide different target definitions:
* __stable__
  * __knip-sdk-2.11-full__:
    KNIME 2.11 with the latest release of the compatible KNIP plugins.
  * __knip-sdk-2.12-full__:
	KNIME 2.12 with the latest release of the compatible KNIP plugins.
* __nightly__:
  * __knip-sdk-dev__ For people who work directly on KNIP and have the KNIP source code checked out in their workspace.
It contains KNIME and all needed dependencies for developing KNIP itself. It is targeting the KNIME nightly build, older versions of KNIP will not work with it.

If you need additional plugins you can easily edit the software sites in the target definitions and select the ones you need.

### How-To
1. Download and install [Eclipse 4.4 or 4.5] (http://eclipse.org/home/index.php)
- Install the __Eclipse Plug-in Development Enviroment__ plugin from the __The Eclipse Project Updates__ update-site
- Clone this repository using git clone https://github.com/knime-ip/knip-sdk-setup
- Import the contained projects (File -> Import -> General -> Existing Projects) into Workspace
- Double-click on the desired target definition file, which you will find in the ``org.knime.knip.sdk`` project.
- Wait until eclipse has resolved the target platform and click on __Set as Target Platform__ (upper-right corner)
- The ``knip-stable-launch-configuration`` and ``knip-nightly-launch-configuration`` should now be available to you in the debug and run configuration dialogs (under Eclipse Application).
- The debug configuration assumes you have 2GB RAM available, if you want to use a different amount just  change the value of the ``-Xmx2g`` vm argument in the _Arguments_ tab of the ``knip-launch-configuration``.
- Remember to regul click the ``update`` and ``refresh`` buttons in the target definition interface to stay up to date with the nightly builds.


### How to Build
The target definition files are build using this [eclipse plugin](https://github.com/mbarbero/fr.obeo.releng.targetplatform). You need to install it to build your own, modified target definition files.
The build files are located in the autogen folder. To rebuild the target definition files after modification rightclick on the corresponding .tpd file and select "Create Target Definition File".
