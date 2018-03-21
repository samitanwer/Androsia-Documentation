
# Quickstart


This is the reference quickstart guide for users and developers, which is designed to get you up and running in minutes.


Dependencies
------------

Some basic prerequisites which you'll need in order to run Androsia:

* A Windows or UNIX-based operating system 
* Java JDK > 1.7
* android.jar corresponding to the ``targetSdkVersion`` for your Android application

Note: We have dichotomized the quickstart guide for **Users** and **Developers** 

Users
-----

The quickest way to start using Androsia is by downloading the JAR file: 
[Andros.jar](../../bin/Andros.jar) along with [AndroidCallbacks.txt](AndroidCallbacks.txt) and [SourcesAndSinks.txt](../../SourcesAndSinks.txt) files which are required by FlowDroid to create a callgraph. Place these two text files in the same directory as that of the JAR.


The JAR file takes three arguments:


    $ java -jar Andros.jar <PATH_TO_APK> <1 OR 2> <J OR A>
    
The first argument is the full path to the APK (including name of the APK) that is to be analysed.    
    
The second argument tells Androsia which analysis to perform, it could either be ``"1"`` or ``"2"``

If argument is ``"1"``, Androsia analyses the APK tracking ``StringBuilder`` objects which are local to methods and also those ``StringBuilder`` objects which are referenced by Static Field reference variables in the whole program.

If argument is ``"2"``, Androsia analyses the APK tracking ``StringBuilder`` objects which are referenced by Instance Field reference variables.

The third argument specifies the output format, it could be one of the following:

``J``: Generates output in Jimple format
``A``: Generates an APK file

The output is generated in a directory named  ``"sootOutput"`` in the same directory as the JAR file. Additionally, a text file named ``Results.txt`` is generated which lists the instrumentation points Androsia found.

Note: If you use "A" as the output format the APK generated will not be [zipaligned](https://developer.android.com/studio/command-line/zipalign.html) or [signed](https://developer.android.com/studio/publish/app-signing.html). You would have to follow instructions on the aforementioned hyperlinks to perform these operations.  


Developers
----------

Start by cloning the Androsia repo on GitHub:

    git clone https://github.com/samitanwer/Andros.git

Import the project as a Java project into your IDE. Modify location of Android SDK and optionally the Soot Output Directory in ``Config.java`` file.

The file ``StartTest.java`` is the starting point of the analysis which tracks ``StringBuilder`` objects which are local to methods and ``StringBuilder`` objects which are referenced by Static Field reference variables in the whole program. 

The file ``NewTest.java`` under ``InstanceField`` folder is the starting point for the analysis which tracks ``StringBuilder`` objects which are referenced by Instance Field reference variables.

Both ``StartTest.java`` and ``NewTest.java`` contain a hardcoded APK path, which developers can modify to use Androsia on their desired APKs.

Getting Support
---------------

For bug reports and feature requests, please file a GitHub issue.

If you have a question that isn't covered in this documentation, please reach out for help at my email address: samit1274 at iiitd dot ac dot in

Contributing to Androsia
-------------------------
I will gladly review and accept pull requests for Androsia. If you want to have a design discussion for your changes, please reach out to me on samit1274 at iiitd dot ac dot in.
