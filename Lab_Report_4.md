 **Week 8: Lab Report 4**
 
---

*Baseline "Done Quick" Challenge*

*Step-by-Step*

---

**Step 1: Delete any existing forks of the repository you have on your account**

*Keys pressed:* ```<c><d><space><.><.>``` (cd out of Lab7/)
               ```<r><m><space><-><r><f><space><l><tab><enter>```(after typing l, enter will auto-fill the rest)
               Now remove the repository from your gitHub account by selecting the
               repository, going to settings, and scrolling down to remove option.
               You will need your password for this, so be prepared.
               
> Image of Terminal after commands:

![rm -rf lab7:](https://user-images.githubusercontent.com/116247778/221094196-a43eeeb5-fddd-429d-9663-0d394a96eada.png)

> Image of Delete this Repository from GitHub:

![Delete Repository](https://user-images.githubusercontent.com/116247778/221094274-4c31ba50-3ad3-4e1b-9ea6-1838fc0a5b75.png)

Now go to your GitHub account, access the lab7/ file your forked, then proceed to click on *settings* and scroll down
until you see the *Delete this Repository* and click it. It will ask you to type your username followed by the name of 
the repository you are trying delete, in this case it will be *yourUsername*/lab7/.

>Image of deleting fork for from GitHub acount:

![Delete fork](https://user-images.githubusercontent.com/116247778/221377021-58178655-160b-4e1c-aa60-07a439bc05f0.png)

*For this step I used the cd .. to exit out of the lab7/ directory and proceeded to remove the directory
by using the rm -rf lab7/ command. I also explained how to remove the repository from the Github site
and included an additional screenshot. I had done other commands after completing the last step, so this was actually
faster than clicking up 15+ times. Now that the repository is deleted form both the GitHub account and the server, we 
setup from scratch!*

---

**Step 2: Forking the repository**

First, go to the provided link to fork the lab7/ repository and look to the top right corner and find the fork option
and press it.

>Image of where to fork the repository:

![Fork 1](https://user-images.githubusercontent.com/116247778/221377887-cf13c4fe-c875-4249-938e-24a779e4964f.png)

After clicking, you will get a confirmation with allowance to give a custom description.

>Image of creating the fork:

![Fork 2](https://user-images.githubusercontent.com/116247778/221378019-91c5bf02-cb7c-4e10-92c9-4919af5ec7db.png)

Now you have the repository forked and ready for use by any server!

---

**Step 3: The real deal Start the timer**

If you don't have a smartphone or smartwatch, google 'timer' for simple use of a stopwatch feature.

>Image of google stopwatch:

![google timert](https://user-images.githubusercontent.com/116247778/221378270-84c5b586-88be-4cfe-91b2-2aafc1186746.png)

---

**Step 4: Log into ieng6**

*Keys pressed:* ```<up><up><up><up><up><up><up><up><up><enter>```

Pressing the up key 9 times got me to the command ```nikvirrey@Niks-MacBook-Pro-2 ~ % ssh cs15lwi23ana@ieng6.ucsd.edu```
which will log me into my ieng6 account. Then you press enter once to execute the command. No passwords are needed because we created
a SSH key for our ieng6 accounts.

>Image of logging into ieng6:

![Log into ieng6](https://user-images.githubusercontent.com/116247778/221378525-5f11f4ba-adf5-430e-89ae-557fe3bf566a.png)

---

**Step 5: Clone your fork of the repository from your GitHub account**

*Keys pressed:* ```<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>```

Pressing the up key in the ieng6 server 16 times got me to ```[cs15lwi23ana@ieng6-202]:~:442$ git clone git@github.com:vvvNikvvv/lab7.git```
line and then I pressed enter to execute the command. You will see the last word 'done' when the cloning has successfully completed.

>Image of cloning the repository:

![Press Up to Git Clone](https://user-images.githubusercontent.com/116247778/221378897-6f5a73b9-1727-472e-82c9-727d6683badc.png)

---

**Step 6: Run the tests, demonstrating that they fail**

*Keys pressed:* ```<c><d><space><l><enter>``` (cd into lab7/, after typing l, enter will auto-fill the rest)

>Image of cd'ing into lab7/:
                
![cd lab7:](https://user-images.githubusercontent.com/116247778/221379205-af0f61d4-1d3a-477f-84b0-3fb64193aa42.png)

*Keys pressed:* ```<up><up><up><up><up><up><up><up><up><up><up><up><up><enter>```

Pressing the up key 13 times get us to ```javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java``` and hitting the enter
key will execute the command to compile the JUnit tests. 

*Keys pressed:* ```<up><up><up><up><up><up><up><up><up><up><up><up><up><enter>```

Now, pressing the up key 13 more times will get us to ```java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples JUnit version 4.13.2``` and hitting the enter key will execute command to execute the JUnit tests.

>Image of demonstrating the failed tests:

![Test Fails](https://user-images.githubusercontent.com/116247778/221379470-de5d8da7-502f-494f-badf-8d83ff6efddd.png)

---

**Step 7: Edit the code file to fix the failing test**

*Keys pressed:* ```<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>```

Pressing the up key 16 times gets us to the line ```nano ListExamples.java``` which will let us edit the ListExamples file in
order to fix the bug that is failing the tests.

>Image of the editable file after nano'ing into it:

![nano file](https://user-images.githubusercontent.com/116247778/221379623-7956eb10-5910-42a6-aa1f-60b4b7a47af9.png)

*Keys pressed:* ```(holding down)<down>```(hold down the down arrow until you reach the bug)

Holding down the down arrow until you reach line containing the bug, which in our case is ```index1 += 1``` 

>Image of cursor reaching the bug line:

![scroll down to index1](https://user-images.githubusercontent.com/116247778/221379787-a95f85e2-9017-450e-89e8-87f69ca226cd.png)


*Keys pressed:* ```<right><right><right><right><right><right><right><right><right><right><right><delete><2>```

Pressign the right arrow key 11 times and then delete key once, will delete the 1, then press the 2 key to fix the bug.

>Image of bug fixed:

![bug fixed](https://user-images.githubusercontent.com/116247778/221379949-cf85de20-7ebd-47c7-bc95-c295a29daccc.png)

*Keys pressed:* ```<ctrl><o><enter><ctrl><x>```

Pressing ctrl-o will save the edits you made. You will be prompted to name the file, but you don't want to change the name, so
you just press the enter key. Now to exit the nano editor you press ctrl-x. All done.

---

**Step 8: Run the tests, demonstrating that they now succeed**


---

**Step 9: Commit and push the resulting change to your Github account**

*Keys pressed:*  ```<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>```

Pressing the up key 16 time will get you to the line ```git add ListExamples.java``` hitting enter will add the new version
of the file to the directory

*Keys pressed:*  ```<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>```

Pressing the up key 16 times will get you to the line ```git commit -m "Done"``` hittin enter will commit the change.





