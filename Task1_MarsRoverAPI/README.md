MarsRoverApi
============
The objective is to TEST an API that follows the movement of a planet exploration vehicle (also called a Rover) and keeps track of its position and the obstacles that it may have encountered on a tour. 
- There is no graphical user interface.  
- You ONLY work in `MarsRoverTest.java` and write skeleton test cases based on the requirement.
- You are free to consult/use any online resources, including documentations, tutorials, and Q&A sites

**Project Template**  
You are provided with a project template that contains two skeleton classes: `MarsRover` and `MarsRoverException`, each each contains some fields and methods. DO NOT CHANGE the names, parameters and the return types of the existing methods.

**Mars Rover  API Task Description**  
Mars Rover API manages the movement of a planet exploration vehicle (i.e., a rover) around a planet. The planet is represented as grid with x and y coordinates. The rover starts the movement at position (0,0). The rover has also a direction that it is facing. The direction of the rover can be N (north), S (south), E (east) and W (west). The rover starts facing North. The input received by the rover is a string representing the sequence of commands it needs to execute.

The rover receives one string of commands. The commands are: "l" (left), "r" (right), "f" (forward) and "b" (backward). "l" and "r" change the rover’s direction counter- and clockwise, respectively, but not the position. "f" and "b" move the rover 1 position on the grid towards the direction it is facing or away from it, respectively. The facing does not change. Since the planet is a sphere, the grid wraps around the edges. When the rover moves over the edges of the planet, it spawns on the opposite edges.

The planet (grid) may contain obstacles in cells. Obstacles are defined as a list of coordinates "(obs1_x,obs1_y)(obs2_x,obs2_y)… (obsN_x,obsN_y)". When the rover finds an obstacle during a tour, it skips the current command (i.e., does not move to the cell where the obstacle is located) and continue executing the remaining commands.

Upon processing the string of commands, the rover returns its position and facing in the format "(pos_x,pos_y,facing)". If obstacles are found, the output will be "(pos_x,pos_y,facing)(obs1_x,obs1_y)(obs2_x,obs2_y)..(obsN_x,obsN_y)" The same obstacle shall be reported only once. Obstacles are reported in the order they are found.

**Examples:**   
![MarsRoverAPIexample](https://github.com/largehappygroup/HW4-G1/assets/89805831/103242b3-165d-4653-8111-eab55dea6165)

Example of an rover’s tour on a 3x3 planet in response to the command "ffrf". The starting position is (0,0) facing N(orth). After the 1st "f" (forward) command, the rover moves to position (0,1) facing North. Subsequent commands keep the rover moving. The expected output is (1,2,E). 
If there were two more "f" in the command, the rover would move over the right edge and spawn on the left edge to the final position (0,2,E).  (Figure on the left)

Example of a rover’s tour on a 3x3 planet in response to the command "ffrf", with one obstacle in position (0,2). After the 1st "f" (forward) command, the rover moves to position (0,1) facing North. The 2nd "f" command does not change the rover’s position, because there is an obstacle in (0,2). This second "f" command is thus skipped. The expected output is (1,1,E)(0,2). (Figure on the right)

Note that the API that you are implementing does not have a graphical user interface. These examples are given to help you visualize the moves of the planet rover. 

# Checklists

Use the following checklists to improve the quality of your test suite. 

## Test Case Checklist

### Each test case *should*:
- [ ] be executable (i.e., it has an **@Test** annotation and can be run via “Run as JUnit Test”)
- [ ] have at least one assert statement or assert an exception is thrown. Example assert statements include: **assertTrue**, **assertFalse**, and **assertEquals** ([click for tutorials](https://www.baeldung.com/junit-assertions)). For asserting an exception is thrown, use **assertThrows** in JUnit 5 ([click for tutorials](https://www.baeldung.com/junit-assert-exception)). 
- [ ]  evaluate/test only one method

### Each test case *could*:
- [ ] be descriptively named and commented
- [ ] If there is redundant setup code in multiple test cases, extract it into a common method (e.g., using **@BeforeEach**)
- [ ] If there are too many assert statements in a single test case (e.g., more than 5), you might split it up so each test evaluates one behavior.


## Test Suite Checklist

### The test suite *should*:
- [ ] have at least one test for each requirement
- [ ] appropriately use the setup and teardown code (e.g., **@BeforeEach**, which runs before each **@Test**)
- [ ] contain a fault-revealing test for each bug in the code (i.e., a test that fails)
- [ ] For each requirement, contain test cases for:
  - [ ] Valid inputs
  - [ ] Boundary cases
  - [ ] Invalid inputs
  - [ ] Expected exceptions
### To improve the test suite, you *could*:
- [ ] measure code coverage using an appropriate tool, such as EclEmma ([installation](https://www.eclemma.org/installation.html), [tutorial](https://www.eclipse.org/community/eclipse_newsletter/2015/august/article1.php)). Inspect uncovered code and write tests as appropriate.
