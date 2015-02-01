KNIP SDK
==============
This repository comprises all OSGi plugins which are required to develop KNIME Nodes in the context of KNIME Image Processing (KNIP).

### KNIP SDK vs. KNIME SDK
The KNIME SDK still bases on Eclipse Indigo, which is kind of buggy and not as feature-rich as the 4.x versions of Eclipse. Therefore
the KNIME Image Processing SDK (KNIP SDK), provides an [Eclipse Target Definitions](https://wiki.eclipse.org/PDE/Target_Definitions) and a launch config, which can be used to develop KNIME and especially
KNIME Image Processing nodes with Eclipse 4.x.

### How-To
- Download and install [Eclipse 4.x] (http://eclipse.org/home/index.php)
- Install the __Eclipse Plugin Development Enviroment__ plugin from the __Eclipse Project__ update-site
- Clone this repository using git clone https://github.com/knime-ip/knip-sdk
- Import the contained projects (File -> Import -> General -> Existing Projects into Workspace 
- Double-click on the knip-sdk-full.target_ file, which you find in the imported project org.knime.knip.sdk.
- Wait until the target platform was resolved by your eclipse and click on __Set as Target Platform__ (upper-right corner)
- The KNIP launch / debug configuration should now be avaiable.
- The debug configuration assumes you have 2GB RAM available, if you don't you can change the value of the ````-Xmx2g```` vm argument in the _Arguments_ tab of the KNIP debug configuration.
