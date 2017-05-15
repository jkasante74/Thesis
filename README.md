INSTALLING Iterated-PD-Tournament-WithGUI-5.0

1. INTRODUCTION

This Thesis studies the evolution of cooperative behavior in a variation of the classical Iterated Prisoner's Dilemma game structured in the form of iterated tournaments where individual agents using partial information about past behaviors of future opponents (that are exhibited against other players) to adjust their own strategies at different levels of information acquisition uncertainties.

In order to arrive at a conclusion, a simulation model, as well as experiments will be performed. This README file explains how to import and run the Iterated-PD-Tournament-WithGUI-8.0 implementation developed for the model. The simulation software is freely available for distribution and experimentation.

The implementation of the simulator is divided into six main packages that represent the main components of the System's Architecture: ExternalSystem, FrontEnd, MasModel, parameter Manager, Simulation logger and SimulationEngine.

These packages are collections of JAVA programs some of which are adopted from external sources and implemented to provide services such as creating line graph, and scheduling of tournaments in Round Robin structure.  

The packages shown in this implementation are described as the main components in the System Architecture section of the Thesis titled An Iterated Round Robin Tournament of the Prisoner Dilemma Game and the Evolution of Cooperation. 

By Jonathan Nyantakyi.




2. INSTALLATION


2.1 Requirements

The software requirements

  - Java Eclipse IDE version Kepler or higher with capacity to support J-Free-Charts 1.0.19
  - J-Free-Charts 1.0.19 Java library
  - Microsoft Excel 2003 or Matlab version 6 or higher.


I have successfully compiled Iterated-PD-Tournament-WithGUI-7.0 under the following operating systems and compiler versions:

  - Mac OS X with Eclipse IDE and JDK Compliance level 1.6 

  - Running on other operating systems with Java such as Microsoft Windows should also  
    work just fine.




2.2 Unpacking the archive

To install,

1) Download the compressed archive file "Iterated-PD-Tournament-WithGUI-7.0".

2) Import the compressed file into Eclipse IDE Kepler or above using the steps below:

	a. Right-click any space in the package Explorer pane.
	b. Select the "Import..." option.
	c. Choose "Existing Projects into Workspace" and choose Next.
	d. Choose the "Select archive file" option and browse to import the compressed program file.
	e. Click "Finish" to import the program.

	This will create a new project labelled "Iterated-PD-Tournament-WithGUI-7.0" which contains the source 
	code.



2.3 Importing Supporting Libraries

To perform a simulation experiment, it is important to ensure that all other required external libraries are first imported

1. Right click on the "Iterated-PD-Tournament-WithGUI-7.0" project in your package explorer and select "Properties" 
2. In the Properties dialog, click on "Java Build Path" to show the various imported libraries.
3. Click on add "External Libraries JARS"
4. Locate the libraries "jcommon-1.0.23.jar" and "jfreechart-1.0.19,jar" in the externalLibraries folder.
5. Click on "Open" and "OK".


3. RUNNING THE PROGRAM


You have several options available to run the implementation


3.1 Run In Eclipse

If you want to run the in an IDE, such as Eclipse, follow the instruction 
below;

1. Expand the project "Iterated-PD-Tournament-WithGUI-7.0". 
2. Locate the "FirstView.java" file in the "frontEnd" and then "GUI" package.
3. Right-Click on the file "FirstView.java"
4. Select "Run As" option
5. Choose "Java Application" to run the program.



3.2 Compile And Run On The Command Line

If you know how to compile programs on the command line, and if you have
downloaded the program, you can easily compile and run.
Just change directory in terminal into "Iterated-PD-Tournament-WithGUI-7.0" and use
the command 
                  javac FirstView.java
                  
to compile the FirstView.java.  
As long as your compiler supports Java 7 or higher, there should be no errors.  


NOTE : (You might see some warnings, especially if you use a newer version of java, but warnings do not stop a program from being compiled or executed.)  
		You can then run individual programs using the java command.  


3. PACKAGES AND CLASSES



a. externalSystem/   							--  Holds files with documentation for external services such as graphing.

	CusLineChart.java            				--  Creates line graph in customized competitions
	CusLineCharts.java            				--  Creates line graph in customized competitions
	RandomLineChart.java						--  Creates line graph in randomized competitions
	
	externalSystem/ externalLibraries			-- Holds libraries required to run this implementation
		jcommon-1.0.23.jar						-- provides library support to display line chart
		jfreechart-1.0.19.jar					-- provides library support to display line chart
		
		

b. frontEnd/           							--  Holds files with documentation for all GUI components and Configuration Inspector component of the simulator.

	frontEnd/GUI								-- Hold files for GUI Components
		CusSimGUI.java  							--  Creates the GUI window for customized simulations
		FirstView.java   							--  Creates the GUI window for simulation options.
		PlayGameGUI.java							--  Creates the GUI window for a one on one Prisoner‚Äôs Dilemma game between user and computer 
		RandomSimGUI.java   						--  Creates the GUI window for randomized simulations
		
	frontEnd/Configuration Manager				-- Hold files for GUI Components
		ConfigManager.java  						-- Ensures that input parameter for an experiment are correct and meet simulation requirement
	


c. masModel/        							--  Holds files with documentation for all components (subpackages) of the model 

	masModel/agents 							-- Holds files and classes for the agent's reasoning, strategies, and actions
		CusAgentsAction.java  	 					--  Holds functions for the implementation of various agents‚Äô actions in customized simulations.
    	CusStrategies.java   						--  Holds functions for the implementation of various strategies in customized simulations.             	
		OneOnOneStrategies.java   					--  Holds functions for the implementation of various strategies for computer when in one on one game against user.
		RandomAgentsAction.java   					--  Holds functions for the implementation of various agents‚Äô actions in randomized simulations.
		RandomStrategies.java   					--  Holds functions for the implementation of various strategies in customized simulations. 

	masModel/microWorld        					-- Holds files that provides the platform for agents to perform their actions. 
		CusSim.java   								--  Simulation model environment component for customized simulation experiment.  
		RandomSim.java   							--  Simulation model environment component for randomized simulation experiment.
		
	HisDbase									-- Holds a dBase of all agent's actions during tournament(s)
		
	
		
d.  paramManager								-- This package holds classes responsible for parameter checking during simulation
		RulesSetup.java   							--  Parameter(payoff matrix,  management component 
		
		
		
e.  simLogger									-- This package holds classes responsible for logging different forms of simulation.
		CusSimlogGUI.java   						--  Logs players matching, strategies, actions and scores displayed in a window for a customized simulation.
		RandomSimLogGUI.java   						--  Logs players matching, strategies, actions and scores displayed in a window for a random simulation.



d. simulationEngine/     		--  Holds files for controlling the executions of simulation experiments.
	CusPrintOutputs.java   		--  Simulation engine component for reporting on simulation, tournament, round, and matches in customized simulation experiment.
	CusScores.java   		--  Simulation engine component for handling customized simulation matches (Match Handler).
	OneOnOne.java   		--  Simulation engine component for handling one on one simulation games.
	RandomPrintOutputs.java   	--  Simulation engine for reporting on simulation, tournament, round, and matches in customized simulation experiment.
	RandomScores.java   		--  Simulation engine component for handling customized simulation matches.
	
	




More descriptions of these classes and the various methods  can be found in the javadoc file attached to the implementation code or as block comments at the beginning of each method.


4. EXTERNAL CODES ADOPTED AND MODIFIED

a. SimpleLineChart : 
      
	Used in files : CusLineChart.java , CusLineCharts.java, RandomLineChart.java 
      	
	Adopted and modified from : http://www.advsofteng.com/doc/cdjavadoc/simpleline.htm 


b. RoundRobinScheduling :

	Used in files : CusGame.java , RandomSim.java

	Adopted and modified from : http://bluebones.net/2005/05/generating-fixture-lists/comment-page-1/
