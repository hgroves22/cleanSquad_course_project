# Simulated Cleaning Robot Fleet Management System

## A fully functional management system written in C++ that enables users to send custom-designed robots to clean simulated rooms through a Command Line Interface (CLI).

This project was developed by me and three classmates as part of our Software Engineering elective in the fall of 2023. Throughout the four-month project, we applied the Scrum framework to practice effective Agile development. Below, you will find details on the program's main functions, along with instructions on installation and usage

## Features

### 1.) Simulation Options
At the start of the program, the user can select either a default simulation or create a custom simulation.

* Default Simulation: Automatically generates 12 robots: one of each size (small, medium, large) and type (mopper, vacuum, scrubber), as well as an additional large robot of each type to help demonstrate the program. It also generates 6 rooms: one of each size (small, medium, large) with one of the medium-sized rooms designated to not be cleaned.
  
* Custom Simulation: Allows the user to create any number of robots and rooms, and allows them to specify their size and types as well.

### 2.) CLI Functionalities
The CLI provides the following options to manage robots and rooms within the simulation:

* 1.) Creating New Tasks: Prompts the user to select which room they want to clean. It is required that the room's "Clean Status" is set to "Dirty" for this to continue. This will set the status of the room to "Cleaning". Once selected, the program will automatically send the necessary robots to the room to start cleaning it and will return when their battery runs out or the task is completed. This is tracked in real time depending on the robot's battery life as well as required cleaning times of each room. We used multithreading to allow each robot to be on their own timetable. While each robot is sent on a task, they spin a thread which properly accounts for the time they should be on this task. After all the robots are made available again, and all the necessary time for mopping/vacuuming/scrubbing is complete, the room will be set to Clean.
  
* 2.) Printing Available Robots: Returns a visual of all the robots that are not actively assigned to "Clean" a room and that are not broken and being repaired. The information shown for each robot is: RobotID, Robot Size, Robot Type, Probability of Failure, and Battery Remaining
  
* 3.) Printing Rooms: Returns a visual of all the rooms in the building. The information shown for each robot is: RoomID, Room Size, Mop/Vacuum/Scrub Time required, and the "Clean Status". RoomID: 0 is always designated as a default room that the robots stay in when not cleaning and will always be programmed.

* 4.) Set Room to DO NOT CLEAN: Allows the user to set a room's "Clean Status" to "Do Not Clean" preventing any tasks to send robots to that room.

* 5.) Make All Clean Rooms Dirty: Changes all the "Clean Status" of every "Clean" room to "Dirty" allowing tasks to send robots there.

* 6.) Charging All Robots: Every robot has an attribute called Battery Remaining which depletes when they get sent to clean each room. Every second that a robot is working on a task accounts for 10 battery. Once a robot has 0 battery, they are unable to be sent on a task to clean rooms. This operation charges all the robots that are not sent on a task at a rate of 10 battery a second.

* 7.) Exit Simulation: This will end the simulation.

### 3.) MonogoDB
All simulation data, including rooms, robots, and tasks, is stored in a MongoDB database. As updates occur in the simulation, this data is logged and updated in real time.


## Installation
Below is a step by step guide to running this program. 

* 1.) Download all files in this repository
* 2.) Open the terminal and navigate to the build folder. This can be done with 'cd build/'.
* 3.) Run the 'cmake ..' command to build the program.
* 4.) Navigate to the app folder inside of build using 'cd app', then compile the simulation with 'make'.
* 5.) To start the simulation, run './main'

* You need to make sure your local machine has mongodb installed. This can be done with homebrew with the following commands: brew install mongocli.


### Design Structure
+ `Design` - This [folder](docs/design/DESIGN.md) contains all the diagrams designed for this project. There are Behavioral and Class Diagrams as well as Use Case Diagrams as well.


