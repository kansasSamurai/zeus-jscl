================================================================================

  Zeus (zeus-jscl), a free Java Swing Components Library

  Version 1.70

  by Gregory Kotsaftis
  gregkotsaftis@yahoo.com
  (c) 2004-2011 Athens, Greece

================================================================================


INTRODUCTION
------------

  Zeus is a swing based components (widgets) library.
  The purpose of this library is to provide solid and useful swing components,
  to all of you, java GUI developers out there.
  After so many years using the opensource community projects, I think it's
  time for me to give something back...

        ANOTHER GUI LIBRARY, WHY? ... should you ask...
        Well this is why:
        During the last few years that I have worked especially with Java GUIs,
        I really had the need to find and use some nice widgets (e.g. like in
        win32 RAD tools, Delphi, VB, ...) If you use opensource tools like the
        Netbeans IDE or the Eclipse IDE, believe me you will have a really hard
        time creating java GUIs, since only the standard components are
        supported and most of the time you have to code the GUI by hand! Yes,
        back to the middle ages, RAD is science fiction for Java! At least up
        to now... :(
        Anyway, after endless hours browsing the net I came to realise that good
        and free GUI components were really hard to find. Moreover, many guys
        used the obsolete AWT or they extended the original Java Swing
        components to achieve their goals. The latter I think is much worse.
        Let me explain why. If you consider the actually infinite bugs that have
        been reported to Sun about Swings over the last years and the code
        changes their developers have made in order to solve some major design
        flaws, you will come to realize that most of the components out there
        that have been extending the swings are having major difficulties
        upgrading to newer Java versions.
        
        So, my main goal is to create GUI components that will only use the
        standard swings so as to be easy to upgrade and reuse, as Java evolves.
        I will try to minimize the need for 'extends' in any swing components
        and also try to avoid to create my own GUI components from scratch like
        for example IBM did with the SWT package, so as to be at all times
        compatible with Sun; yes we love you guys :)
        Other development goals for this library are:
        - Use of Java Patterns whenever possible.
        - Implement code from good examples found on articles/forums/books and 
          reference back to them when able.
        - Give more attention to code quality than to create more swing
          components (better to have less widgets but well written and really
          usefull ... that's my motivation!)
        - Simple is better! Do not implement complicated solutions for simple
          problems when a decent and easy solution will do instead.
          (We are not trying to get a PhD here...)


LICENSE
-------
  
  This library is distributed under LGPL license, please read the 'license.txt'
  before using this software. In short LGPL allows you to use this library in 
  opensource or commercial applications as-is. If you need to modify it or 
  add new code, you have to distribute the modified or new code with your
  application under LGPL.


SUPPORT / FEATURE REQUESTS / CODE CONTRIBUTION
----------------------------------------------

  Please e-mail me at: gregkotsaftis@yahoo.com
  and I promise I'll do my best.
  
  'Thank you' and 'Well done' emails REALLY appreciated,
  keeps up the spirit for me to go-on :)
  
  
QUICK START GUIDE
-----------------

  Check out the 'test' folder for test batch file(s). Execute them in order to
  get a good idea about the components already implemented.
  
  The actual library exists in 'lib' folder.
  
  I assume you have Java 1.6 runtime installed, if not edit the batch file(s)
  and add these lines:
  
  (example)
  
      set JAVA_HOME=C:\jdk1.6
      set PATH=%PATH%;%JAVA_HOME%\bin
  
  You should be OK now!
  
  Also feel free to read the javadocs for the library: doc/api/index.html


SWING COMPONENTS OVERVIEW
-------------------------

  Here you can read in detail about the major components implemented up to now.
  
  1 ) JConsole
      A java console to replace the command line window
      Redirects the stdout and stderr, customizable,
      can save the messages it a text file. In addition it can
      auto dump to a log file and clear the textarea.
      Can be used with JFrame, JInternalFrame or as a JPanel.
      If used in conjunction with any exe creator for java,
      e.g: the really great launch4j - http://launch4j.sourceforge.net/
      or JSmooth - http://jsmooth.sourceforge.net/
      you can eliminate the dos application windows and your application
      looks more professional.
  
  2 ) JMessage
      This component is similar to javax.swing.JOptionPane component.
      It can be used to display message and error dialogs. The main features of
      JMessage are:
      - Displays simple messages and the stacktrace of an exception
      - Supports html text for messages with build-in plain text conversion
      - The dialogs are modal. In addition they stay on top of other windows at
        all times
      - Supports for JOptionPane OK,CANCEL,YES,NO buttons
      - Selects a default button in the dialog
      - Supports all JOptionPane messageType(s) & optionType(s)
      - Uses UI default icons or user supplied icons
      - Uses localized dialog titles and button text, or user supplied text
      - Returns dialog status depending on which button was pressed
  
  3 ) JSplash
      A simple, yet nice splash screen implementation for java
      Follows Sun recommendations for splash screen and logos:
      see "Designing Graphics for Corporate and Product Identity"
      http://java.sun.com/products/jlf/ed2/book/HIG.Graphics7.html
      Draws a black border of one pixel wide around the splash
      image. Also uses a simple progress bar that the user must
      "progress" manually in his code in order for it to work.
      Also, it has options for percent display, custom loading
      messages display and application version string display at
      the bottom-right corner of the image.
  
  4 ) OutLookToolBar
      Provides the mouse over looks of microsoft outlook toolbar buttons
      on a simple JToolBar.
  
  5 ) SingleAppInstance
      This is actually a helper class rather than a swing component.
      Provides a simple solution to the multiple application instances problem.
      Just invoke onInit() at your application startup and onExit() at your 
      application shutdown and that's all there is to it. 
      SingleAppInstance creates and locks a file within the startup directory 
      so if anyone is to execute your application again the second onInit() call 
      fails with a message. The onExit() method unlocks and deletes the file.
      You can also customize the way SingleAppInstance informs the user, 
      e.g via JOptionPane popup window or stderr. Finally, you can easily
      translate the popup messages without modifing any code.
  
  6 ) WindowManager
      Provides almost any functionality you need to manage all JInternalFrames
      within a JDesktop.
  
  7 ) AutoResizeTableColumns
      This class can be used to dynamically resize a JTable, every time it's 
      data changes, based on header size and row data. It can also lock any or 
      all of the table's columns (no manual resize possible).
  
  8 ) ProgressBarCellRenderer
      Provide progress bar cell rendering inside a JTable's cell.
  
  9 ) TableSorter
      This is actually Sun's latest TableSorter version taken from the 
      Swing Tutorial with only a couple of modification in order to accept 
      custom icon images.
  
  10) TypeSafe API & SwingConfigurationManager
      SwingConfigurationManager is actually a convenient method to use the 
      "gr.zeus.ui.typesafe" package. It automatically configures your gui for 
      data validation using a property file. This is a component that was 
      missing from Swing and is usually found only in commercial libraries. 
      With this component you can automatically:
      - perform max and min character checks in fields
      - trim spaces
      - convert to uppercase/lowercase
      - accept only a set of characters inside a field (valid chars)
      - reject a set of characters inside a field (invalid chars)
      - replace a set of characters with another (replaceable/replaced character
        pairs)
      - convert, validate and limit check integer numbers: byte,short,int,long
      - convert, validate and limit check real numbers: float,double
      - convert and validate dates using a specified date pattern
      Also you can enable/disable a selectAll functionality upon focus for any
      field. Finally you can attach a custom Focus Traversal Policy that enables
      you to create a custom focus route for your fields, even if they exist in
      different containers. Special care is also taken for JTextArea, JTextPane
      and JEditorPane CTRL+TAB which is replaced with single TAB, making focus
      traversal much easier. And all these with minimal code inside your form
      and an external property file!
  
  
  Furthermore, you might want to check out package "gr.zeus.util", there are
  quite a few useful general library classes in there.
  
  
FOR DEVELOPERS
--------------

  I use Netbeans IDE to develop this project (hence the .form files)
  A small ANT script is also available to you. Execute it from the command
  line (need ant installation): 'build.bat', 'clean.bat'
  You should modify the: 'cp.bat', to match your installation.
  
Addendum:
This project requires Java8 and Ant 1.10*.
(A refactor for Maven is in progress)

If you use SDKMAN (which I strongly recommend), I have added
the .sdkmanrc file - then you can simply use the following commands:
> sdk env install
> ant clean
> ant clean all

* As I am not the original author, the Ant version is simply a latest
version I have that seems compatible.  