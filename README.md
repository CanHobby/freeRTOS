# freeRTOS for CH32V RISC-V
freeRTOS on RISC-V MCU CH32Vxxx

setting up freeRTOS on MRS could not be easier...  They have the template already made up.

1). Create a directory on you computer to use as a workspace.

2). Open MRS specifying this directory as the workspace. - Hit the "Launch" button.

2a). (optional) I like to set up the dark theme by clicking on Window -> Preferences -> General -> Appearance
	  and selecting Theme = "Dark"  as well as  Color and Font themes = "Classic Theme".  Apply and close.
	  
3).  Click on "Create new MounRiver project".   Do the following steps in the order indicated (important)

4).  unClick the "ARM Core" box

5).  Select "FreeRTOS" in the Template Type drop down.

6).  Select MCU Family eg. CH32V203 [RISC-V]  --  Note: the -003 Chip does not offer sufficient memory to do very much with freeRTOS and is not listed.

7).  There should only be 1 option autoselected in the right-hand column.  such as CH32V203-FreeRTOS

8).  You may wish to change the Project Name at the top to a name of your choosing

....  hit Finish...  whizz...  whirr...  and you have a ready to build project.

If you are not real familiar with freeRTOS but are used to Arduino you can think of a "task" as a separate Arduino sketch.
... the first lines of code in the "Task()" function are equivalent to the setup() function and will run once when the task is started.
... the code inside of the while(1) loop is equivalent to the loop() function in Arduino.
... You need to NOTE that you cannot use "blocking" functions in tasks - such as Delay_Ms().  Use vTaskDelay(xxx) instead, which yiels the time to other tasks. Normally the units of xxx can vary from 1 board implementation to another but it seems that MRS has set it to indicate mSec just like the Delay_Ms(xxx) function.

I have added a modified "main.c" to better illustrate this fact..  To use it right-click on "> User" and select Add->Existing File.
Navigate to your copy of my main.c and select it - MRS will ask if you want to overwrite which you will have to accept.

Build and upload....   Done...  If you have changed the "LED" defines near the top to reflect your board setup you should get some flashin LEDs.
( I was using a 203 board that had 2 junpers that needed to be connect to "PXx" pins of my selection.  Other boards may have the LED Pin(s) hardwired. ) 

.....  I have yet to figure out how to make this into a C++ project....   maybe soon ??







   	  
