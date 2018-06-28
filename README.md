KNIME Image Processing SDK
==============
This repository collects the tools to facilitate the development of KNIME Nodes in the context of KNIME Image Processing (KNIP). The KNIME Image Processing SDK (KNIP SDK), provides [Eclipse Target Definitions](https://wiki.eclipse.org/PDE/Target_Definitions) and a launch configuration, which can be used to develop KNIME and especially KNIME Image Processing nodes.

## Target Definitions
We provide different target definitions:
* __stable__
   These target definitions allow starting and debugging released versions of KNIME / KNIP. This is useful to reproduce the environments of users.
  * __knip-sdk-2.11-full__:
        KNIME 2.11 with the latest release of the compatible KNIP plugins.
  * __knip-sdk-2.12-full__:
	KNIME 2.12 with the latest release of the compatible KNIP plugins.
  * __knip-sdk-3.0-full__:
	KNIME 3.0 with the latest release of the compatible KNIP plugins.
  * __knip-sdk-3.1-full__:
	KNIME 3.1 with the latest release of the compatible KNIP plugins.
  * __knip-sdk-3.2-full__:
	KNIME 3.2 with the latest release of the compatible KNIP plugins.
  * __knip-sdk-3.3-full__:
	KNIME 3.3 with the latest release of the compatible KNIP plugins.
  * __knip-sdk-3.4-full__:
	KNIME 3.4 with the latest release of the compatible KNIP plugins.
  * __knip-sdk-3.5-full__:
	KNIME 3.5 with the latest release of the compatible KNIP plugins.	
* __nightly__:
  * __knip-sdk-dev__ For people who work directly on KNIP and have the [KNIP](https://github.com/knime-ip/knip) and [KNIP SciJava](https://github.com/knime-ip/knip-scijava) source code cloned and added to their workspace.
It contains the most recent KNIME Analytics Platform and all required dependencies for developing KNIP itself.
  * __knip-sdk-dev-full__ For people who want to test the latest nightly build from their IDE, contains the latest nightly build of all KNIP plugins and the latest release of KNIME Analytics Platform.
  * __knip-sdk-dev-nightly__ Same as _knip-sdk-dev_ but targets the latest nightly build of KNIME Analytics Platform.

If you need additional plugins you can easily edit the software sites in the target definitions and select the ones you need.

## Getting started with KNIP development
- Download and install [Eclipse 4.7](http://eclipse.org/home/index.php) or later.
- Install the __Eclipse Plug-in Development Environment__ plugin from the __The Eclipse Project Updates__ update-site
- Clone this repository using git clone https://github.com/knime-ip/knip-sdk-setup
- Import the contained projects (File -> Import -> General -> Existing Projects) into Workspace
- Double-click on the desired target definition file, which you will find in the ``org.knime.knip.sdk`` project.
- Wait until eclipse has resolved the target platform and click on __Set as Target Platform__ (upper-right corner)
- The ``knip-stable-launch-configuration`` and ``knip-nightly-launch-configuration`` should now be available to you in the debug and run configuration dialogs (under Eclipse Application).
- The debug configuration assumes you have 4GB RAM available, if you want to use a different amount just  change the value of the ``-Xmx4g`` vm argument in the _Arguments_ tab of the ``knip-launch-configuration``.
- Remember to often click the ``update`` and ``reload`` buttons in the target definition interface to stay up to date with the nightly builds.

## FAQ
- _Eclipse complains that some plugin can't be installed and the target definition file seems to have many errors in it!_
Sadly eclipse seems to do that from time to time, in most cases clicking ``reload`` and ``update`` a few times solves that issue. If not you might need to update this repository as the target platform has changed.

## Guidelines
- Questions/Bug-Reports concerning the individual frameworks: Issues in the corresponding repositories.
- Questions/Bug-Reports concerning KNIME Image Processing: http://tech.knime.org/forum/knime-image-processing

Asking questions in a public forum or reporting the bugs on github makes sure, that others also benefit from the answers to your questions or see which bugs have already been reported and maybe solved.

## Frameworks and Tools
### KNIME Image Processing:
- Short Description: KNIME Image Processing extends KNIME by providing integrations for the processing and analysis of huge amounts of image data.
- Uses: ImgLib2, ImageJ-Ops, ImageJ2
- Link: http://knime.imagej.net
- Webinar: https://www.youtube.com/watch?v=MqSIyqmm3EU&feature=youtu.be&a
- Example Workflows: https://tech.knime.org/community/image-processing#exampleworkflows
- Example Projects: https://github.com/knime-ip/knip-examples
- Lecture with KNIME Image Processing: https://github.com/kmader/Quantitative-Big-Imaging-2015/blob/master/Exercises/02-Description-KNIME.md

### ImgLib2:
- Short Description: ImgLib2 is a general-purpose, multidimensional image processing library.
- Link: http://imglib2.net
- GitHub: http://github.com/imglib/imglib2
- Tutorial "Getting Started": http://fiji.sc/ImgLib2_-_Introductory_Workshop
- Tutorial "Advanced": http://fiji.sc/ImgLib2_-_Advanced_Programming_Workshop

### ImageJ-Ops:
- Short Description: ImageJ OPS is an extensible Java framework for algorithms, particularly image processing algorithms.
- Uses: ImgLib2
- Link/GitHub: https://github.com/imagej/imagej-ops
- Tutorial "Using Ops": https://github.com/imagej/imagej-tutorials/tree/master/using-ops
- Tutorial "Creating Ops": https://github.com/imagej/imagej-tutorials/tree/master/create-a-new-op

### ImageJ2:
- Short Description: ImageJ2 is a supercharged version of ImageJ1 with new features. ImageJ2 is an entirely redesigned, more powerful set of software libraries.
- Uses: ImgLib2, ImageJ-Ops
- Link: http://imagej.net
- GitHub: https://github.com/imagej
- Tutorials: https://github.com/imagej/imagej-tutorials


## How to Build the target platform file
The target definition files are build using this [eclipse plugin](https://github.com/mbarbero/fr.obeo.releng.targetplatform). You need to install it to build your own, modified target definition files.
The build files are located in the autogen folder. To rebuild the target definition files after modification rightclick on the corresponding .tpd file and select "Create Target Definition File".
