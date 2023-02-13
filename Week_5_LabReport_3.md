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
(I've only inlcuded the first 15 occurances of the pattern for sake of concise report)*

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


