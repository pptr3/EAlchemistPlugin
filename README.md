# EAlchemistPlugin

EAlchemistPlugin is an Eclipse plugin created in order to facilitate the creation of new Alchemist projects. [What is Alchemist?][Alchemist].


### Premise
This plugin has been built merging two existing projects([webtools.javaee], [webtools.jsdt] 

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
* Once you have ran the plug-in go to File -> New -> Project... -> Alchemist (if you don't see it, check the box "Show All Wizards.") -> `Alchemist Project`
* Click Next
* If a Confirm Enablement window appears, just press Ok
* Insert the name of the project
* Finish.


#### Create New Protelis File
* Once you have created an Alchemist Project, for creating new Protelis file, go to File -> New -> Project... -> Other... -> Alchemist -> `New Protelis File`
* Click Next
* Insert a name for your file
* Select the project
* Finish.




[Alchemist]: http://alchemistsimulator.github.io/
[eclipse]: https://eclipse.org/downloads/
[webtools.javaee]: https://github.com/eclipse/webtools.javaee
[webtools.jsdt]: http://git.eclipse.org/c/jsdt/webtools.jsdt.git/tree/
