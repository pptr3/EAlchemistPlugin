# EAlchemistPlugin

EAlchemistPlugin is an Eclipse plugin created in order to facilitate the creation of new Alchemist projects. [What is Alchemist?][Alchemist].


### Premise

The features that this project needed it's the same that many other Eclipse plugins offers, so we took from these two Eclipse plugins ([webtools.javaee], [webtools.jsdt]) what we needed and merge it. Due that, many file still have the original-old name and there is a bunch of source file that need to be delete because probably useless.

### Importing the project

The project has been developed using Eclipse, and can be easily imported in such IDE.

#### Recommended configuration
* Download [the latest Eclipse for Java][eclipse].
  * Arch Linux users can use the package `eclipse-java`
  * Ubuntu-based Linux users can install it using [ubuntu-make](https://wiki.ubuntu.com/ubuntu-make): 
    ```bash
    sudo apt-add-repository ppa:ubuntu-desktop/ubuntu-make
    sudo apt-get update
    sudo apt-get install ubuntu-make
    umake ide eclipse 
    ```
* Install the required eclipse plugins:
  * In the search field enter "checkstyle", then press Enter
  * One of the retrieved entries should be "Checkstyle Plug-in" with a written icon whose text is "eclipse-cs", click Install
  * Click "< Install More"
  * In the search field enter "eclipse pde", then press Enter
  * One of the retrieved entries should be "Eclipse PDE (Plug-in Development Environment) X.Y Luna", click Install
  * Click "Install Now >"
  * Wait for Eclipse to resolve all the features
  * Click "Confirm >"
  * Follow the instructions, accept the license, wait for Eclipse to download and install the product, accept the installation and restart the IDE
  * When restarted, click "Help" -> "Install New Software..."
  * Click "Add..."
  * In "Location" field, enter `https://dl.bintray.com/pmd/pmd-eclipse-plugin/updates/`
  * The "Name" field is not mandatory (suggested: "PMD")
  * Click OK.
  * If not already selected, in "Work with:" dropdown menu choose the just added update site
  * Select "PMD for Eclipse 4" and click next
  * Follow the instructions, accept the license, wait for Eclipse to download and install the product, accept the installation and restart the IDE.
* Set the line delimiter to LF (only for Windows users)
  * In Eclipse, click window -> preferences
  * In the search form enter "encoding", then press Enter
  * Go to General -> Workspace
  * In the section "New text file line delimiter" check "Other" and choose Unix
  * Apply
* Use space instead of tabs
  * In Eclipse, click window -> preferences
  * Go to General -> Editors -> Text Editors
  * Check "insert spaces for tabs" option.
  * Apply.
  * Go to Java -> Code style -> Formatter
  * Click Edit button
  * In Indentation tab, under "General Settings", set "tab policy" to "Spaces only"
  * Apply (you should probably rename the formatter settings).

#### Import Procedure
* Install git on your system, if you haven't yet
* Pull up a terminal, and `cd` to the folder where you want the project to be cloned (presumably, your Eclipse workspace)
* Clone the project with `git clone git@github.com:Pptr95/EAlchemistPlugin.git`
  * If you are a Windows user, you might find easier to import via HTTPS: `git clone https://github.com/Pptr95/EAlchemistPlugin.git`
* In terminal type `git branch`. This shows you all the branches. If you only have the master branch type `git branch -a` to see local and remote branches. For add a remote branch to your local repository type `git checkout -b <branch-name> origin/<branch-name>`. For switch between branches use `git checkout <branch-name>`.
* Open Eclipse
* Click File -> Import -> Maven -> Existing Maven Projects -> Next
* Select the folder that has been created after the cloning (presumably `EAlchemistPlugin`)
* Finish
* Wait for Eclipse to build the workspace
* The projects will appear in your projects list.

#### Run Configuration
* Plugins need to be ran in another workspace
* Right click on `org.eclipse.wst.jsdt.ui` project -> Run As -> Run Configurations...
* Double click on `Eclipse Application`
* Choose a custom name
* Go to Plug-ins tab
* In `Launch with:` select "features selected below"
* Click Apply
* Click Run
* If a Validation window appears, just press Continue
* Wait the loading of the new workspace.

#### Create New Alchemist Project
* Once you have ran the plug-in go, to File -> New -> Project... -> Alchemist (if you don't see it, check the box "Show All Wizards.") -> `Alchemist Project`
* Click Next
* If a Confirm Enablement window appears, just press Ok
* Insert the name of the project
* Finish.


#### Create New Custom File
* Once you have created an Alchemist Project, for creating new custom file, go to File -> New -> Project... -> Other... -> Alchemist -> `New Protelis File` (in this demo i've choosed `protelis` extension, it can be easily changed, take a look in "Developing the project" section down below)
* Click Next
* Insert a name for your file
* Select the project
* Finish.

### Developing the project
* Contributions to this project are welcome. The main features (creating new custom projects and new custom files) has been     implemented, however need to do other things such as clean up the project of all the things and file useless.
* The built demo consist in creating and Alchemist projects and Protelis files. If you want to change the name and properties of the custom project, take a look at `EAlchemistPlugin/plugins/org.eclipse.jst.j2ee.ui/plugin.xml` file. You can easily change the wizard immediatly underneath the comment `<!--Alchemist Project Wizard-->` as you prefer. You can even add a new wizard and with some code in `EAlchemistPlugin/plugins/org.eclipse.jst.j2ee.ui/` package you can create your own custom project.
* If you want to create others custom file, take a look at `EAlchemistPlugin/plugins/org.eclipse.wst.jsdt.ui/plugin.xml` line 488.  You can easily change the wizard immediatly underneath the comment `<!--Create new Protelis File-->` as you prefer or copy that wizard and paste in the same parent `<extension>` to have a new type of custom file. In this case the only things that actually you can change in plugin.xml is the name and icon of the custom file, to change the extension of the new custom file that you want to introduce i recommend to search where is located the keyword `protelis` (that is the default extension) through the bash command `grep -wrn '/path/to/repo/EAlchemistPlugin/plugins/' -e 'protelis'` and write code to change all instances that appears in order to create many custom files, each one with a different extension.

[Alchemist]: http://alchemistsimulator.github.io/
[eclipse]: https://eclipse.org/downloads/
[webtools.javaee]: https://github.com/eclipse/webtools.javaee
[webtools.jsdt]: http://git.eclipse.org/c/jsdt/webtools.jsdt.git/tree/
