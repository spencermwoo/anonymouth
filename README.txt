Anonymouth
-Document Anonymization Tool
-Version: 0.5

----------------------------------------------------

The Privacy, Security and Automation Lab (PSAL)
Drexel University, Philadelphia PA
http://psal.cs.drexel.edu/

----------------------------------------------------

P.I.
	Dr. Rachel Greenstadt	-greenie@cs.drexel.edu

Developed by:
	Andrew W.E. McDonald	-awm32@cs.drexel.edu
	Marc Barrowclift		-meb388@cs.drexel.edu
	Jeff Ulman
	Joe Muoio

====================================================
-------------------DEPENDENCIES---------------------
====================================================

Java 7 is required to run Anonymouth. If you don't
yet have it, get it at Oracle's website here and
follow the installation instructions there:

http://java.com/en/download/index.jsp

If you are unsure whether or not you have it
installed, follow these steps to see:
OS X:
	-Open up Terminal (Applications/Utilities)
	-Type "java -version" without the quotes
	-If you see something like:

		java version "1.7.x_xx"

	 then you're ready to go! If not, then that
	 means you most likely don't have Java 7
	 installed, in which case you should go to the
	 download link above
WINDOWS:
	-Follow the instructions here:

	 http://www.java.com/en/download/help/version_
	 manual.xml

	 if you have version "1.7.x_xx", then you're
	 good to go! If not, then that means you most
	 likely don't have Java 7 installed, in which
	 case you should go to the download link above

If you are using Eclipse, also make sure that Java
7 is your selected compiler (Preferences/Java/
Compiler) and is an included Library in your java
Build Path (Not sure how to do this? Google is your
friend).

----------------------------------------------------

Anonymouth requires the included jsan_resources
directory in it's running directory (The main
Anonymouth directory containing lib, src, etc.). It
should be in the correct directy by default.

----------------------------------------------------

Anonymouth requires a corpus (basically a database
of other authors and documents they have written) to
run. It needs this so it can classify your documents
with respect to these other documents and their
styles so that Anonymouth can give you an idea of
how anonymous it thinks your document is and what
features to remove/add to help you get there. Three
different corpi are included in the project
directory for you to choose and are located at:

./anonymouth/jsan_resources/corpora/amt
./anonymouth/jsan_resources/corpora/drexel_1
./anonymouth/jsan_resources/enron_demo

Though we included corpi, you are more than welcome
to use any other corpus you may have. It is
recommended to use many different combinations of
authors so you can get the best posisble picture of
where your document stands anonymously with respect
to others.

====================================================
---------------------LICENSE------------------------
====================================================

License:

JStylo was released by the Privacy, Security and
Automation lab at Drexel University in 2011 under
the AGPLv3 license. A copy of this license is
included with the repository/program. If for some
reason it is absent, it can be viewed here:
http://www.gnu.org/licenses/agpl.htmla