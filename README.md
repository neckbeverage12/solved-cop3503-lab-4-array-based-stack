Download Link: https://assignmentchef.com/product/solved-cop3503-lab-4-array-based-stack
<br>
<h1>Overview</h1>

In this assignment, you will be implementing your own <em>Array-Based Stack</em> (ABS). A <strong>stack</strong> is a linear data structure which follows the last in, first out (LIFO) property. LIFO means that the data most recently added is the first data to be removed. (Imagine a stack of books, or a stack of papers on a desk—the first one to be removed is the last one placed on top.)




The typical operations of a stack are:

<strong>Push</strong> – Add something to the top of the stack

<strong>Pop</strong> – Remove something from the top of the stack and return it




<strong>Example of a LIFO-the data most recently added is the first to be removed</strong>

<h1>Description</h1>

Your ABS will be a template class, and thus will be able to hold any data type. (Many data structures follow this convention—reuse code whenever you can!) As with previous classes that use dynamic memory, you must be sure to define The Big Three: The Copy Constructor, the Assignment Operator, and the Destructor.

Data will be stored using an array (hence the <em>array-based </em>stack)<em>.</em> You may use any other variables/function in your class to make implementation easier.

By default, your ABS will have a scale factor 2.0f.

<ol>

 <li>Attempting to push() an item onto an ABS that is full will scale its capacity by the scale factor.</li>

 <li>When calling pop(), if the “percent full” (e.g. current size / max capacity) becomes less than</li>

</ol>

1/scale_factor, decrease the capacity of the ABS by 1-1/scale_factor




<strong>Why increase (or decrease) the size by any amount other than one? </strong>

Short answer: performance!

If you are increasing or decreasing the size of a container, it’s reasonable to assume that you will want to increase or decrease the size again at some point, requiring another round of allocate, copy, delete, etc.

Increasing the capacity by more than you might need (right now) or waiting to reduce the total capacity allows you to avoid costly dynamic allocations, which can improve performance—especially in situations in which this resizing happens frequently. This tradeoff to this approach is that it will use more memory, but this speed-versus-memory conflict is something that programmers have been dealing with for a long time.




<strong>The images above assume a 2.0f scale factor</strong>

Your ABS will support the following methods:

<ul>

 <li>ABS(): Default constructor. Capacity should be initialized to 1, and size should be initialized to 0.</li>

 <li>ABS(int capacity): Constructor for an ABS with the specified starting capacity.</li>

 <li>ABS(const ABS &amp;d): Copy constructor.</li>

 <li>ABS &amp;operator=(const ABS &amp;d): Assignment operator.</li>

 <li>~ABS(): Destructor for an ABS.</li>

 <li>void push(T data): Add a new item to the top of the stack.</li>

 <li>T pop(): Remove the item at the top of the stack, and return its value. Throws -1 if the stack is empty.</li>

 <li>T peek(): Return the value of the item at the top of the stack, without removing it. Throws -1 if the stack is empty.</li>

 <li>unsigned int getSize(): Returns the current number of items in the ABS.</li>

 <li>unsigned int getMaxCapacity(): Returns the current max capacity of the ABS.</li>

 <li>T* getData(): Returns the array representing the stack. This should only be used in order to implement the copy constructor or assignment operator.</li>

</ul>







<h2>Extra Credit (1%)</h2>

You can earn up to 1% extra credit (toward your final course grade) for this lab by doing everything listed below. DO NOT work on extra credit until your standard lab scored full points. If your standard lab does not pass everything, you cannot earn any extra credit.




Update ABS

Update your ABS to use a scale factor other than 2.0f, and modify any methods that should behave differently as a result:

<ul>

 <li>ABS(int capacity, float scale_factor) : Constructor for an ABS with the specified starting capacity, and a custom scale factor.</li>

</ul>




Add an extra attribute to your ABS, total_resizes, which is a count of how many  times the ABS has been resized. Add an accessor for this attribute:

<ul>

 <li>unsigned int getTotalResizes(): Returns the total number of times the ABS has  been resized.</li>

</ul>




Analysis Report

Create a testing file that can perform the following tasks, each with an ABS that starts with a max capacity of 2:

<ul>

 <li>push <em>N</em> items onto an empty ABS.</li>

 <li>pop <em>N </em>items off an ABS with <em>N</em>  items already on it.</li>

</ul>

For each of the tasks, record:

<ul>

 <li>How long it takes to perform the task</li>

</ul>

○ Use the &lt;chrono&gt; or &lt;ctime&gt; libraries

<ul>

 <li>How many resizes were performed during the task</li>

</ul>




Do the tasks for each of the following possible combinations of Scale Factor and N:

<table width="242">

 <tbody>

  <tr>

   <td width="106"><strong>Scale Factor </strong></td>

   <td width="136"><strong>N </strong></td>

  </tr>

  <tr>

   <td width="106">1.5</td>

   <td width="136">10 000 000</td>

  </tr>

  <tr>

   <td width="106">2.0</td>

   <td width="136">30 000 000</td>

  </tr>

  <tr>

   <td width="106">3.0</td>

   <td width="136">50 000 000</td>

  </tr>

  <tr>

   <td width="106">10.0</td>

   <td width="136">75 000 000</td>

  </tr>

  <tr>

   <td width="106">100.0</td>

   <td width="136">100 000 000</td>

  </tr>

 </tbody>

</table>




You should have 50 different sets of data (2 tasks * 5 scale factors * 5 Ns).

Graph the data for each scale factor, with N being the independent variable and time being the dependent variable. Include the number of resizes for each task somewhere on the graph as well.

You should have 5 graphs, one for each scale factor.




Write a 1-2 page analysis of your results. Make note of any trends in the data. How does N affect the time it takes for? What are the effects of changing scale factor? How do both of these affect the number of times the ABS will be resized? What seems to be the best scale factor, and why? These are the types of questions you should try to answer in your analysis.

Submission (on Canvas):




<ul>

 <li>Your updated ABS.h file</li>

</ul>