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




