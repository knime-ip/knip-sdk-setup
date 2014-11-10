KNIP SDK Setup
==============
Target definition and  debug / launch configurations for developing KNIME-Plugins in new (post Keppler) versions of Eclipse.

### Reasoning
KNIME is based on Eclipse Keppler, and so is the KNIME-SDK, this creates several
problems, as the new versions of many Eclipse plugins don't work with Keppler anymore.
These newer versions contain critical bug fixes, for example m2e.
 So we need a way to use the new eclipse versions to develop KNIME-Plugins.

### How-To
- install latest Eclipse version.
- clone this repository.
- import the project.
- open the knime 2.10.target file and select _Set as Target Platform_ [1].
- The KNIP launch / debug configuration should now be avaiable to you [2].
- The debug configuration assumes you have 2GB RAM available, if you don't you can change the value of the ````-Xmx2g```` vm argument in the _Arguments_ tab of the KNIP debug configuration.

[1] For this to work you have to have the __Eclipse Plugin Development__ Enviroment installed. If your eclipse version did not ship with it, you can install it from the __The Eclipse Project Updates__ Software Site.

[2] If it doesn't appear right-click on the KNIP.launch file and select _Debug As_, and select __KNIP__.
