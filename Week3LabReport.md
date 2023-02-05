#**Week 4 Lab Report (2)**
---
*Servers and Bugs*

---
*PART 1*
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

*PART 2

I choose the **reverseInPlace()** method to fix because at first it was very easy, simply using 
a temporary array to store all original content and then backfilling the orginal array with its
original content in reverse. After reading clearly, the goal was to NOT create a new array. So
after a few scratch tests, I found on that worked form within the orginal array itself using only
a temporary int for holding values between swaps.

Failure-inducing input for the buggy program:
```
The failure-inducing input is {3,7,0}.
  
public class ArrayTests {
@Test 
public void testReverseInPlace() {
    
    int[] input2 = {3, 7, 0};
    ArrayExamples.reverseInPlaceBUGGED(input2);
    assertArrayEquals(new int[]{0,7,3 }, input2);

  	}
 ```
 The arrays first differed at element[2]: expected:[3] but was: [0].
 This is because the code produces a mirror of contents from the middle of
 only the last elements in the beginning of the array and then replaces the 
 end of the array with the previous values.
 
 Non-Failure-inducing input for the buggy program:
 ```
The non-failure-inducing input is {3}.
 
public class ArrayTests {
@Test 
public void testReverseInPlace() {

    int[] input1 = { 3 };
    ArrayExamples.reverseInPlaceBUGGED(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
    
    }
 ```
No errors shown because the array has only one element, it simply replaces
arr[0] with arr[0] based on the algorithm.

 The symptom of these two inputs by running jUnit tests:

*Failure-inducing*

![Failure-Inducing](https://user-images.githubusercontent.com/116247778/216797361-3e5b6067-b704-490b-abd9-26349b1a2e05.png)

*Non-Failure-inducing*

![Non-Failure_Inducing](https://user-images.githubusercontent.com/116247778/216797433-2ae4092d-122d-4ed3-a9a3-47f07efe3d5f.png)

The buggy code before the fix:

```
static void reverseInPlaceBUGGED(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
The code after the fix:

```
static void reverseInPlaceFIXED_TWO(int arr[]){

    for(int i = 0; i < (arr.length/2);i++){
      int j = 0;
      int k = arr.length - 1;
      int temp = arr[j];
      arr[j] = arr[k];
      arr[k] = temp;
      j++;
      k--;
    }
  }
  
```
The code previously replaced all elements before middle correctly with elements after, but
at the middle it would replace the back with the new values from the front which were the 
original back. The fix is is to have the iterator stop once at half the size of the array's 
length, this utilizes integer division positively in that if the array is odd or even, it
still performs correctly for all possible inputs. Then have seperate counters for with 
initialized values of the zeroth element and the nth element. The zeroth is incremented and 
the nth is decremented. The temporary int value is to hold the zeroth(and subsequent) to be
given to the nth(and precedent), this happens after zeroth is given the value of nth.
I've included screenshots of my trace-building of the fixed algorithm.

> The trace-building of the algorithm and examples to demonstrate correctness:

Trace of the Bug

![Trace Bug](https://user-images.githubusercontent.com/116247778/216797760-8c12026d-3b05-40dd-801e-937c9b709402.png)

Trace of Even Proof

![Trace Even Proof](https://user-images.githubusercontent.com/116247778/216797767-ee75ec03-9deb-428a-aa80-136d0f6fe732.png)

Trace of Odd Proof

![Trace Odd Proof](https://user-images.githubusercontent.com/116247778/216797771-d1c08dd4-3d66-4724-a7e5-f8f6314820ef.png)

---

*PART 3*

I've learned many things that I had not heard of before, but I think the coolest topic is the power of
jUnit to strengthen your code and the strengthen your understanding of your code. The asserEquals when you
want to compare values and assertSame if comparing objects. I'm growing more confident in assertThrows and
assertTrue/False. I've heard before that a strong style of coding is to design tests before ever writing algorithms, and I think jUnit is a hard argument for that. Looking forward to implementing a tester file to all future projects!


















  
