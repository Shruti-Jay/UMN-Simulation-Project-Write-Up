## Team Number
- 001-52

## YouTube Video
- [(https://youtu.be/WJLcOtXS_iY)]

## Docker Link
- [(https://hub.docker.com/repository/docker/lenz0187/final_project/general)]

## Team Members
- Shruti Jayavardhanan (jayav004)
- Walker Lenz (lenz0187)
- Grant Oie (oiexx032)
- Anna Poi (poi00001)

## Project Overview

This project is a culmination of the skills and knowledge acquired in C++ programming and program design throughout the course of the semester in 3081 Program Design & Development. The project focuses on the application of design patterns and agile development methodologies. The objective is to enhance the ongoing simulation project by designing and integrating new features that demonstrate basic design proficiency, technical ability, and creative problem-solving. Each feature aims to complement and expand the functionality of the existing codebase, ensuring compatibility and robustness.

## How to Run the Simulation
### Prerequisites
1. Navigate to the correct location of the program within the terminal. For our implementation that will be .../team-001-52-finalproject.
2. Ensure that a port is enabled. For our implementation, port 8081 is the local host that the simulation will be active on.
### Running the Simulation
1. Run the command "make -j". Wait for this to complete.
2. Run the command "make run".
3. Open up a localhost browser on the same machine.
4. Once inside the simulation, there are 2 main things to note. On the left there is a shaded box. This is the log where information about the simulation is displayed to the user. On the right, there is a control box that allows you to select the view of a specific entity, alter the simulation speed, toggle the route view on, schedule deliveries, add humans, add drones, and stop the simulation. 
5. To end the simulation, press the stop simulation button.
### Specific Actions
1. Scheduling trips
   - First click on the button "Schedule Trip".
   - The next 2 times you click on the simulation map will place a starting and ending location. To change the ending location click on a new spot on the map.
   - Add a name for your delivery in the "Name:     " entry box.
   - You can also change the delivery search strategy here by toggling the drop down icon at "Search Strategy". 
   - When you are ready to schedule the trip, select the "Submit" button
2. Tracking Entity
   - To track an entity we begin by selecting the "Change View:" drop down button.
   - From here select the give entity you would like the camera to focus on.
3. Adding Entities
   - Human
     - Click on the button "Add Human"
   - Drone
     - Click on the button "Add Drone"
### Extensions
1. Data Collection
   - Begin running the simulation as you would for regular use.
   - After the desired amount of trips have been scheduled, drones have been added, packages have been delivered, etc. the simulation can be terminated.
   - Navigate to the folder .../team-001-52-finalproject/DashboardData
   - Inside of this folder there will be 2 csv files that will be created/populated
     - The ownershipDetails csv file has information regarding the owner details of specific packages.
     - The tripDetails csv file has information regarding the moving of a specific package from point A to B.
   - Further analysis can be produced from these csv files.
2. Drone Specialization
   - Begin running the simulation as you would for regular use
   - Select a package type and weight before scheduling each delivery, weights should be between 0 and 150

## Simulation Overview
The simulation is a model of the University of Minnesota - Twin Cities campus and surrounding area that models drone delivery, human movement, helicopters, and intersections. The simulation provides the user the ability to simulate delivering packages across campus with the use of drones, using different delivery strategies. In addition to the main functionality of delivering packages via drones, the simulation also provides the user the ability to add humans and robots into the simulation, modeling how one might traverse campus. To further improve this simulation, we added two extensions, the data collection extension and the drone specialization extension. This simulation would be useful for companies that want to simulate their delivery processes and test new ideas.
### Movement of Entities
In the simulation, entities move in a variety of ways. Humans and helicopters are not controlled by the user, rather they are spawned in and move around the simulation without user interference. On the other hand, drones move around the simulation based on user-specified starting locations and ending locations. When the user decides to create a package delivery, two endpoints are chosen for the drone to traverse from. Initially, the drone beelines it to the starting position, where it then follows a designated strategy (BFS, DFS, Dijkstra, or AStar) to the endpoint. Packages and robots are the two entities that do not move in our simulation. Robots are spawned at the endpoint of a package delivery, while packages are spawned at the starting point. Finally, the packages are carried by the drone from the starting location to the ending location.
### Additional Simulation Mechanics
- The simulation can be sped up or slowed down with the use of a toggle that changes the dt variable. This allows the user to speed up the simulation of drone delivery.
- The simulation also allows for adding multiple entities throughout the simulation without crashing.


## Data Collection Feature
The Data Dashboard feature is designed to enhance the runtime capabilities of our 3D simulation project by implementing an advanced data collection and analysis tool. Utilizing the Singleton design pattern, this feature systematically captures and logs various performance metrics from each simulation run into a CSV file. Metrics such as speed, trip counts, fuel efficiency, directions, and positional data are recorded, providing a comprehensive dataset for subsequent analysis. This interface is very extensible, with minimal code required to add additional metric collection.

The Data Dashboard is significantly interesting because it provides a granular view of operational dynamics within the simulation, offering insights that are crucial for both development and business strategy. By aggregating data across multiple simulations, it allows for an in-depth understanding of performance trends and efficiency metrics, which are essential for optimizing the simulation’s design and functionality.

This feature adds a robust analytical layer to the existing drone simulation system. While the primary simulation focuses on operational dynamics, the Data Dashboard extends this by offering a tool for continuous performance monitoring and improvement. 

The Singleton pattern was chosen for the implementation of the Data Dashboard due to its need for a consistent and accessible data collection mechanism throughout the simulation environment. By ensuring that there is only one instance of the dashboard throughout the runtime, we maintain all data collection and analysis tasks centralized and synchronized, which is critical for accuracy and reliability in data logging.

To utilize the Data Dashboard feature, users need to initiate a simulation run as usual. When the Stop Simulation button is pressed, the collected data is processed and stored in two csv files in the directory 'DashboardData'. 

There are two csv file generated:
 - ownershipDetails.csv - captures data relevant to customer analysis: Owner ID, Owner Name, Destination, Package Name
 - tripDetails.csv - captures data relevant to drone performance analysis: Drone ID, Package ID, Time Elapsed, Start Position, Destination, Speed, Strategy

![Alt text](./UML/datadashboard-uml.png?raw=true "Data Collection UML Diagram")

In the presentation folder, there is breakdown of how the ownership and trip details can be used in a buisness setting. This was also included in our video.

## Drone Specialization Feature
The Drone Specialization feature allows users to specify the type of package delivery based on weight and food contents. These attributes cause the delivery to be assigned to a drone of a certain size, with or without a temperature controlled container. 

This feature allows users to simulate a more realistic variety of deliveries to account for a range of products and potential food delivery services. 

This feature is interesting because it allows for more specific types of deliveries and becomes applicable to a wider range of potential delivery services who might want to use our simulation. 

This feature implements the decorator design pattern in order to extend existing aspects of the simulation, such as by adding weight and food attributes to the packages, as well as size and contianer attributes to the drones. This pattern allowed for minimal modification of base classes such as drone and package. Additionally, the factory design pattern was extended to create the new container entities. 

### Instructions to Use New Feature

<img width="864" alt="Screen Shot 2024-04-30 at 11 58 06 AM" src="https://media.github.umn.edu/user/29338/files/6d032490-2886-48b3-b483-9a0dcd6c76c3">

## Sprint Retrospective
For our sprint retrospective, we decided to follow the guidelines that were linked to the scrum slide presented in class. [https://scrumguides.org/docs/scrumguide/v2020/2020-Scrum-Guide-US.pdf](url)

### Sprint 1
Our first 2 week sprint occurred from 04/09/2024 to 04/21/24. The goals of this first sprint were as follows:
- Determine 2 project extensions.
- Create scrum tasks.
- Begin implementation of extensions.

Things that went well:
- In the first meeting we were able to determine our extensions and break up our team in a timely and efficient manner.
- UML design and requirements were generated within a week.
- Multiple scrum tasks were created, assigned to team members, and documented in Jira.
- Start of and completion of extension 1 ahead of schedule.
- Productive use of team meetings.

Problems encountered:
- A few scrum goals were missed in the initial thought process.

Items Completed:
- Determine extensions
- Create UML for DataCollector
- First draft UML for Drone Specialization
- Figure out design of DataCollector
- Create header files for DataCollector
- Doxygen comment DataCollector
- Implement .ccp files for DataCollector
- DataCollector generate csv files upon simulation termination
- Integrate DataCollector into existing files
- Initial Drone Specialization files for PackageWeightDecorator and DroneSizeDecorators
- Initial Container and ContainerFactory .h and .cc files

Items Backlogged to Sprint 2 (generalized):
- Drone Specialization tasks
- Run Lint
- Dockerize
- Documentation
- Integration
- Creation of video and slideshow

Changes to Increase Effectiveness:
- Attend office hours in order to receive guidance on extensions.
- Communicate changes made to the extensions as soon as they are made.

To summarize our first sprint, we believe that we stayed on task or made excess progress for where we had planned to be. We were able to meet 2 times throughout this sprint, where we shared ideas, thoughts, and problems we were encountering. Through our implementation of the DataCollector system and progress made on the drone specialization extension, we were hitting our goals consistently throughout the first 2 week sprint. Some areas that we identified for improvement included deciding that we should meet with TAs in their office hours to get help with troubles encountered and communicating changes as they happen. With these ideas in mind, we went into our second 2 week sprint optimistic to finishing the project in a timely manner.

### Sprint 2
Our second 2 week sprint occurred from 04/22/2024 to 05/05/24. The goals of this second sprint were as follows:
- Complete implementation of DataDashboard.
- Complete implementation of Drone Specialization.
- Complete documentation, video, and dockerize our simulation.

Things that went well:
- We were able to finish the implementation of DataDashboard with enough time to demonstrate its importance. This was a key part of DataDashboard as we needed to show how this new extension could be used in a business setting.
- Documentation was completed on the new extensions as well as on previous code that had not been thoroughly documented.
- The video was able to be completed.
- We were able to dockerize our project.

Problems encountered:
- The drone specialization extension proved to be far more challenging to implement than was previously thought. 
- Dates that were set for code completion and implementation were missed, pushing back our game plan days and weeks.
- We had trouble maintaining sub variable such as toPackage when using wrapper functions. For example, toPackage was succesfully created in the getNextDelivery function and maintained in the wrapper update, but became null when entering the sub->update() function. Check-ins with team members and TA's left us still unable to solve this issue. The pushed code has this update function commented out so that the drones are able to move according to their original update function. However, the wrapper getNextDelivery functions are therefore not called and the drones go to packages in order of creation.
- Did not get to linking the front end user input to modify the package attributes, weight and type were therefore randomized.
- The container lags behind the drone even when the positions are set together. We were unable to find a fix for this issue after analyzing the setPosition function as well as json details including position, scale, and offset.

Items Completed:
- DataDashboard analysis and presentation
- Upload UML to github
- Updated DroneSpecialization UML
- Create header files for all drone specialization files
- Google code styling for all files
- Drone specialization design determined
- DroneSizeDecorator restructuring, base DroneDecorator class created 
- PackageFoodDecorator implementation
- Container implementaion in the json with a functional glb
- Creation of wrapped drone and package objects using factories
- Linking container objects to drone objects using containers LinkModel function
- Assigning drones to deliveries based on size and type
- Front end visual implementation

Changes to Increase Effectiveness:
- Increased communication earlier in the development process. This includes communicating with each other about how progress was going, as well as communicating with TAs and professors about getting help and clarification with project extensions.
- More frequent meetings. Instead of meeting once a week to document work and make sure we were staying on track, we should have been meeting at least 3 times a week. This would have helped alleviate the large end of sprint work that needed to be completed.
- Form a more thorough plan of the extension structure and requirements, as well as an in depth understanding of the code early on in the process, so as to minimize time consuming reworks later on.
