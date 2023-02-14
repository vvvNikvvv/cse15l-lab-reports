#**Week 5: Lab Report 3**
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

*In this example, you can either enter the directory or know the path with the files you are wanting to search. After entering changing directories to the **berlitz1** directory, we specify the pattern and name of files to search; in this case we use the asterisk to instruct the search to operate on all files of type '.txt'.

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
 various directories via the cd command.
 
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
directory.

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
