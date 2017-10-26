# OPCSM-VAI
Development environment for automation and IoT (Internet of Things) base on state diagrams programing and powered by OPC, TCP/IP, bluetooth, USB/Serial comm, aso.

*****************************
Antonio Tamairón Pérez - 2016
*****************************

A. ABOUT OPCSM VAI (OPC Statematic Virtual Automation Interpreter)
------------------------------------------------------------------
This software is an interpreter for automation and GUI development environment to implement automation process through state diagrams.
This one is part of project in progress, to automate easly any process.

The environmet works through project -> documents -> objects, then;

1. Need to create a project
2. Need to add so many documents to going to use.
3. Need to add objects and link these in order to compose a tree according to the process to be implemented.

HOW OPCSM VAI works?
Well, when you have implemented the process (program as state diagram) you can simulate it. 
At least one of the elements must be marked (like PETRI nets). The runtimer execute those marked elements and go to next elements 
according to arrows. Each element has a special function (see below) when the element is triggered.

The interpreter use a memory shared system in order to permit a data sharing between elements for all documents (entire project) then
each element have a own variable (MyVariable) generated in sharing memory system, when it is created.

<b>NOTE: Mark means the element is prepared to be executed (green filled). Un-marked means the element wait until is marked again.</b>

OPCSM VAI has a toolbox with several elements.

 - STATE -
   Puts "1" in 'MyVariable' when is triggered and puts "0" when is not marked. 
   Has a special mode "TOGGLE" then when is trigger change the previous value and
   keep it until new trigger.
   
 - TRANSITION -
   Leaves to continue program if the variable assigned is "1" in another case, pause the branch.
   
 - CONDITION
   Function similar to transition but complex conditions. Powered by conditions scripts.
   
 - COUNTER
   Simple counter up/down with pre-charge. It's possible to pre-charge on run time.
   
 - EXPRESSION
   Complex mathematical expressions.
   
 - OPC
   Element that permits W/R OPC data thanks to OPC server (need a OPC server local or remote)
   
 - TIMER
   Simple timer. The timer step is based on simulator timer period.
   
 - VARIABLE
   Element to create other variables, assignation, aso.
 
 - END
   Stop simulator and finish simulation.
   
 - STOP
   Stop a simulation branch.

 Other interactive elements

 - INDICATOR
   Shows value of a variable.
   
 - GRAPH
   Draw value of a variable in a time-graph.
   
 - BUTTON
   Permits to user interacts with environment.

The environment now could be used as learning environment to undertand automation, play with OPC servers and hardware like PLCs, Domotic devices,
and all things that could interact with OPC. The next step is create a kernel for low cost hardware in order to execute the implemented program
with OPCSM VAI directly in hardware with RTOS as freeRTOS.

B. How to install
-----------------
1. Install OPC Core Components Redistributable previous to use the program.
   - Can load from OPC foundation "https://opcfoundation.org/developer-tools/developer-kits-classic/core-components" (Need registration for download)
   
2. Launch OPCSM.exe and enjoy!
