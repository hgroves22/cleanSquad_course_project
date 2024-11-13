# Simulated Cleaning Robot Fleet Management System

## A fully functional management system written in C++ that allows the user to work with a CLI to send designed robots to clean simulated rooms.

This project was developed by me and three classmates as part of our Software Engineering elective  in the fall of 2023. Throughout the four-month project, we applied the Scrum framework to learn and implement effective Agile development practices. Both the functions of the program and how to initially install/run it are below. 

## The main functions that are available to the user with this program:

### 1.) Default or Custom Simulation: 
At the start of the program, the user will be prompted to choose either a default simulation, or create a custom simulation.

* The default simulation generates 12 robots: one of each size (small, medium, large) and type (mopper, vacuum, scrubber), as well as an additional large robot of each type to help demonstrate the program.
  
* The default simulation also generates 6 rooms: one of each size (small, medium, large) with one of the medium sized rooms designated to not be cleaned.
  
* The custom simulation allows the user to create any amount of robots and rooms, and allows them to specify the typing as well.

### 2.) CLI Properties
Once deciding the type of simulation the user wants to run, they are then shown the CLI consisting of different options. 

* 1.) Creating New Tasks: Prompts the user to select which room they want to clean. It is required that the room's Clean Status is set to dirty for this to continue. This will set the status of the room to Cleaning. Once selected, the program will automatically send the necessary robots to the room to start cleaning it and will return when their battery runs out or the task is completed. This is tracked in real time depending on the robot's battery life as well as required cleaning times of each room. We used multithreading to allow each robot to be on their own timetable. While each robot is sent on a task, they spin a thread which properly accounts for the time they should be on this task. After all the robots are made available again, and all the necessary time for mopping/vacuuming/scrubbing is complete, the room will be set to Clean.
  
* 2.) Printing Available Robots: Returns a visual of all the robots that are not actively assigned to clean a room and that are not broken and being repaired. The information shown for each robot is: RobotID, Robot Size, Robot Type, Probability of Failure, and Battery Remaining
  
* 3.) Printing Rooms: Returns a visual of all the rooms in the building. The information shown for each robot is: RoomID, Room Size, Mop/Vacuum/Scrub Time required, and the Clean Status. RoomID: 0 is always designated as a default room that the robots stay in when not cleaning and will always be programmed.

* 4.) Set Room to DO NOT CLEAN: Allows the user to set a room's Clean Status to "Do Not Clean" preventing any tasks to send robots to that room.

* 5.) Make All Clean Rooms Dirty: Changes all the Clean Status of every clean room to dirty allowing tasks to send robots there.

* 6.) Charging All Robots: Every robot has an attribute called Battery Remaining which depletes when they get sent to clean each room. Every second that a robot is working on a task accounts for 10 battery. Once a robot has 0 battery, they are unable to be sent on a task to clean rooms. This operation charges all the robots that are not sent on a task at a rate of 10 battery a second.

* 7.) Exit Simulation: This will end the simulation.

### 3.) MonogoDB



### Something else
+ `docs` - this [folder](docs/README.md) maintains **all** of your project documentation: `puml` files and `README`s. You will have deliverables that require updating this documentation.
+ `include` - the [include](include/INCLUDE.md) files for the libraries your team makes
+ `src` - the [source](src/SRC.md) files for libraries you decide to split out the implementation
+ `app` - the [main application(s)](app/APP.md) of the project
+ `tests` - a battery of [tests](tests/TESTS.md) tests for your libraries and app

## How to run this program


