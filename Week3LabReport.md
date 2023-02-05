#**Week 4 Lab Report (2)**
---
*Servers and Bugs*

---

>Here is the code to my StringServer with commented notes for reference:

![StringServer Code](https://user-images.githubusercontent.com/116247778/216794951-29ef8cd8-d7e8-4aeb-8f76-46929ab2c0f1.png)

---
>Here is the screenshot of the first string added:

![Hello, CSE 15L!](https://user-images.githubusercontent.com/116247778/216795254-40728150-343a-4aee-b310-d17beaf169d0.png)

**The methods called are as followed:**
*(methods pertaining to adding strings to string array)*

* handleRequest()
* .getPath()
* .equals()
* .format()
* .contains()
* .getQuery()
* .split()
* .add()
* .join()

The relevant argument for **handleRequest()** would be the URI value *url*, which 
initiates the process of calling all successive methods. **getPath()** is an instance
variable called by Object *url* to find the argument for **.equals()**, which in this
case is the "/" charachter used as flag to return the present contents of the string
created using the **.format()** instance variable. Using the **.contains()** method
with argument "/add-message", this program will then use instance method **.getQuery()**
to then use the **split()** for the "=" and "s" method along with the **.equals()** method 
again to parse the input and then insert the string object "Hello, CSE 15L!" afterwards to 
be added to the internal *strings* array using the **add()** method for later for continual 
output in the form of a new line per new added string object by using the **join.()** method. 
The relevenat field would be the ArrayList *strings* that now contains one element.

The field that changes is ArrayList *strings*, which is appended to with each new
"/add-message" call. The other value that changes would be *parameter[1]*, which at the time
of the method call equals "Hello, CSE 15L!". This value could be that same if someone wanted
to have a list of the same statement, but that is unlikely, so it is reasonable to say each new
string value would be different for each new addition.
The values and arguments that do not change are that way in order for the overarching method,
**handleRequest()**, to function properly.

---

> Here is the screenshot of the second string that was added:

![StringServer is working!](https://user-images.githubusercontent.com/116247778/216796083-93a2ec4c-18da-4b76-b0aa-be150c48f65e.png)

>>(This screenshot has the same answers save for a few specific details listed below)

**The methods called are as followed:**
*(methods pertaining to adding strings to string array)*

* handleRequest()
* .getPath()
* .equals()
* .format()
* .contains()
* .getQuery()
* .split()
* .add()
* .join()

The relevant argument for **handleRequest()** would be the URI value *url*, which 
initiates the process of calling all successive methods. **getPath()** is an instance
variable called by Object *url* to find the argument for **.equals()**, which in this
case is the "/" charachter used as flag to return the present contents of the string
created using the **.format()** instance variable. Using the **.contains()** method
with argument "/add-message", this program will then use instance method **.getQuery()**
to then use the **split()** for the "=" and "s" method along with the **.equals()** method 
again to parse the input and then insert the string object "The StringServer project works!"
afterwards to be added to the internal *strings* array using the **add()** method for later 
for continual output in the form of a new line per new added string object by using the 
**join.()** method. The relevenat field would be the ArrayList *strings* that now contains 
one element.

The field that changes is ArrayList *strings*, which has appended the new"/add-message" call
value "The StringServer project works!" to the previous "Hello, CSE 15L!". Also, *parameter[1]*, 
which which is ther value previosly appended, has changed from the original first string.
The values and arguments that do not change are that way in order for the overarching method,
**handleRequest()**, to function properly.

---

