**Week 1 Lab Report**
---
*How to log into a course-specific account on ieng6*


1) Setting up Visual Studio Code

(Note: If you do not wish to use a personal laptop, feel free to use the computers 
provided in the CSE building which have VS Code.)

To begin, click this link: [Visual Studio Code](https://code.visualstudio.com/) and 
follow each instruction for your given operating system.

If correctly installed, you should be able to open the application and see a similar
window as below (Note: may not be look identical based on different systems)

<img width="1026" alt="VS Code" src="https://user-images.githubusercontent.com/116247778/212201975-05f7265e-c727-4ddc-971c-db33c3e0c339.png">

(Note: disregard my 'Recent' files, yours will be empty.)



2) Remotely Connecting

Now we will connect remotely to a computer via our course-specific accounts we have activated.

For Windows users, you need to download **git** for Windows here : [git](https://gitforwindows.org/) to use ssh.

Mac users, you are able to access ssh from a new terminal in the VS Code window directly

Now we are all on the same footing, go to the toolbar and click 'Terminal' then select 'New Terminal',
it should look like this:

<img width="1022" alt="Screen Shot 2023-01-12 at 4 02 27 PM" src="https://user-images.githubusercontent.com/116247778/212206884-4b3a6b8d-1f21-40d3-bf7a-769d4c0a8fba.png">
Terminal is highlighted red and the yellow error shows where you will be entering information.

Now, to use **ssh**, type in 'ssh' before your course-specific account, my account is **cs15lwi23ana@ieng6.ucsd.edu**.
Yours will be identical *except* for the letters after '23' ('ana' in my case), yours are specific to you.

You will then be prompted to enter your password and hit enter. You will not be able to see the password for security purposes, so type it calmly and correctly. Your first sign in will default a warning regarding authenticity of the accout
and will ask if you are wish to continue connection - type 'yes'

It should look like this if successful:

<img width="1026" alt="Screen Shot 2023-01-12 at 4 09 44 PM" src="https://user-images.githubusercontent.com/116247778/212207773-da045b25-c425-4c88-8b50-ac23ec062ed8.png">

Note: if you enter incorrectly more than 3 times, your connection will be lost. I know from experience!
This case will look something like this:

<img width="687" alt="Screen Shot 2023-01-12 at 4 16 18 PM" src="https://user-images.githubusercontent.com/116247778/212207948-242c8598-bf7a-43ac-a3e4-d1a0bd75d01d.png">

If you were successful, congratulations, you have successfully remotley connected to a computer in the CSE basement.
If not, please reach out for help, the professor and staff are all too willing and able.
Now, to test a few commands on our newly made remote connection.


3) Trying some commands

Now that we have our connection, we can use some common Terminal commands to gain some familiarity for what is possible
from this new technology.

Here is a link to check out a few commands before a demonstrate a handful as examples: 
[Terminal Commands](https://www.techrepublic.com/article/16-terminal-commands-every-user-should-know/)

The 'cd' command: "Change Directory" - this is used to switch the current working directory to the given path.
(Note: you will see no action with this command, but trust it has done its job)

<img width="487" alt="Screen Shot 2023-01-12 at 4 35 55 PM" src="https://user-images.githubusercontent.com/116247778/212210183-8a328f06-bc59-425b-b3b8-069114f7450b.png">

To see what 'cd' did, or to know where we are in the system, we use the 'pwd' command: "Print working directory".
This is used to display the current working directory.

<img width="489" alt="Screen Shot 2023-01-12 at 4 38 29 PM" src="https://user-images.githubusercontent.com/116247778/212210456-9d487757-7bd5-4cf7-842c-fb6d93985480.png">

Now that we know where we are, we can use the 'ls' command: "list" to list out all the files and folders of the 
given path.

<img width="476" alt="Screen Shot 2023-01-12 at 4 40 30 PM" src="https://user-images.githubusercontent.com/116247778/212210675-364d6e20-3346-4144-975e-821139d81388.png">

Another useful command is 'top', which gives a real-time look at all actively running computer processes, including
memory and CPU!

<img width="492" alt="Screen Shot 2023-01-12 at 4 45 57 PM" src="https://user-images.githubusercontent.com/116247778/212211516-dc48ae0c-b5db-4f69-bfe8-c8f7b9f6ded3.png">

When you are prepared to exit the connection from the terminal, simply use either

* Ctrl + D
* exit

Good luck with your future exploring!







