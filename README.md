# Preview 
This is my understanding and explanation of a genral Scratch project and a try to give my solution on the interested project, "Development of an interactive flow visualization tool for visual / blockly programming"
***
# Understanding a Scratch project via its JSON strucutre

Via a dummy Scratch project, [Scratch Porject](https://scratch.mit.edu/projects/814990872/editor), the following observations were made by me:
* Every Scratch project has a list "targets" which has its elements as ``` Stage```, ```Sprite1``` and so.
  * Meaning every observable and interactable entity of a project is a seperate element in the list "targets".
<p></p>

* Each element of list ```"targets"``` is a nested dictionary (i.e. key-value pairs). 
<p></p>

* Each dictionary ( the "parent" one) has major 5 key-value pairs :
  * variables
  *  lists
  *  broadcasts
  *  blocks
  *  comments
<p></p>

* "blocks" is the nested key-value data type which actually defines code and control the flow.
<p></p>

* Every elemet of "blocks" has numerous keys like :
    * opcode
    * next
    * parent
    * shadow
    * topLevel
    * x
    * y
<p></p>

* The "opcode" gives a description of the function (for e.g. : "event_whenflagclicked", "control_repeat", "operator_random", etc.)
<p></p>

* "next" key controls the flow i.e. the value of "next" is actually another "blocks" key which in turn lead to a function block.
<p></p>

* Some function "blocks" are lists which has elements like MESSAGE, SUBSTACK, TIMES etc., which are elementary instructions.
***
#Solution
After discussing the various compenents of a Scratch JSON file, i am laying a skeletal structure on how i would tackle the problem and provide the desrired output:
<p></p>

* Parse the JSON file and create an empty dictionary and append the "blocks" keys with their values; fo every "Sprite" there is in the project.
 <p></p>

* Now in the currated dictionary we again run a loop and make a nested dictionary in which for every "block" , the key-value pairs (like "opcade", "next", "parent") and append another nested dictionary for the values that the above key-value pairs could possess.
<p></p>

* Now that we have all the data from the target project, using a suitable tool (that forms and vizualizes the relations from a dictionary/list).
<p></p>

* According to me, we just require to lay relations between different keys depends upon certain parameters like "next", "opcode", "SUBSTACKS", etc.
***
# Workflow

<img src = "https://github.com/deathzombie/Explanation-/blob/main/Untitled.excalidraw.png">

