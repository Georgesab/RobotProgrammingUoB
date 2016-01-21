# RobotProgrammingUoB

<h1> Setting up LeJOS on OS X <h1>
<p> Tested on OS X 10.11.3 </p>

<h2> Setting up files and drivers </h2>

1. Download and install Java 6 (1.6) from <a href="https://support.apple.com/kb/dl1572?locale=en_GB"> here<a>. This is the last version of Java on OS X that works in 32-bit mode, which is needed for the Fantom drivers.

2. Download and install the Fantom driver from <a href="http://www.lego.com/en-us/mindstorms> here.</a>. Click downloads and then scroll down the page till you find "Download the NXT Fantom Driver". Once downloaded, click the .pkg file and follow the instructions.
 
3. Download LeJOS from <a href="http://sourceforge.net/projects/nxt.lejos.p/files/"> here.</a>  The file you want is **0.9.1beta3/leJOS_NXJ_0.9.1beta-3.tar.gz** 

4. Extract **leJOS_NXJ_0.9.1beta-3.tar.gz** into a directory of your choice, e.g. 'Documents/SDKs'

5. Delete the build folder in the root directory of the leJOS folder.

6. Now you need to edit your PATH variables, the easiest way to do this is open a terminal, ensure you are at the root (type <code>cd</code>) and then type <code>vim .bash_profile.</code> To start editing press I.

  You want to add the following to the file:
  
  <code>export NXJ_HOME="**PATH_TO_leJOS_NXJ**" (replace with where you saved the folder) </code>  
  
  <code>export LEJOS_NXT_JAVA_HOME="/usr/libexec/java_home -v 1.6.0_65-b14-468" </code>  
  
  <code>export PATH="$NXJ_HOME/bin:$PATH" </code> 
  
7. To exit and save, press **'esc'** then type **:wq** to write and quit.

8. To test this, restart your terminal and type <code>nxjflashg</code>. If the GUI appears, you have set it up correctly. 

<h2> Setting up Eclipse <h2>

1. You want to download a 32-bit version of Eclipse, since the 64-bit version does not work with the Fantom driver. The last version to support 32-bit was <a href="http://www.eclipse.org/downloads/packages/release/luna/sr2"> Luna SR2. </a>. You want the 32-bit version for Mac Cocoa.

2. Extract the Eclipse folder to a directory of your choice.

3. Start Eclipse. If you want this to be your only version, you can select your existing workspace, or create a new one if you haven't. If you wish to use 2 versions of Eclipse, I would recommend creating a new workspace, e.g. 'Documents/workspace32'.

4. Once Eclipse has loaded, go to Help > Install New Software > and paste the following into the 'Work with:' box "http://www.lejos.org/tools/eclipse/plugin/nxj/"

5. Select leJOS NXT Support when given a list of plug-ins, then follow the prompts to install the plugin, restarting Eclipse when asked.

6. Now you want to ensure Eclipse is pointing to your downloaded leJOS download. Go to the 'Eclipse' menu > Preferences > leJOS NXJ and make NXJ_Home point to where you placed the earlier downloaded **leJOS_NXJ_0.9.1...** file.

7. Whilst in the same menu, set 'connection type' to USB only to avoid bluetooth errors

8. Ensure eclipse is reading your installed Java 6 installation by again going to the 'Eclipse' menu > Preferences > Java > Installed JREs. If it does not appear here, click Add and follow the instructions.

<h3> Setting up packages <h3>

Best to follow the options on <a href = "https://canvas.bham.ac.uk/courses/15668/assignments/50340"> Canvas </a>.

**NOTE**: When creating a NXT project to run on the robot, right-click the project > Properties > Java Compiler and enable project specific settings and select Java 1.6. This is so that it uses Java 6 for the project. The rest of your imported projects, or projects to run in the simulator should default or be set to Java 8/1.8. 

**NOTE 2**: Make sure when you are creating a NXT project to run on the robot, that y Java Build Path > Libraries that the JRE system library is not included. You should only need the LeJOS NXT Runtime. If this is included, it will cause a Java heap overflow error on execution. 

<h3> Flashing your robot </h3>

Not all robots will have leJOS installed.

1. Hold the reset button on the bottom of the NXT for around 4 seconds until you hear a ticking sound.
2. Plug the robot in via USB and then open a terminal and type <code>nxjflashg</code>. 
3. Press "Flash lejOS firmware" and follow the instructions. 
4. Your robot should now reboot with leJOS installed. 


<h4> Pages used </h4>

<li>
<ul>leJOS on OS X page on Canvas https://canvas.bham.ac.uk/courses/15668/pages/lejos-on-os-x</ul>
</li>
