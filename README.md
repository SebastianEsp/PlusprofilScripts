# Plusprofil-Scripts
A series of scripts for Sparx Enterprise Architect, written in JScript, that provides automation to assist in conforming to the Plusprofil.

## Overview
The scripts in this project serve as a tool that simplifies certain actions required when working with the Plusprofil MDG-technology in Sparx Enterprise Architect. The following scripts are currently available:

* 1a: Copy UML name to preflabel (da)
* 1b: Copy UML name to prefLabel (en)
* 2a: Copy Alias to prefLabel (da)
* 2b: Copy Alias to prefLabel (en)
* 3a: Copy Notes to definition (da)
* 3c: Copy Notes to definition (en)
* 4: Copy tags from selected element to another
* 5: Autofill URI and assign prefixes
* 6: Autofill subClassOf-tag

Aside from "4: Copy tags from selected element to another", the scripts must be run on a package. The script will then perform the specified action on every child package, element, attribute and connector end found in the package.

Please note that the effects of the scripts are saved as the script runs, and thus cannot be reverted.

## Usage
### Setup
To use or modify the scripts, they must be imported into the current Sparx Enterprise Architect project:

1. Download the file 'Plusprofil Scripts.xml' or clone the 'PlusprofilScripts' repository.
2. In Sparx Enterprise Architect, go to "Import Reference Data", found in the tab "Configure" -> "Transfer".
3. Press "Select File", then select 'Plusprofil Scripts.xml'.
4. In "Select Datasets to Import:", choose "Automation Scripts"
5. Press "Import"

### Using the scripts
To run the package-only scripts, i.e. every script except "4: Copy tags from selected element to another", right click a package, select "Scripts" and then the script to run on the package.

To use the script '4: Copy tags from selected element to another', right click a package, element or attribute in the Project Browser, select "Scripts" and then "4: Copy tags from selected element to another". A dialog box will appear, asking you to select another object. In the Project Browser, click the element to move the tags to, then press "OK" in the dialog box.

### Exporting the scripts
To export the scripts, follow the following steps:

1. In Sparx Enterprise Architect, go to "Export Reference Data", found in the tab "Configure" -> "Transfer".
2. Select "Automation Scripts"
3. Select a filename, then press "Save"

Be aware that this will export all Automation Scripts found in the project.

## TODO
* **Performance issues**: The scripts currently use the Enterprise Architect Automation Interface to find and modify tagged values. This is a cause for significant performance problems, especially when the scripts are run on a remote project, as traversing the Enterprise Architect type 'Collection' is inefficient. Retrieving each tagged value using 'Repository.SQLQuery(string query)' could mitigate or solve this problem.
* **Refactoring and debugging**: As the scripts have been written entirely using the Sparx Enterprise Architect script editor, few debugging and refactoring tools have been available during the writing of the scripts. It may be worthwhile to do a quality check of every script, ensuring that best practices are used.

## Authors
* **Mathias Enggrob Boon** - Implementation - [Boonoboo](https://github.com/Boonoboo)

## License
This project is licensed under the GNU General License v3.0.
