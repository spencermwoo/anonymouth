# <a id="top"></a>Anonymouth

![](anonymouth_LOGO.png)

Document Anonymization Tool, Version 0.5<br>

The Privacy, Security and Automation Lab (PSAL)<br>
Drexel University, Philadelphia PA<br>
<http://psal.cs.drexel.edu/>

# Index
1. Set Up
	- [Dependencies](#dependencies)
	- [How To Run](#how-to-run)
	- [Usage](#usage)
2. Credits
	- [Developers](#developers)
	- [License](#license)

# Set Up

### <a id="dependencies"></a>Dependencies

Java 7 is required to run Anonymouth. If you don't yet have it, get it at <a href="http://java.com/en/download/index.jsp">Oracle's website here</a> and follow the installation instructions provided there.

If you are unsure whether or not you have it installed, follow these steps to see:
* OS X:
	1.  Open up Terminal (Applications/Utilities)
	2.  Type "java -version" without the quotes
	3.  If you see something like `java version "1.7.x_xx"` then you're ready to go! If not, then that means you most likely don't have Java 7 installed, in which case you should go to the download link above
* Windows:
	1.  Follow the instructions here: http://www.java.com/en/download/help/version_manual.xml. if you have version "1.7.x_xx", then you're good to go! If not, then that means you most likely don't have Java 7 installed, in which case you should go to the download link above
	
### <a id="how-to-run"></a>How To Run

Run the `anonymouth.jar` in the root directory
```sh
java -jar anonymouth.jar
```

### <a id="usage"></a>Usage

If you are using Eclipse, also make sure that Java 7 is your selected compiler by checking `Preferences/Java/Compiler` and is an included Library in your java Build Path (Not sure how to do this? Google is your friend).

Anonymouth requires the included `jsan_resources` directory in it's running directory (The main Anonymouth directory containing lib, src, etc.). It should be in the correct directy by default.

Anonymouth requires a corpus (basically a database of other authors and documents they have written) to run. It needs this so it can classify your documents with respect to these other documents and their styles so that Anonymouth can give you an idea of how anonymous it thinks your document is and what features to remove/add to help you get there. Three different corpi are included in the project directory for you to choose and are located at:

* `./anonymouth/jsan_resources/corpora/amt`
* `./anonymouth/jsan_resources/corpora/drexel_1`
* `./anonymouth/jsan_resources/enron_demo`

Though we included corpi, you are more than welcome to use any other corpus you may have. It is recommended to use many different combinations of authors so you can get the best posisble picture of where your document stands anonymously with respect to others.

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