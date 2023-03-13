 **Week 9: Lab Report 5**
 
---

*Grading Script (SkillDemo2Practice)*

**STEP 1: Fix the code**

Here I took the foundation of *grade.sh* and included the necessary *cd*'ing into the 
students directory and verification of the existence of the file and the appropriate
response depending. Then we move on to the *cp*'ing of the *TestListExamples* file and
repeat the previous step. From here I stored the output from both the compile and execute 
commands in differnt *.txt* files and used the *grep -q* command to search for various 
key words to help with responses that would be fitted to the different successful and 
unsuccessful out comes. Below I have provided the code block.

> *grade.sh* code block:

```
CPATH='.:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar'

rm -rf student-submission
git clone $1 student-submission
echo 'Finished cloning'

cd student-submission

if [[ -f ListExamples.java ]]
then
  echo 'ListExamples.java found'
else
  echo 'ListExamples.java not found'
  echo 'COMPILER ERROR, you fool!'
  echo  ""
  echo "______________"
  echo "| Score: 0/4 |"
  echo "______________"
  echo ""
  exit 1
fi

cp ../TestListExamples.java ./

if [[ -f TestListExamples.java ]]
then
  echo "TestListExamples.java copied."
else
  echo "TestListExamples.java NOT FOUND."
  exit 2
fi

javac -cp $CPATH *.java 2> compile.txt
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > output.txt
#cat output.txt

  if grep -q "error" compile.txt
then
  echo COMPILER ERROR
  echo  ""
  echo "______________"
  echo "| Score: 0/4 |"
  echo "______________"
  echo ""
  exit 1                #SHOULD THESE EXITS BE NONZERO?
fi

if grep -q "timed out" output.txt
then
  echo TIMED OUT
  #exit 4
fi

if grep -q "Ok" output.txt
then
  echo Success!
  exit 0
fi


FAILURES=`grep -c FAILURES!!! output.txt`

if [[ $FAILURES -eq 0 ]]
then
  echo 'All tests passed'
  echo  ""
  echo "______________"
  echo "| Score: 4/4 |"
  echo "______________"
  echo ""
else
  echo "sentinel"
  line='grep 'Tests run:' output.txt'
  echo $line
  failures=${line:(-1)}

  RESULT_LINE=`grep "Tests run:" output.txt`
  COUNT=${RESULT_LINE:25:1}

  echo "JUnit output was:"
  cat output.txt
  echo ""
  echo "--------------"
  echo "| Score: $COUNT/4 |"
  echo "--------------"
  echo ""
fi
```

**STEP 2: Test all the student submissions**

*list-methods-lab3*

This file contains the same code as lab 3.

```https://github.com/ucsd-cse15l-f22/list-methods-lab3```

> Image of the output for this student submission:

<img width="866" alt="list-methods-lab3" src="https://user-images.githubusercontent.com/116247778/224834072-0da23255-43c0-48e2-8ae8-26f8227c68bd.png">

We can see that the two errors were caught, the incorrct array ordering as well as the time out action, and the score was given accordingly.

---

*list-methods-corrected*

This file contains all errors corrected and is expected to recieve 4/4 points.

```https://github.com/ucsd-cse15l-f22/list-methods-corrected```

> Image of the output for this student submission:

<img width="900" alt="list-methods-corrected" src="https://user-images.githubusercontent.com/116247778/224840078-60478af1-1484-432f-bf0e-490a4f040250.png">

We can see that the perfect score was given for the corrected version, as expected.

---

*methods-compile-error*

This file is missing a semicolon after *result.add(0, s)* and therefore has a compile error.

```https://github.com/ucsd-cse15l-f22/list-methods-compile-error```

> Image of the output for this student submission:

<img width="928" alt="list-methods-compile-error" src="https://user-images.githubusercontent.com/116247778/224840987-abc3d8d7-059e-4991-b5f1-ba24463a2daf.png">

We see that both files were found, but compilation failed - so a score of 0/4 was given. Compilation is mandatory.

---

*list-methods-signature*

This file has the parameters in the wrong positions for the *filter* method and thus fails compilation, recieveing 0/4 points.

```https://github.com/ucsd-cse15l-f22/list-methods-signature```

> Image of the output for this student submission: 

<img width="897" alt="list-methods-signature" src="https://user-images.githubusercontent.com/116247778/224843531-e543823d-d287-4295-a28a-f3c19f113f14.png">

We can see the file was found but then the mismatch parameters caused a compile error.

---

*list-methods-filename*

This file contains the correct implementation but has the incorrct filename, causing it not to be found.

```https://github.com/ucsd-cse15l-f22/list-methods-filename```

> Image of the output for this student submission: 

<img width="891" alt="list-methods-filename" src="https://user-images.githubusercontent.com/116247778/224842379-a12f107c-4e00-42f4-a06a-c4e4a6809881.png">

We can see that the file was unable to be found and thus an immediate exit occured with no compilation and a 0/4 score.

---

*list-methods-nested*

This file contains the proper implementation and file name, but within a subdirectory that causes the not found error.

```https://github.com/ucsd-cse15l-f22/list-methods-nested```

> Image of the output for this student submission: 

<img width="876" alt="list-methods-nested" src="https://user-images.githubusercontent.com/116247778/224845195-6a967d35-549a-489f-ba36-0cd6c00ba224.png">

We can see the output from the code has become more aggressive with this type of error (haha, jk), awarding 0/4 points.

---

*list-examples-subtle*

This file contains a subtle issues with value/address comparison as well as logical errors of dynamic instantiationn placement.

Challenge:``` https://github.com/ucsd-cse15l-f22/list-examples-subtle```

> Image of the output for this student submission: 

<img width="887" alt="list-examples-subtle" src="https://user-images.githubusercontent.com/116247778/224846941-91f9320b-7cb3-4b4f-adf6-a4ae0c46854d.png">

---

**STEP 3: Conclusion**

The goal of the last portion of class content for CSE 15l and nearly the entirety of CSE 12 was focus on debbugging via testing. 
I believe utilizing *@Test* methods and files have greatly improved my coding quality. Here, the goal was to write code to catch 
the errors known to be existent, but it is a beneficial way of reverse learning what to code for when you are unaware of possible
errors. Things like signature check, file existance, reasons for compile errors via grep commands on text files hold the outputs 
in order to be more precise with output. I am finallly convinced after this quarter that testing and javadoc should be completed 
prior to coding as a insurance of understanding and the benefit of having the wholistic project in mind as you begin on the individual
and compartmentalized portions of the code.

---


