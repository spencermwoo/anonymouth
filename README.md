<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [<a id="top"></a>Anonymouth](#a-idtopaanonymouth)
- [Set Up](#set-up)
    - [<a id="introduction"></a>Introduction](#a-idintroductionaintroduction)
    - [Disclaimer](#disclaimer)
    - [<a id="dependencies"></a>Dependencies](#a-iddependenciesadependencies)
    - [<a id="run"></a>Running Anonymouth](#a-idrunarunning-anonymouth)
- [Credits](#credits)
    - [<a id="license"></a>License](#a-idlicensealicense)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# <a id="top"></a>Anonymouth

![](src/edu/drexel/psal/resources/graphics/readme_Logo.png)

A Document Anonymization Tool <br>
Version: 0.5<br>

The Privacy, Security and Automation Lab (PSAL)<br>
Drexel University, Philadelphia PA<br>
<https://psal.cs.drexel.edu/index.php/Main_Page>

# Set Up

### <a id="introduction"></a>Introduction

Anonymouth is a Java-based application aiming to provide users with tools on anonymizing documents they have written.

Anonymouth makes use of [JStylo](https://github.com/psal/jstylo) libraries (an author detection application also develped by PSAL) to detect stylometric patterns and determine features (like word length, bigrams, trigrams, etc.) that the user should remove/add to help obsure their style and identity.

### Disclaimer
Though Anonymouth and it's team works hard to provide you with tools to help remove your identity from documents you have written, **IN NO WAY WE CAN GUARANTEE THAT YOUR DOCUMENT IS ANONYMOUS OR NOT ANONYMOUS**.<br>

Anonymouth is always giving you it's best guess, it's best idea of where your document stands, **though it should not be taken as an absolute** (for example, you could have forgotten to remove your name from the document and Anonymouth has no way to know that that's your name and should remove it). What we can say is Anonymouth is only as good as you make it, and when used right, can be helpful in guiding your document towards the right direction.

### <a id="dependencies"></a>Dependencies

[Java 7](https://www.oracle.com/technetwork/java/javase/archive-139210.html) is required to run Anonymouth. If you are unsure whether or not you have it installed, follow these steps to see:<br>
1. Open up your Terminal
2. Type "java -version" without the quotes
3. If you see something like `java version "1.7.x_xx"` then you're ready to go! If not, then that means you most likely don't have Java 7 installed.

### <a id="run"></a>Running Anonymouth

The simplest way to run Anonymouth is to check out the `compiled` [branch](https://github.com/spencermwoo/anonymouth/tree/compiled) and run the compiled program.

# Credits

### <a id="license"></a>License

Anonymouth was released by the Privacy, Security and Automation lab at Drexel University in 2011 under the AGPLv3 license. A copy of this license is included with the repository/program. If for some reason it is absent, it can be viewed <a href="http://www.gnu.org/licenses/agpl.html">here</a>.
