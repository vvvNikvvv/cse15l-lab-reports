**Week 5: Lab Report 3**
---
*Researching Commands*

---

**grep** : *global regular expression print*

As the acronymic name suggest, this command-line utility is used to search for a plian-text data for a
specified word or set of words which are called 'patterns'. 
The template for use is 
> **grep** *[options]* **'pattern'** *[files]*

I will be exploring a few of the *options* at our disposal with grep and demonstrate a few examples.

- *grep -r*: performs a recursive search through all the files for the pattern in a given directory.


- *grep -l*: displays the name(s) of the file(s) that contain the pattern.


- *grep -i*: prints the name of the file and sentence containing the **case-insensitive** pattern.


- *grep -c*: prints the count of the number of times the pattern appears in a given file.


> Examples of *grep -r*:

*The goals of this example was to search within the entirety of the written_2 directory and return 
the path to the sentence that contains the pattern "history of ancient Greece". It is useful for
its ability to traverse sub-directories and not only just files like other grep options.*
```
nikvirrey@Niks-MacBook-Pro-2 written_2 % grep -r "history of ancient Greece"

./berlitz1/WhereToGreek.txt:        Parian Chronicles, a history of ancient Greece enscribed on marble

```

*The goal of this example was to show the ability to specify the files in a specific directory and still
have the command function as required. The benefit is to verify that a certain file has or not the desired
pattern, and if so, printing the opening line where it occurs.*

```
nikvirrey@Niks-MacBook-Pro-2 berlitz1 % grep -r "Agamemnon" WhereToIstanbul.txt

WhereToIstanbul.txt:        Achilles, and Agamemnon.

```

*As an extra example, one more broad, here we can use the command to see what files in a specific directory
contain the pattern and list them by expected filename then sentence where the pattern appears.
(I've only inlcuded the first 15 occurances of the pattern for sake of concise report).*

```

nikvirrey@Niks-MacBook-Pro-2 travel_guides % grep -r "Greece"

./berlitz1/WhereToGreek.txt:        accessible island chain from Athens, the capital of Greece. Next,
./berlitz1/WhereToGreek.txt:        the summer return to their homes on mainland Greece until the following
./berlitz1/WhereToGreek.txt:        Catholic community in Greece. In 1823, a nun from the Convent of
./berlitz1/WhereToGreek.txt:        epithet “Lourdes of Greece. ” The island is a delight, because it has
./berlitz1/WhereToGreek.txt:        sanctuary in ancient Greece) was said to be the richest of the many
./berlitz1/WhereToGreek.txt:        Parian Chronicles, a history of ancient Greece enscribed on marble
./berlitz1/WhereToGreek.txt:        become part of Greece until 1947. From 1912 to 1947, they were ruled by
./berlitz1/WhereToGreek.txt:        Greece and Turkey are now genial, at least on a day-to-day basis. One
./berlitz1/WhereToGreek.txt:        collections of artifacts in Greece. A new, air-conditioned,
./berlitz1/WhereToGreek.txt:        vacation spot for families from the cities of northern Greece, being
./berlitz1/WhereToGreek.txt:        lies off the Greek mainland in just this fashion. Part of Greece from
./berlitz1/HistoryIstanbul.txt:        southern Greece, forcing many mainland Greeks to leave their homeland
./berlitz1/HistoryIstanbul.txt:        Around 1000 b.c. mainland Greece entered a “dark age” of
./berlitz1/HistoryIstanbul.txt:        the Persians from northern Greece and unifying the entire Greek world.

```

> Examples of *grep -l*:

*In this example, you can either enter the directory or know the path with the files you are wanting to search. After entering changing directories to the **berlitz1** directory, we specify the pattern and name of files to search; in this case we use the asterisk to instruct the search to operate on all files of type '.txt'.*

```

nikvirrey@Niks-MacBook-Pro-2 berlitz1 % grep -l "Greece" *.txt

HistoryGreek.txt
HistoryIstanbul.txt
IntroGreek.txt
WhatToGreek.txt
WhereToEgypt.txt
WhereToGreek.txt
WhereToIstanbul.txt
WhereToItaly.txt
WhereToJerusalem.txt

```
 *Here is the same search as above but from  one directory out in 'travel_guides' and specifiying all .txt files
 inside the berlitz1 directory, beneficial if you know the exact location to search and don't wish to descend into
 various directories via the cd command.*
 
```

nikvirrey@Niks-MacBook-Pro-2 travel_guides % grep -l "Greece" berlitz1/*.txt
berlitz1/HistoryGreek.txt
berlitz1/HistoryIstanbul.txt
berlitz1/IntroGreek.txt
berlitz1/WhatToGreek.txt
berlitz1/WhereToEgypt.txt
berlitz1/WhereToGreek.txt
berlitz1/WhereToIstanbul.txt
berlitz1/WhereToItaly.txt
berlitz1/WhereToJerusalem.txt

```
*Here is another example of knowing the subdirectory in which you would like to search the pattern "Golf" and then 
having all the files containing it be presented. So this would be an effective process of elimination tool for 
multiple directory concerns - quicly perform an exact search in a different directory without changin the present working
directory.*

```

nikvirrey@Niks-MacBook-Pro-2 travel_guides % grep -l "Greece" berlitz2/*.txt

berlitz2/Athens-History.txt
berlitz2/Athens-Intro.txt
berlitz2/Athens-WhatToDo.txt
berlitz2/Athens-WhereToGo.txt
berlitz2/Barcelona-WhereToGo.txt
berlitz2/Budapest-History.txt
berlitz2/CostaBlanca-History.txt
berlitz2/Crete-History.txt
berlitz2/Crete-WhatToDo.txt
berlitz2/Crete-WhereToGo.txt

```

> Examples of *grep -i*:

*Here is an example of when searching "many beaches", the command looks for any string with these letters in order with
case insensitivity. You will notice 'Many' capitalized in the second file returned and not so in the first. Notice the 
return is the name of the file and a lengthy excerpt of the patterns occurance. Helpful when looking for the pattern when
case sensitivty is not a concern.*

```

nikvirrey@Niks-MacBook-Pro-2 travel_guides % grep -i "many beaches" berlitz2/*.txt

berlitz2/Boston-WhereToGo.txt:The most alluring section of the Cape is its north shore and “upper arm.” Beaches vary. The sheltered Cape Cod Bay beaches on the north shore are transformed into mud flats when the tide is out. The spectacular East Coast Atlantic beaches can have a strong undertow. On a sunny summer’s day parking lots at the latter fill up fast; at many beaches visitors need a parking permit, which can be obtained from the town hall.

berlitz2/Costa-WhatToDo.txt:Many beaches now fly the blue EU flag, which means that water quality and general sanitation meets environmental standards established by the European Union.

```

*This example employs double use of command options for easier readability. The goal being just to retrieve the file 
name the pattern occurs in case insensitively. The order of the dual commands has no affect as shown below. This is
helpful for when you are concerned solely with pattern occurance, case insensitively, and what files therein.*

```
nikvirrey@Niks-MacBook-Pro-2 travel_guides % grep -i -l "many beaches" berlitz2/*.txt

berlitz2/Boston-WhereToGo.txt
berlitz2/Costa-WhatToDo.txt



nikvirrey@Niks-MacBook-Pro-2 travel_guides % grep -l -i "many beaches" berlitz2/*.txt

berlitz2/Boston-WhereToGo.txt
berlitz2/Costa-WhatToDo.txt

```

*In this example we will keep the technique of double options for readability and demonstrate the differnce of when
you search for "city" without this command vs when you do. This will be done by using a small bash script. The goal to
demonstrate a multi-step process that could be resused more quickly. We can see that "city" is capitalized only once
in the .txt files.*

```

nikvirrey@Niks-MacBook-Pro-2 travel_guides % cat > city1.sh

grep -l "city" berlitz2/*.txt > city.txt
wc city.txt

nikvirrey@Niks-MacBook-Pro-2 travel_guides % bash city1.sh

      67      67    2012 city.txt
      
      
      
      
nikvirrey@Niks-MacBook-Pro-2 travel_guides % cat > city2.sh

grep -l -i "city" berlitz2/*.txt > city2.txt
wc city2.txt


nikvirrey@Niks-MacBook-Pro-2 travel_guides % bash city2.sh

      68      68    2040 city2.txt


```

> Examples of *grep -c*:

*This command is quite simple but can be combinded with different syntax to have very informative output. In these 
examples, we'll look at when you know the subdirectory and subtitle and need a count of a certain word in those
files. Helpful if you are citing information or would like to have a certain word mentioned a certain amount of times
in all the files, this provides direction of action.*

```

nikvirrey@Niks-MacBook-Pro-2 travel_guides % grep -c "Agamemnon" berlitz2/Athens-*.txt

berlitz2/Athens-History.txt:0
berlitz2/Athens-Intro.txt:0
berlitz2/Athens-WhatToDo.txt:0
berlitz2/Athens-WhereToGo.txt:3

```

```

nikvirrey@Niks-MacBook-Pro-2 travel_guides % grep -c "Hollywood" berlitz2/California-*.txt

berlitz2/California-History.txt:5
berlitz2/California-WhatToDo.txt:7
berlitz2/California-WhereToGo.txt:14

```





