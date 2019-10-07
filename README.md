# <a id="top"></a>Anonymouth

![](src/edu/drexel/psal/resources/graphics/readme_Logo.png)

A Document Anonymization Tool <br>
Version: 0.5<br>

The Privacy, Security and Automation Lab (PSAL)<br>
Drexel University, Philadelphia PA<br>
<https://psal.cs.drexel.edu/index.php/Main_Page>


# Index
1. Set Up
	- [Introduction](#introduction)
	- [Dependencies](#dependencies)
	- [Running Anonymouth](#run)
	- [IDE and Development Setup](#installation)
2. Development	
	- [Basic Logic Flow](#basic-logic-flow)
	- [Basic Class Strucutre](#basic-class-structure)
	- [To Do List](#to-do-list)
	- [Known Bugs](#known-bugs)
3. Credits
	- [Developers](#developers)
	- [License](#license)

# Set Up

### <a id="introduction"></a>Introduction

Anonymouth is a Java-based application aiming to provide users with tools on anonymizing documents they have written.

Anonymouth makes use of [JStylo](https://github.com/psal/jstylo) libraries (an author detection application also develped by PSAL) to detect stylometric patterns and determine features (like word length, bigrams, trigrams, etc.) that the user should remove/add to help obsure their style and identity.
___
### Disclaimer
Though Anonymouth and it's team works hard to provide you with tools to help remove your identity from documents you have written, **IN NO WAY WE CAN GUARANTEE THAT YOUR DOCUMENT IS ANONYMOUS OR NOT ANONYMOUS**.<br>

Anonymouth is always giving you it's best guess, it's best idea of where your document stands, **though it should not be taken as an absolute** (for example, you could have forgotten to remove your name from the document and Anonymouth has no way to know that that's your name and should remove it). What we can say is Anonymouth is only as good as you make it, and when used right, can be helpful in guiding your document towards the right direction.

[Back to top](#top)
___
### <a id="dependencies"></a>Dependencies

[Java 7](https://www.oracle.com/technetwork/java/javase/archive-139210.html) is required to run Anonymouth. If you are unsure whether or not you have it installed, follow these steps to see:<br>
1. Open up your Terminal
2. Type "java -version" without the quotes
3. If you see something like `java version "1.7.x_xx"` then you're ready to go! If not, then that means you most likely don't have Java 7 installed.
___
### <a id="run"></a>Running Anonymouth

The simplest way to run Anonymouth is to check out the `compiled` [branch](https://github.com/spencermwoo/anonymouth/tree/compiled) and run the compiled program.

[Back to top](#top)
___
### <a id="installation"></a>IDE and Development Setup
*Note: This is currently the only way to compile and run Anonymouth. We will be including an updated build file soon so that you may build and run Anonymouth easily with a certain command.*

The quickest way to install Anonymouth is to clone or download the zip of the <a href="https://github.com/psal/anonymouth">Anonymouth github project here</a>.

Import this project as an existing project into Eclipse (or clone and import directly within [Eclipse](https://www.eclipse.org/ide/) if you have the [Eclipse eGit plugin](https://www.eclipse.org/egit/download/)). Also make sure that Java 7 is your selected compiler by checking `Preferences/Java/Compiler` and is an included Library in your Java Build Path.

Anonymouth requires the included `jsan_resources` directory in it's running directory (The main Anonymouth directory containing lib, src, etc.). It should be in the correct directory by default.

Anonymouth requires a corpus (basically a database of other authors and documents they have written) to run. These allows your documents to be classified with respect to other stored documents and styles. Anonymouth will then give you an idea of how anonymous it thinks your document is and what features are to be removed or added to help you get there. Three different corpi are included in the project directory for you to choose, and are located at:

* `./anonymouth/jsan_resources/corpora/amt`
* `./anonymouth/jsan_resources/corpora/drexel_1`
* `./anonymouth/jsan_resources/enron_demo`

Though we included corpi, you are more than welcome to use any other corpus you may have. It is recommended to use many different combinations of authors so you can get the best possible picture of where your document stands anonymously in regards to the others.

Anonymouth also needs the following jars in the lib directory (everything should already be included):

<table>
  <tr>
    <th>Package Name</th><th>Version</th>
  </tr>
  <tr>
    <td>weka</td><td>3.7.9</td>
  </tr>
  <tr>
    <td>fasttag</td><td>2.0</td>
  </tr>
  <tr>
    <td>Jama</td><td>1.0.3</td>
  </tr>
  <tr>
    <td>jaws</td><td>1.3</td>
  </tr>
  <tr>
    <td>jcommon</td><td>1.0</td>
  </tr>
  <tr>
    <td>freechart</td><td>1.0.14</td>
  </tr>
  <tr>
    <td>jgaap</td><td>5.4.0</td>
  </tr>
  <tr>
    <td>microsoft translator</td><td>0.6.1</td>
  </tr>
  <tr>
    <td>miglayout</td><td>4.0</td>
  </tr>
  <tr>
    <td>tt4j</td><td>1.0.15</td>
  </tr>
  <tr>
    <td>Stanford postagger</td><td>-</td>
  </tr>
  <tr>
    <td>ui</td><td>-</td>
  </tr>
</table>



Once Anonymouth is all set up in Eclipse, you need only run [ThePresident](https://github.com/jjjimenez100/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/gooie/ThePresident.java) from the package [edu.drexel.psal.anonymouth.gooie](https://github.com/jjjimenez100/anonymouth/tree/master/src/edu/drexel/psal/anonymouth/gooie) to begin using it.

Please note that there are two main package categories, JStylo and Anonymouth. The majority of Anonymouth development should be in the Anonymouth packages as Anonymouth simply uses the JStylo libraries for parts of the initial document process, so beginners need only concern themselves with the Anonymouth packages.


[Back to top](#top)


# Development

### <a id="basic-logic-flow"></a>Basic Logic Flow

##### ↓ ---LAUNCH---


<b>Setup and start up:</b> [anonymouth.gooie.ThePresident](https://github.com/spencermwoo/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/gooie/ThePresident.java)

Should never be accessed in any other class (or at least limit it). It's only purpose is to initialize the main class and other start up classes.

- Readies and displays splash screen
- Prepares the Logger
- Initializes the `GUIMain` instance (and with it all Anonymouth class instances)
- Displays the start window, which from there it takes over

##### ↓ ---AUTOMATICALLY DISPLAYS---

<b>Start up window:</b> [anonymouth.gooie.StartWindow](https://github.com/spencermwoo/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/gooie/StartWindow.java)

The first window that shows up (not counting the splash screen) when Anonymouth loads up. Allows the user to change advanced processing settings, access the pre process set up wizard, or start Anonymouth.

##### ↓ ---USER CLICKED START BUTTON---

<b>Initial document processing begins immediately with: </b> [anonymouth.engine.DocumentProcessor](https://github.com/spencermwoo/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/engine/DocumentProcessor.java)

Inititalized within GUIMain as should nearly all Anonymouth class instances, this holds the main method and thread that handles processing and reprocessing documents. All processing events can be traced back to this class.

##### ↓ ---PROCESSING COMPLETE---

<b>Main GUI Code:</b> [anonymouth.gooie.GUIMain](https://github.com/spencermwoo/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/gooie/GUIMain.java)

The main gui window is displayed. This is also the central "hub" for Anonymouth. This should be the main instance center, and anytime you want to access code from other classes from another class you more than likely will be going through this.

- Houses and initialized nearly all class instances in Anonymouth
- Lays out and creates the main Anonymouth window

<b>From here the logic flow depends largely on what the user does:</b>

- If they're editing in the editor, the main class handling that is [anonymouth.googie.EditorDriver](https://github.com/spencermwoo/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/gooie/EditorDriver.java)
- If they are using translations the main class handling that is [anonymouth.gooie.TranslationsPanel](https://github.com/spencermwoo/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/gooie/TranslationsPanel.java)
- If they are using word suggestions, the main class handling that is [anonymouth.gooie.WordSuggestionsDriver](https://github.com/spencermwoo/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/gooie/WordSuggestionsDriver.java)
- If they are changing Preferences, the main class handling that is [anonymouth.gooie.PreferencesWindow](https://github.com/spencermwoo/anonymouth/blob/master/src/edu/drexel/psal/anonymouth/gooie/PreferencesWindow.java)
- etc.

[Back to top](#top)
___
### <a id="basic-class-structure"></a>Basic Class Structure

##### ---Naming Convention---

For the most part, Anonymouth splits UI objects into two classes: **[Class name]Panel/Window and [Class name]Driver**.  By convention and a general guideline, the Panel/Window class:

- Creates and lays out all swing components
- Handles all get, set, and is methods (if any)
- Handles assert methods (if any)
- Handles UI update/panel switch methods (if any)

While the corresponding Driver class:

- Handles all listeners
- Handles most backend/data manipulation and updating

Again, these are just general guidelines. Sometimes it makes more sense to just have one class handle everything if it's a small object, or sometimes it doesn't make sense to have a separate Panel/Window class but it does to have a Driver class, etc. You just need to use your best judgement on what will make things more organized and easier to understand.

##### ---Package / Organizing Convention---

Anonymouth loosly follows these guidelines for class organization in packages:

- [anonymouth.engine](https://github.com/spencermwoo/anonymouth/tree/master/src/edu/drexel/psal/anonymouth/engine) - for all processing code and any classes you deem "enginey" (for example, `HighlighterEngine`, `VersionControl`, etc.)
- [anonymouth.gooie](https://github.com/spencermwoo/anonymouth/tree/master/src/edu/drexel/psal/anonymouth/gooie) - for all classes displaying or creating swing components and their respective Driver classes
- [anonymouth.helpers](https://github.com/spencermwoo/anonymouth/tree/master/src/edu/drexel/psal/anonymouth/helpers) - for classes that aren't necessarily Anonymouth specific, but are used by Anonymouth for general purposes and tasks (for example, `FileHelper`, `ScrollToTop`, `ImageLoader`, etc.)
- [anonymouth.utils](https://github.com/spencermwoo/anonymouth/tree/master/src/edu/drexel/psal/anonymouth/utils) - for classes that serve only as a means for storing and manupulating data (For example, `TaggedSentence`, `TaggedDocument`, `Word`, `TextWrapper`, etc.)

There are still quite a few classes that are clearly where they don't belong, so feel free to organize Anonymouth so that it best fits these guidelines.

[Back to top](#top)
___
### <a id="to-do-list"></a>To Do List
Add features as they are conceived and ~~strikethrough~~ as they are completed ([1] means most important and [5] means relatively small and not particularly a priority at the moment)

- [1] AUTOMATE AS MUCH OF THE ANONYMIZATION PROCESS AS POSSIBLE. This should be the top priority as of now, see Andrew for the plan and details.
- [1] An internal  thesaurus must be implemented to help users change words to remove (that or nicely implement the one built into the system, preferable if possible)
- [2] An intelligent method to search and filter through words to add (start with simple search box, then possibly extend to automatic filtering based on synonyms?)
- [5] The clusters window should be updated to be easier to understand and use (it's hidden away in `Window > Clusters`)

[Back to top](#top)
___
### <a id="known-bugs"></a>Known Bugs
Add bugs as they are discovered and ~~strikethrough~~ as they are completed ([1] means fatal or breaks usability and [5] means relatively small and does not have much of an impact on usability)

- [1] During processing on OS X (though the problem may extend to other operating systems as well) the Stanford POS tagger is extremely prone to breaking due to a fatal threading issue which results in heap space or out of memory exceptions. This absolutely MUST be fixed.
- [2] The threading with the words to add refresh is not that great, fails to refresh at times and throws exceptions every once in a while.
- [3] For whatever reason, Anonymouth does not seem to process or recognize all cap words LIKE THIS when working in the editor.
- [5] The max features slider in Preferences does not work as expected at times and is a little finicky.
- [5] Currently Anonymouth is all running on the initial thread which <a href="http://docs.oracle.com/javase/tutorial/uiswing/concurrency/initial.html">should NOT be the case</a>. This should be done in a GUI creation and show task thread, though when I tried this in the past it breaks the slash screen.

[Back to top](#top)

# Credits

### <a id="developers"></a>Developers

P.I. Dr. Rachel Greenstadt:

- Forward questions or concerns pertaining to the lab or its other projects to <greenie@cs.drexel.edu>

Developed by:

  - Andrew W.E. McDonald
  	- Forward questions or concerns pertaining to Anonymouth in general or document processing to <awm32@cs.drexel.edu>
  - Marc Barrowclift
  	- Forward questions or concerns pertaining to Anonymouth's UI or front end/editor to <meb388@drexel.edu>
  - Jeff Ulman
  - Joe Muoio
  
[Back to top](#top)

### <a id="license"></a>License

Anonymouth was released by the Privacy, Security and Automation lab at Drexel University in 2011 under the AGPLv3 license. A copy of this license is included with the repository/program. If for some reason it is absent, it can be viewed <a href="http://www.gnu.org/licenses/agpl.html">here</a>.

[Back to top](#top)
