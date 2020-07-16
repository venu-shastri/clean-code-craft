# Clean Code
- Clean Code is not  a beautiful code and has no beauty reasons
- Professional programmers are not paid for writing beautiful or pretty
code
- Code is clean if it can be understood and maintained easily by any team member.
- Clean code is the basis for being fast
	- If your code is clean and test coverage is good, a change or a new
function just take a few hours or a couple of days – and not weeks or months
- Clean code is the foundation for sustainable software and keeps a software development project running over a long time without accumulating a large amount of technical debt
- Clean code is also a key to make a happier developer
	- It leads to a stress-free life
	- If code is clean and developer feeling comfortable with it,  keep calm in every situation, even in front of a tight project deadline.
- Clean code saves money (economic efficiency)
	- Each year, development organizations lose a lot of money because
their code is in bad shape

### Why Code should be Bug Free 
- **`There is no life today without software!`**
- Board an elevator, we give our lives are in the hands of software.
-  Aircrafts are controlled by software, and the entire, worldwide air traffic control system depends on software.
-  Modern cars contain a significant amount of small computer systems with software that communicate over a network, responsible for many safety-critical functions of the vehicle. Air conditioning, automatic doors.
-  medical devices, trains, automated production lines in factories 
-  Digital Revolution and the Internet of Things (IoT), the relevance of
software for our life will again increase significantly.
- The autonomous (driverless) car.

Bug in above software-intense systems can have catastrophic consequences
Quality is under no circumstances negotiable in these kinds of systems - **Never!**

## Different levels of quality assurance measures in software development projects
These levels are often visualized in the form of a pyramid – the so-called **`Test Pyramid`**

![testpyramid](https://github.com/venu-shastri/clean-code-craft/blob/master/images/testpyramid.PNG)

>Experience has shown that the total costs regarding implementation and maintenance of tests are increasing toward the top of the pyramid.
> Large system tests and manual user acceptance tests are usually complex, often require extensive organization, and cannot be automated easily.
> large system tests, or UI-driven tests, are totally improper to check all possible paths of execution through the whole system . 
> if a test on a system level fails, the exact cause of the error can be difficult to locate

Unfortunately, in several software development projects we will  find **`degenerated Test Pyramids`**
- **Ice Cream Cone Anti-Pattern** - Enormous effort is put into the tests on the higher level, whereas the elementary unit tests are neglected .
- **Cup Cake Anti-Pattern** - In the extreme case elementary unit tests are completely missing
- 
![enter image description here](https://github.com/venu-shastri/clean-code-craft/blob/master/images/DegeneratedTestAntipatterns.PNG)

### How to  ensure High Quality of a Software System
>A broad base of **`inexpensive, well-crafted, very fast, regularly maintained, and fully automated unit tests, supported by a selection of useful component tests`**.

## Unit Test
**`refactoring” without tests isn’t refactoring, it is just moving shit around`**.
—Corey Haines (@coreyhaines), December 20, 2013, on Twitter

### How to write unit  testable  Code ?
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTk2NTgwMjEyLDIxMDI0MTI4MjAsNTc3OD
IzNzA1LC05NDc5MjA1NDgsLTE1MTc0NzA2NjNdfQ==
-->