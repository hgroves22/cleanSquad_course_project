# Simulated Cleaning Robot Fleet Management System

## A fully functional management system written in C++ that allows the user to work with a CLI to send designed robots to clean simulated rooms.

This project was developed by me and three classmates as part of our Software Engineering elective  in the fall of 2023. Throughout the four-month project, we applied the Scrum framework to learn and implement effective Agile development practices. Both the functions of the program and how to initially install/run it are below. 

## The main functions that are available to the user with this program:

### 1.) Default or Custom Simulation: 
At the start of the program, the user will be prompted to choose either a default simulation, or create a custom simulation.

* The default simulation generates 12 robots: one of each size (small, medium, large) and type (mopper, vacuum, scrubber), as well as an additional large robot of each type to help demonstrate the program.
  
* The default simulation also generates 6 rooms: one of each size (small, medium, large) with one of the medium sized rooms designated to not be cleaned.
  
* The custom simulation allows the user to create any amount of robots and rooms, and allows them to specify the typing as well.

### 2.) Various CLI Functions
Once deciding the type of simulation the user wants to run, they are then shown the CLI consisting of different options. 

* Creating new tasks:
* 2.) Printing Available Robots: This will return all the robots that are not actively assigned to clean a room and that are not broken and being repaired. The information shown for each robot is: Robot ID, Robot Size, Robot Type, Probability of Failure, and Battery Remaining
* 
* 3.) 
### 3.) Testing

### Something else
+ `docs` - this [folder](docs/README.md) maintains **all** of your project documentation: `puml` files and `README`s. You will have deliverables that require updating this documentation.
+ `include` - the [include](include/INCLUDE.md) files for the libraries your team makes
+ `src` - the [source](src/SRC.md) files for libraries you decide to split out the implementation
+ `app` - the [main application(s)](app/APP.md) of the project
+ `tests` - a battery of [tests](tests/TESTS.md) tests for your libraries and app

## How to run this program


