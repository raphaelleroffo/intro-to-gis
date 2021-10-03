# Session 1: What is GIS?
**Introduction to GIS | Sciences Po Urban School, GETEC Masters | Fall semester 2021-2022**

Lecturer: Raphaëlle Roffo

.

## **I. Session 1 Overview** 

*[See Slides](https://github.com/raphaelleroffo/intro-to-gis/blob/main/Session1/Intro%20to%20GIS%20-%20session%201.pdf)*

- *Course overview and objectives*
- *GIS as a field of research and a tool*
- *Why is spatial special?*
- *Issues with 2D representations of the Earth surface: Coordinate Reference Systems and Projections*
- *Common use cases*
- *GIS and geospatial data science workflows*

.


## **II. Tutorial**

### Goals:

- Installing QGIS
- Exploring the QGIS console

.

### Downloading QGIS

Visit https://qgis.org/en/site/forusers/download.html

Download the long-term release (most stable) version for your OS. This is a stable and relatively bug-free version as opposed to the latest release in which new features were introduced but you may find some bugs.

**MacOS:**

![MacOS_Download](https://raw.github.com/raphaelleroffo/intro-to-gis/main/img/MacOS_download.png)

If you own an old Mac you may need to download an older version of QGIS. If you are unable to download 3.16, try downloading one of the 2.18 releases from [this page](https://qgis.org/downloads/macOS/)

**Windows users:** download the QGIS Standalone installer, you won't need the OSGeo4W setup for your usage.

![Windows_Download](https://raw.github.com/raphaelleroffo/intro-to-gis/main/img/Windows_download.png)

Once the installer is downloaded and launched, you can follow the steps and use the default options offered in each step. You're then ready to start mapping!


![Welcome](https://raw.github.com/raphaelleroffo/intro-to-gis/main/img/Welcome.png)

. 

### The QGIS GUI

Let's explore the QGIS Graphical User Interface (GUI).

![GUI](https://raw.github.com/raphaelleroffo/intro-to-gis/main/img/GUI.png)

.
### Documentation
The QGIS documentation is available at this address: https://qgis.org/en/docs/index.html

Please note:
1. This course is taught in English but some of you will have a version of QGIS installed that's in a different language. If you are trying to understand how a function translates into that language, at any time when navigating the documentation you can change the language of the page directly in the url (by replacing `/en/` by `/fr/` for French, or `/es/` for Spanish, `/zh-Hans/` for Mandarin Chinese etc.): For instance to go from English: `https://docs.qgis.org/3.16/`**en**`/docs/user_manual/introduction/qgis_gui.html` to French: `https://docs.qgis.org/3.16/`**fr**`/docs/user_manual/introduction/qgis_gui.html`

2. Similarly, you might have a version installed that is not 3.16 ; you can also edit the version directly in the URL to match the release you're using, by changing `/3.16/` . For instance from QGIS version 3.16 https://docs.qgis.org/3.16/en/docs/user_manual/introduction/qgis_gui.html to QGIS version 2.18 https://docs.qgis.org/2.18/en/docs/user_manual/introduction/qgis_gui.html 