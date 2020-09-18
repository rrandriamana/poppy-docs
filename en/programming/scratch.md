# Programming Poppy robots using Scratch

<!-- toc -->

Scratch is a blocks-based graphical programming language that allows users to create interactive animations, games, and more, while learning about mathematical and computational ideas.

Scratch could be used by both novice and more advanced users.

Scratch is open-source and it is entirely written in javascript, you can use it from the [official website](https://scratch.mit.edu/projects/editor/) but you can also use a [copy of the website](https://github.com/LLK/scratch-gui/wiki/Getting-Started) in your personal computer. It is a way more difficult but also possible by following the instructions.


## Introduction to Scratch programming

This chapter will focus on things necessary to understand in Scratch for using Poppy creatures.


### Connect your robot to Scratch

#### If you have a tangible robot

First, you must be connected to the same network LAN area than your robot (e.g. on the same router or Wifi).

You have to go on the web homepage of your robot with its URL. You can use its IP address (for example http://192.168.1.42) if you have a way to know it or its hostname like http://poppy.local. To find its IP address look at [the zeroconf chapter](../installation/install-zeroconf.md#alternatives-to-find-the-ip-address-of-a-computer-on-your-local-network). To use directly its hostname http://poppy.local you must have a Zeroconf software installed on your computer (aka ["Bonjour print services for Windows"](https://support.apple.com/kb/DL999?locale=en_US) if you are running Windows).

The home page of your poppy creature should look like the snapshot below:

![find blocks](../img/scratch/homepage.png)

Click on the "Programming" button then "Scratch" link to open the Scratch interface.


### Interface and general ideas

It is possible to change the language with the sphere button, on the right of the logo Scratch 

### Saving & importing project in Scratch

![Save click](../img/scratch/scratch_save.png)

As this Scratch is a Virtual Machine, you can save and import your project only on your computer. 

> **Warning** It is not possible to share your project on the cloud as unofficial extension are still not yet supported on Scratch 3.0.

### Launch Poppy blocks

Poppy special blocks are stored in the Extension "Poppy". Push the Add Extension blue button at the lower left corner. 

![add extension](../img/scratch/add_extension.png)

Click on "Poppy" and all the blocks should appear in the Poppy category.

![poppy extension](../img/scratch/poppy_extension.png)

![poppy category](../img/scratch/poppy_category.png)

#### Network

First connect Scratch to your robot with the "set host" block. The host variable must be the IP or the hostname+".local" of your robot. Then test your connection with the (tangible or simulated) robot with the "test connection" block.

![connection](../img/scratch/connection.png).

if the block answer is "You may have connection troubles", your "host" variable inside the Scratch project is probably wrong. 


### Build your own blocks!

It is now possible to create your own block by a combinaison of many blocks in Scratch 3.0. There is a My Blocks category to make a block.

![create block](../img/scratch/create_block.png)

You can choose three different options for your block : 
- Add an argument : it could be a number, a string or a Reporter block as 
![reporter](../img/scratch/reporter.png)
- Add an boolean argument
- Add text or labels


![button option](../img/scratch/button_option.png)

For exemple if you want to create a block which plays a move and swicth on some LEDs of some motors, you can do it as it is shown below. 
![own button](../img/scratch/own_button.png)

> **Info** If you use a reporter block from the poppy extension in a command block 
![command](../img/scratch/command.png)
 outside the poppy category block, you will have to use the "transform to string" button 
 ![string button](../img/scratch/scratch_blocks/transform_string.png) 
 as you can see above.

## Description of Poppy blocks
|                                                            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ![](../img/scratch/scratch_blocks/set_host.png)                  | This block allows you to connect Scratch to your robot. The host input can accept : - robot_name.local (e.g. : poppy.local if your robot’s name is poppy)- the IP address (e.g. 169.254.145.25)                                                                                                                                                                                                                                                                                   |
| ![](../img/scratch/scratch_blocks/test_connection.png)           | Click on this block to verify that you are connected to your robot.                                                                                                                                                                                                                                                                                                                                                                                                              |
| ![](../img/scratch/scratch_blocks/set_motors_compliant.png)      | Put one or many motors in compliant or stiff mode. Motors are hand-drivable in compliant mode but must be in stiff mode to controlled with Scratch. The “motor(s)” input can accept:- string of a motor name (e.g. m1) - string of many motors separated with spaces (e.g. m1 m2 m4)- a Scratch list of motors like the reporter block "all motors" or the block “list”                                                                                                       |
| ![](../img/scratch/scratch_blocks/set_position.png)              | Put one or many motors in a position (angle in degree) in a given time. The “motor(s)” input can accept: - string of a motor name (e.g. m1) - string of many motors separated with spaces (e.g. m1 m2 m4) - a Scratch list of motors like the reporter block "all motors" or the block “list”.  “Wait” can be true or false. If it’s on True, the action will wait the end of the previous action. If it’s on False, then the action will proceed during the previous one. |
| ![](../img/scratch/scratch_blocks/reset.png)                     | Restart the software inside the robot.                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ![](../img/scratch/scratch_blocks/set_register_of_motor.png)     | Put the value to one register (position, speed, max torque, …) of one or many motors.                                                                                                                                                                                                                                                                                                                                                                                            |
| ![](../img/scratch/scratch_blocks/set_led.png)                   | Activate/deactivate color leds of motors and choose the color of your choice.The “motor(s)” input can accept: - string of a motor name (e.g. m1) - string of many motors separated with spaces (e.g. m1 m2 m4) - a Scratch list of motors like the reporter block "all motors"" or the block “list”                                                                                                                                                                         |
| ![](../img/scratch/scratch_blocks/play_move_reporter.png)        | Play a movement at a given speed. It is necessary to indicate the exact name of the movement previously recorded. This block can be nested in the “concurrent/sequential” block.                                                                                                                                                                                                                                                                                                |
| ![](../img/scratch/scratch_blocks/play_move_in_reverse_reporter.png)      | Play a move in reverse at a given speed  (reporter block)
| ![](../img/scratch/scratch_blocks/sequence.png)                  | All blocks in input are run one after each other. You can use this block to play concurrently many sequently move.                                                                                                                                                                                                                                                                                                                                                                |
| ![](../img/scratch/scratch_blocks/concurrent.png)                | All reports input are run simultaneously. You can use this block to play concurrently many recorded move.                                                                                                                                                                                                                                                                                                                                                                         |
| ![](../img/scratch/scratch_blocks/create_and_start_record.png)   | Create and start a movement recorded by demonstration to the given motors.                                                                                                                                                                                                                                                                                                                                                                                                       |
| ![](../img/scratch/scratch_blocks/stop_record_and_save_move.png) | Stop a record and save the recorded move in the robot. Be careful, you must have previously defined a move record with the "create & start record move ..." block.                                                                                                                                                                                                                                                                                                               |
| ![](../img/scratch/scratch_blocks/stop_move.png)                 | Stop a movement that is being played.                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ![](../img/scratch/scratch_blocks/play_concurently_moves.png)    | Play movements at the same time (can be nested to concurrent block). Inputs can be : - move name (string) - any reporter block, like sequential or play sequentially                                                                                                                                                                                                                                                                       |
| ![](../img/scratch/scratch_blocks/play_sequentially_moves.png)   | Play movements following in order (can be nested to sequential block). Inputs can be :  - move name (string) - any reporter block, like sequential or play sequentially                                                                                                                                                                                                                                                                                                          |
| ![](../img/scratch/scratch_blocks/start_behaviours.png)          | Start/Stop/Pause/Resume an integrated behaviour of the robot. It can be a position, a movement, a sensorimotor loop, high level camera feature..                                                                                                                                                                                                                                                                                                                                 |
| ![](../img/scratch/scratch_blocks/play_move_in_reverse_command.png)      | Play a move in reverse at a given speed  (command block)                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ![](../img/scratch/scratch_blocks/play_move_command.png)         | Play a move at a given speed (command block)                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ![](../img/scratch/scratch_blocks/motors_in_group.png)           | Give motors which are in a given group. You can know groups name with the block “all motors groups”.                                                                                                                                                                                                                                                                                                                                                                             |
| ![](../img/scratch/scratch_blocks/all_motors.png)                | Return a list with the name of every motors in the robot.                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ![](../img/scratch/scratch_blocks/get_register.png)              | Give the value of a register (position, speed, load, ... ) of one or many motors.                                                                                                                                                                                                                                                                                                                                                                                                |
| ![](../img/scratch/scratch_blocks/get_all_motors_position.png)   | Give the position of every motors. It is a shortcut to the block above. It is useful to make a snapshot of pose of the robot.                                                                                                                                                                                                                                                                                                                                                    |
| ![](../img/scratch/scratch_blocks/index_of_motor.png)            | Return the index of a motor name in the "all motors" block list.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ![](../img/scratch/scratch_blocks/robot_URL.png)                 | Give the URL of the robot. For internal use only.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ![](../img/scratch/scratch_blocks/all_recorded_moves.png)        | Give all records stored in this robot.                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ![](../img/scratch/scratch_blocks/get_all_behaviours.png)        | Give the list of all attached/running behaviours .                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ![](../img/scratch/scratch_blocks/get_all_motors_group.png)                          | Give all existing motors groups.                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ![](../img/scratch/scratch_blocks/get_function_of_behaviour.png) | Get all methods or functions which are runnable in a behavior. It is an advanced block.                                                                                                                                                                                                                                                                                                                                                                                           |
| ![](../img/scratch/scratch_blocks/card_is_detected.png)          | Return a boolean (true/false) depending if the selected card is detected by the camera of the robot.                                                                                                                                                                                                                                                                                                                                                                             |
| ![](../img/scratch/scratch_blocks/popup.png)          | Display a popup with the chosen message.                                                                                                                                                                                                                                                                                                                                                                             |
| ![](../img/scratch/scratch_blocks/transform_string.png)          | Transform the output of Poppy reporter block into string to be used with other basic Scratch command block as parameter.                                                                                                                                                                                                                                                                                                                                                                             |
| ![](../img/scratch/scratch_blocks/call_api.png)          | Call the REST API.                                                                                                                                                                                                                                                                                                                                                                             |
| ![](../img/scratch/scratch_blocks/remove_move.png)          | Remove one or several recorded moves.                                                                                                                                                                                                                                                                                                                                                                             |
| ![](../img/scratch/scratch_blocks/get_sitemap.png)          | Get the sitemap. Use the URL of the robot as parameter.                                                                                                                                                                                                                                                                                                                                                                             |




## Quick examples

You can find some exemples and activities on the web site [poppy education](https://www.poppy-education.org/activites/initiation-ergo-jr-et-scratch/) to record a movement by demonstration and play it back or how to use loops.







