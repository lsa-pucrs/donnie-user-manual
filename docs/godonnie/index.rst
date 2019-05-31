.. _godonnie:

===============
Donnie Programming Environment 
===============

Introduction
-------------
GoDonnie is a programming language that commands a robot called Donnie. This robot works in its own environment.
To open this environment it’s necessary to take a few steps. Open a Linux terminal and type ``donnie_player`` and press ``ENTER``.
After that, in order to start the module of GoDonnie’s commands type ``GoDonnie -t``. These expressions can be typed in capital letter or lower case.
Now, in the line of command, the user types the commands he wants. It’s possible to type one command per line or several commands in the same line.
After each line, the user should press ``ENTER``. For the robot to execute the commands, it’s necessary to press ``ESC``.
This way, the user can type a command and press ``ENTER`` and ``ESC``, or he can type one command per line, pressing ``ENTER`` to change lines, and only pressing ``ESC`` when he wants to run the commands. 
The GoDonnie language doesn’t difference capital letters to lower cases, and the commands can be typed with or without accentuation.
The robot always starts at the point 0,0 facing north. This position is located on the left bottom.
The commands in this manual are all in Portuguese.



GoDonnie Programming Language
-------------

************************************
GoDonnie User manual
************************************

Section 1: Leaving the programming terminal
############################################

Command:
    ``QUIT``
    ``EXIT``

Subject-matter:
    None

Explanation:
    It closes the programming environment. It can only be used in the terminal.

**Example:**
    
::
    
    QUIT


Section 2: Declaration of variables
###################################
*Variable is an object that holds value. This variable can only receive integer values*

Command:
    ``VAR x``
Subject-matter:
    ``x`` is the variable that is going to be created. This variable receives integer values.
Explanation:
    There are 5 forms to create a variable:

    1. Create a variable;
    2. Create a variable and assign an initial value;
    3. Create a variable that receives an expression;
    4. Create a variable inside the command of repeat ``FOR``;
    5. Create a variable that will receive a value from another command, such as: ``COLOR`` and ``POS``.

    Variables hold only the last received values. They store only integer values. This way, if there is a comma result, only the integer part will be stored in the variable.

    There are rules for the name of the variables:

    - There are no difference between capital letter and lower case;
    - It can’t contain special characters. Exemple: *, @, #, +;
    - It can’t initiate with a number. Exemple: VAR 52abc is wrong.


**Example:**

    1. To create a variable without initial value, it’s possible to do:

    ::

        VAR A

    Creates a variable called A.

    ::

        A = 2

    When a variable is created it’s possible to assign directly a value. The variable called ``A`` will store the value 2.

    2. To create a variable with initial value, it’s possible to do:

    ::

        VAR B = 5

    Creates a variable called ``B`` and stores the value 5.

    3. To create a variable that receives an expression, it’s possible to do:

    ::

        VAR C = A + B

    Creates a variable called ``C`` that receives the value of the variable ``A`` added to the value of the variable ``B``. The result of variable ``C`` is 7.

    ::

        C = 1

    Changes the value of the variable ``C`` and stores the value 1, losing its previous value.

    4. To create a variable inside the command ``FOR`` (this command will be seen in section 10 of the manual), it’s possible to do:
        
    ::

        FOR VAR d = 0; d > 5; d = d +1 DO
        FW 1
        END FOR

    The robot will take 5 steps forward.

    5. To create a variable that receives value from another command, it’s possible to do:

    ::

        VAR d = DISTANCE F
        VAR c = COLOR GREEN
        VAR px = POS x

    The variable ``d`` is going to store the front distance from the robot to the object. The variable ``c`` is going to store the number of green objects. And the variable ``px`` is going to store the current position of the robot in the x axis. (The commands ``distance``, ``color`` and ``pos`` will be seen in section 10 of the manual).

    ::

        G = 5

    It will return an error because the variable ``G`` was not created.

Section 3: Audio Commands
##########################
*Commands for manipulation and return of audio*


| **a)**
Command:
    ``SPEAK x``

Subject-matter:
    ``x`` is a variable that must have been created previously.

Explanation:
    It speaks the content of the variable. This sound is issued by the robot or the virtual environment, it depends on which one is active.

**Example:**

    ::

        VAR x = 5
        SPEAK x

    Will be spoken: 5

| **b)**
Command:
    ``SPEAK “x”``

Subject-matter:
    ``x`` is a word or a phrase, that needs to be between quotation marks

Explanation:
    It speaks the word or phrase between quotation marks. This sound is issued by the robot or the virtual environment, it depends on which one is active.

**Example:**

    ::

        SPEAK “hello”

    Will be spoken: hello

| **c)**
Command:
    ``SOUND on``
    ``SOUND off``

Subject-matter:
    It turns the sound on or off

Explanation:
    These commands turn on and off the audio from the robot or the virtual environment.

**Example:**

    ::

        SOUND ON
        SOUND OFF


Section 4: Operators
######################
*They are operators that provide support for logical and mathematical expressions*

Command:
    Operators

Subject-matter:
    | *Mathematical:*
    | ``+ addition``
    | ``- subtraction``
    | ``* multiplication``
    | ``/ division``

    | *Comparators:*
    | ``<> different``
    | ``== equals``
    | ``< is less than``
    | ``> is more than``
    | ``<= is less or equals than``
    | ``>= is more or equals than``

    | *Assignment:*
    | ``= assignment``

Explanation:
    Operators are used to compare values or expressions.

**Example:**
    *To add*

    ::

        Var a = 2

    Creating the variable ``a`` and storing the value 2

    ::

        Var b = 1

    Creating the variable ``b`` and storing the value 1

    ::

        Var add

    Creating the variable ``add``

    ::

        add = a + b

    Storing in ``add`` the sum from variables ``a`` and ``b``

    ::

        Speak add

    Will be spoken: 3

    *To divide*

    ::

        Var c = 2

    Creating the variable ``c`` and storing the value 2

    ::

        Var d = 2

    Creating the variable ``d`` and storing the value 2

    ::

        Var division

    Creating the variable ``division``

    ::
    
        division = c / d

    Storing in ``division`` the division from variables ``c`` and ``d``

    ::

        Speak division

    Will be spoken: 1


Section 5: Movement Commands
##############################
*They are commands that move the robot in the environment*

| **a)**
Command:
    ``FW n``
    ``FORWARD n``

Subject-matter:
    ``n`` is the number of steps. This command accepts only integer and positive numbers, or variables that store integer numbers, or mathematical expressions that result in integer numbers.

Explanation:
    It walks ``n`` steps forward

**Example:** 

    ::

        FW 5

    The robot will walk 5 steps forward

    ::
        
        VAR A = 10
        FW A

    The robot will walk 10 steps forward

    ::

        VAR A = 10
        VAR B = 20
        FW A + B

    The robot will walk 30 steps forward

    If the robot hits into something before it walks the number of steps, you will be informed: ``“I walked only X steps forward. I found an obstacle.”``

    ::

        FW -5

    When a negative number is typed as a command, the user will be informed that the robot walked 0 steps.

| **b)**
Command:
    ``BW n``
    ``BACKWARD n``

Subject-matter:
    ``n`` is the number of steps. This command accepts only integer and positive numbers, or variables that store integer numbers, or mathematical expressions that result in integer numbers.

Explanation:
    It walks ``n`` steps backward.

**Example:**

    ::

        BW 5

    The robot will walk 5 steps backward

    ::
    
        VAR A = 10
        BW A

    The robot will walk 10 steps backward

    ::

        VAR A = 10
        VAR B = 20
        BW A + B

    The robot will walk 30 steps backward

    If the robot hits into something before it walks the number of steps, you will be informed: ``“I walked only X steps backward. I found an obstacle.”``

    ::

        BW -5

    When a negative number is typed as a command, the user will be informed that the robot walked 0 steps.





Section 6: Rotation Commands
###############################
*The robot rotates without movement*

| **a)**
Command:
    ``TR n``
    ``RIGHT TURN n``

Subject-matter:
    ``n`` is the number of degrees. This command accepts only integer and positive numbers, or variables that store integer numbers, or mathematical expressions that result in integer numbers.

Explanation:
    Turns ``n`` degrees to the right. The robot does no displacement.

**Example:**

    ::

        TR 90

    The robot will turn 90 degrees to the right.

    ::

        VAR A = 45
        TR A

    The robot will turn 45 degrees to the right.

    ::

        VAR A = 80
        VAR B = 10
        TR A + B

    The robot will turn 90 degrees to the right.

    ::

        TR - 90

    The robot will turn 90 degrees to the left.


| **b)**
Command:
    ``TL n``
    ``LEFT TURN n``

Subject-matter:
    ``n`` is the number of degrees. This command accepts only integer and positive numbers, or variables that store integer numbers, or mathematical expressions that result in integer numbers.

Explanation:
    Turns ``n`` degrees to the left. The robot does no displacement.

**Example:**

    ::

        TL 90

    The robot will turn 90 degrees to the left.

    ::

        VAR A = 45
        TL A

    The robot will turn 45 degrees to the left.

    ::

        VAR A = 80
        VAR B = 10
        TL A + B

    The robot will turn 90 degrees to the left.

    ::

        TL - 90

    The robot will turn 90 degrees to the right.


Section 7: Commands of Visualization of the Environment
#########################################################
*These are commands to get informations about the environment in which the robot is inserted. It’s not possible to store in variables the return from these commands*

| **a)**
Command:
    ``SCAN``

Subject-matter:
    None

Explanation:
    It returns the identification of the object, the approximate angle and the approximate distance between the robot and the identified object. The tracking for the identification of objects occurs from 90 degrees to the left to 90 degrees to the right from the front.

Example:               
    Let’s assume that the robot is in the position 2,3, facing north, and there’s a green obstacle in the position 0,5 and other red obstacle in the position 6,3.

    ::

        SCAN

    It will be spoken:

    ``To the 40 degrees in the left: 1 object of color green at 2 steps.`` ``To the 90 degrees in the right: 1 object of color red at 4 steps.``

    In case two objects are in the same degree, it will inform: ``To the 30 degrees in the left: 2 objects of color green, red at 17 steps.``


| **b)**
Command:
    ``STATE``

Subject-matter:
    None

Explanation:
    It returns the position in the X, Y axis and the angle from the robot. It also informs the last rotation or movement command that was typed before the command ESTADO.

**Example:**

    ::

        FW 3 STATE
    
    Let’s say the robot was at 0,0. The robot will walk 3 steps forward and it will inform: 
    ``“I walked 3 steps forward, command 1 was PF 3, walked 3, didn’t crash, position [3,0,0].”`` The number 3 corresponds to the X axis, the first 0 corresponds to the Y axis and the last 0 corresponds to the angle of the robot.

    In case the robot crashes into something and only completes 2 steps successfully, the command will return:
    ``”I walked 3 steps forward, command 1 was PF 3, walked 2, crashed, position [2,0,0].”``

    If there weren’t previous commands, it will return:
    ``“No command executed, position [0,0,0]".``


Section 8: Commands of Position and Perception of the Environment
################################################################
*These are commands to get informations about the environment in which the robot is inserted. It is possible to store in variables the return from these commands*

| **a)**
Command:
    ``DISTANCE d``

Subject-matter:
    ``d`` is the direction of the robot sensor (``f`` - front; ``fr`` - frontal right; ``fl`` - frontal right; ``b`` - back; ``bl`` - back left; ``br`` - back right).

Explanation:
    It returns the quantity of steps from the robot sensor to an obstacle, depending on the chosen direction.               

    There are three ways to use the DISTANCE command:

    1. If the user wants to have a feedback, he should use the command ``SPEAK`` with the command ``DISTANCE``.
    2. If the user wants only to store in a variable.
    3. If the user wants to use it directly in another command, for example: ``IF`` (section 9), ``FOR`` (section 10), ``REPEAT`` (section 10) or ``WHILE`` (section 10).

    - DISTANCE F returns the number of steps from the robot to an object detected by the front sensor of the robot.
    - DISTANCE FR returns the number of steps from the robot to an object detected by the frontal right sensor of the robot.
    - DISTANCE FL returns the number of steps from the robot to an object detected by the frontal left sensor of the robot.
    - DISTANCE B returns the number of steps from the robot to an object detected by the back sensor of the robot.
    - DISTANCE BR returns the number of steps from the robot to an object detected by the right rear sensor of the robot.
    - DISTANCE BL returns the number of steps from the robot to an object detected by the left rear sensor of the robot.
                    
    If there aren’t obstacles, it returns the quantity of step that the sensor can identify, that usually is 60 steps.


**Example:**

    ::

        DISTANCE F
        DISTANCE FR
        DISTANCE FL
        DISTANCE B
        DISTANCE BL
        DISTANCE BR

    Assuming that the robot is in the position 0,0, facing north and there are obstacles in the following positions, the result will be:

    Obstacle in 0,3:

    ::

        SPEAK DISTANCE F

    Answer: 3 Steps

                    
    You can previously create a variable, and after use it to store what the command DISTANCE will return:

    ::

        VAR d = DISTANCE T

    It stores in the variable ``d`` the back distance from the robot to the obstacle that is directly behind it. Assuming that the robot is in the position 0,3 facing north and there is an obstacle in 0,0. The stored value in ``d`` will be 3.

    ::

        IF DISTANCE F>3 THEN
        FW 1
        ELSE
        SPEAK “It’s impossible to move forward”
        END IF

    In the example above, if the front distance from the robot is more than 3, the robot will move 1 step forward. If the distance is equal or less than 3, it will return: ``“It’s impossible to move forward”``

    ::

        WHILE DISTANCE F>3
        DO
        FW 1
        END WHILE

    In the example above, while the front distance from the robot to the object is more than 3, it will move 1 step forward.

| **b)**
Command:
    ``POS k``
    ``POSITION k``

Subject-matter:
    ``k`` is an axis of the Cartesian plane (X or Y) or angle (A).

Explanation:
    It returns the current position of the robot in the X axis or Y axis or the current angle of the robot.

    There are three ways to use the POS k command:

    1. If the user wants to have feedback, he should also use the command ``SPEAK`` altogether with the command ``POS x``, ``POS y`` or ``POS a``;
    2. If the user wants only to store it in a variable;
    3. If the user wants to use it directly in another command, for example: ``IF`` (section 9), ``FOR`` (section 10), ``REPEAT`` (section 10) or ``WHILE`` (section 10).

Example:
    If the user wants to have a feedback, he can do as it follows:

    Assuming the robot is in the position 0,0 facing north:

    ::

        SPEAK POS x

    It will be spoken 0

    ::

        SPEAK POS y

    It will be spoken 0

    ::

        SPEAK POS a

    It will be spoken 0

    If the user only wants to store the position value:

    ::

        VAR z = POS x

    The variable ``z`` has stored the value of the position of the robot in the x axis

    ::

        VAR b = POS y

    The variable ``b`` has stored the value of the position of the robot in the y axis

    ::

        VAR i = POS a 

    The variable ``i`` contains the angle of the robot

    If the user wants to use it inside other commands:

    ::

        IF POS b > 0 THEN
        FW 5
        ELSE
        BW 5
        END IF


| **c)**
Command:
    ``COLOR c``

Subject-matter:
    ``c`` is the color you want (blue, red, green)

Explanation:
    Verifies how many objects of a certain color the robot can identify at an angle of 180 degrees ahead of it.

    There are three ways to use the COR c command:

    1. If the user wants to have a feedback, he should use the command ``SPEAK`` with the command ``COLOR``.
    2. If the user wants only to store in a variable.
    3. If the user wants to use it directly in another command, for example: ``IF`` (section 9), ``FOR`` (section 10), ``REPEAT`` (section 10) or ``WHILE`` (section 10).

**Example:**
    
    If the user wants to have a feedback, he can do as it follows:

    Assuming there is one green object and two blue objects:

    ::
                       
        SPEAK COLOR blue

    It will be spoken 2

    ::

        SPEAK COLOR green

    It will be spoken 1

    If the user only wants to store the color value:

    ::
                        
        VAR A = COLOR BLUE

    The variable ``A`` stores the number of blue objects.

    ::

        VAR V = COLOR GREEN

    The variable ``V`` stores the number of green objects.

    If the user wants to use it inside other commands:

    ::
                        
        IF COLOR BLUE > 0 THEN   
        SPEAK “Number of blue objects”
        SPEAK COLOR BLUE
        ELSE
        SPEAK "Couldn’t find blue objects"
        END IF

        IF COLOR GREEN > 0 THEN
        SPEAK “Number of green objects”
        SPEAK COLOR GREEN
        ELSE
        SPEAK "Couldn’t find green objects"
        END IF


Section 9: Condition Commands
###############################
*These are conditional commands that allow the program to choose what will be executed, according to the stipulated condition*

| **a)**
Command: 
    | ``IF`` *expression logical operator expression*
    | ``THEN`` *commands*
    | ``ELSE`` *commands*
    | ``END IF``

Subject-matter:
    Expression = variable or expression

Explanation:
    Test if a condition is true and, if it is,executes the first line of commands, else executes the ELSE line of commands.

Example:
    Assuming that, if the variable is less than 4 the robot has to walk 5 steps forward, else it has to turn 45 degrees to the left:

    ::
                   
        VAR a = 0
        IF a<4
        THEN FW 5
        ELSE TL 45
        END IF


| **b)**
Command:               
    | ``IF`` *expression logical operator expression*
    | ``THEN`` *commands*
    | ``END IF``

Subject-matter:
    Expression = variable or expression

Explanation:
    Test if a condition is true and, if it is, executes the first line of commands.

**Example:**

    ::
                       
        VAR a = 0
        IF a<4
        THEN FW 5
        END IF

    If the variable ``a`` has a value less than 4 the robot will walk 5 steps forward

    
Section 10: Repeat commands
############################
*These are commands that allow one or more instructions to be executed a certain number of times*

| **a)**
Command: 
    | ``FOR`` *initialization; expression logical operator expression; increment or decrement*
    | ``DO`` *commands*
    | ``END FOR``

Subject-matter:
    | Initialization: variable = an integer value

    Variable or expression logical operator variable or expression: variable or expression - logical operator - variable or expression.

    | Increment: variable + constant or variable + variable
    | Decrement: variable - constant or variable - variable

Explanation:
    Repeats the commands a certain number of times

Example:
    The example makes the robot to walk towards an obstacle that’s in front of him and after each step he says “hello”.

    ::

        VAR obstacle = DISTANCE F
        FOR VAR x=1; x<=obstacle; x=x+1     
        DO
        FW 1
        SPEAK “hello”
        END FOR

The variable ``x`` will start with 1 as value, the robot will walk one step forward and will say “hello” while the value is less or equal the distance to the obstacle.


| **b)**
Command: 
    | ``REPEAT n TIMES`` commands
    | ``END REPEAT``

Subject-matter:
    ``n`` is the number of times that the commands will be repeated

Explanation:
    Repeats the commands ``n`` times

Example:

    ::

        REPEAT 4 TIMES
        TR 90
        FW 2
        END REPEAT
    
    Assuming the robot will start at the position 0,0 , the commands TR 90 and FW 2 will be repeated 4 times. The robot’s trajectory will look like a square.


| **c)**
Command:
    | ``WHILE`` *expression logical operator expression*
    | ``DO`` *commands*
    | ``END WHILE``

Subject-matter:
    Variable or expression logical operator variable or expression: variable or expression - logical operator - variable or expression.

Explanation:
    Repeats the commands while expression - logical operator - expression is true.

Example:
    This example makes the robot walk towards an obstacle in front of him and after each step speak "I'm coming".

    :: 

        WHILE DISTANCE > 3
        DO
        FW 1
        SPEAK "I'm coming"
        END WHILE

    While the distance ftom the front of the robot in relation to the object is more than 3, the robot will walk one step forward and will speak "I'm coming".


Section 11: Declaration of procedures
######################################
*Procedure is a smaller program(subprogram) that allows decompose and solve a more complex problem in a simpler. It can be called in other parts of the program*

| **a)**
Command:
    | ``PROCEDURE`` *name: variable1, variable2, variable3*, ...
    | ``DO`` *commands*
    | ``END PROCEDURE``

Subject-matter:
    Name is the name of the subprogram and variable1, variable2, variable3 are its arguments

Explanation:
    It creates a subprogram. This command only works via file.

Example:
    The robot needs to walk simulating a rectangle. This rectangle can have different sizes, according to the activity. Therefore the command PROCEDURE can be used to create a procedure called RECTANGLE that receives two variables, one for the height and the other for the base. Thus this procedure can be used to make rectangles with different sizes.

    ::

        PROCEDURE RECTANGLE: base, height
        DO
        FW base TR 90
        FW height TR 90
        FW base TR 90
        FW height TR 90
        END PROCEDURE

    Or

    ::

        PROCEDURE RECTANGLE: base, height
        DO
        REPEAT 2 TIMES
        FW base TR 90
        FW height TR 90
        END REPEAT
        END PROCEDURE

    Calling the subprogram

    ::

        RECTANGLE [5,3]
        RECTANGLE [8,4]
        RECTANGLE [9,5]


Section 12: Various Commands
#############################


| **a)**
Command:
    | ``WAIT t``

Subject-matter:
    ``t`` is the time in seconds

Explanation:
    Waits ``t`` seconds to run the next commands

Example:
    If the robot needs to walk forward 2 steps, wait 3 seconds and then walk 4 more steps

    ::

        FW 2
        WAIT 3
        FW 4

| **b)**
Command:
    - --

Subject-matter:
    None

Explanation:
    After this symbol ``--`` everything that is in the line that has ``--`` won't be executed. These are reminders about the code.

**Example:**
    ::

        -- This is a comment


Section 13: Vibrating Belt
##########################

**a)**
Command:
    | ``BELT on``
    | ``BELT off``

Subject-matter:
    It turns the belt on or off

Explanation:
    These commands turn the belt on or off

**Example:**
    ::

        BELT ON
        BELT OFF


GoDonnie Interpreter
-------------

modos de operacao, exemplos de uso


