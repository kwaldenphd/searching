# Searching and Sorting Functions

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

This lab provides a hands-on overview of different types of searching functions and techniques, as well as an introduction to different kinds of sorting algorithms. This lab also covers Boolean operators that can be useful in searching a range of database and search engine systems.

## Acknowledgements

### Experiments in Search
This lab incorporates elements of the "Experiments in Search" lab:
- Created: Henry Walker, December 31, 2003
- Revised: Henry Walker, February 27, 2006
- Marge Coahran, March 14, 2007
- Marge Coahran, April 3, 2008
- Jerod Weinman, January 2, 2009
- Jerod Weinman, March 15, 2011
- Jerod Weinman, February 25, 2014
- Jerod Weinman, January 6, 2015
- Adopted from [Run-Time Experiments](http://www.cs.grinnell.edu/~coahranm/csc105/labs/run-time-searching.shtml)

### Experiments with Sorting Algorithms
This lab incorporates elements of the "Experiments with Sorting Algorithms" lab:
- Created: Henry Walker, December 31, 2003
- Revised: Henry Walker, February 27, 2006
- Revision: Marge Coahran, March 14, 2007
- Revision: Marge Coahran, April 3, 2008
- Revision: Jerod Weinman, March 16, 2009
- Revision: Jerod Weinman, March 12, 2014
- Revision: Jerod Weinman, March 25, 2015
- Revision: Liz Rodrigues, April 9, 2019

# Review of Linear and Binary Searches

<blockquote>Q1: Provide a brief description of how a linear search works. Include a written and graphical explanation.</blockquote>

<blockquote>Q2: Provide a brief description of how a binary search works. Include a written and graphical explanation.</blockquote>

Consult StackOverflow's [What is the difference between Linear search and Binary Search](https://stackoverflow.com/questions/700241/what-is-the-difference-between-linear-search-and-binary-search) to review.

See also: [Wikipedia article on Linear Search](https://en.wikipedia.org/wiki/Linear_search) and [Wikipedia Binary Search]

## What is an Algorithm?

According to [Wikipedia](https://en.wikipedia.org/wiki/Algorithm), "an algorithm is a finite sequence of well-defined, computer-implementable instructions, typically to solve a class of problems or to perform a computation."

## Basic Algorithm for a Linear Search

1. Open a new Python file in Geany to build a basic linear search algorithm.

2. The linear search algorithm we will build in Python will include the following steps or elements:
  a. define an array with a list of items
  b. define an `x` value to search for
  c. use some kind of `for` loop to interate through the values in the array
  d. output the position of `x` if `x` is present in the array
  e. output some kind of message if `x` is not present in the array

<blockquote>Q3: Based on our previous work in Python, how would you approach writing this program? What elements are you not sure how to structure?</blockquote>

3. Search for sample code that you could modify or adapt to refine your code. 

4. A few examples I found:

From [GeeksForGeeks.org](https://www.geeksforgeeks.org/linear-search/):
```Python
# Python3 code to linearly search x in arr[]. 
# If x is present then return its location, 
# otherwise return -1 

def search(arr, n, x): 

	for i in range (0, n): 
		if (arr[i] == x): 
			return i; 
	return -1; 

# Driver Code 
arr = [ 2, 3, 4, 10, 40 ]; 
x = 10; 
n = len(arr); 
result = search(arr, n, x) 
if(result == -1): 
	print("Element is not present in array") 
else: 
	print("Element is present at index", result); 
```

From [TheCrazyProgrammer.com](https://www.thecrazyprogrammer.com/2017/05/python-linear-search.html):
```Python
items = [5, 7, 10, 12, 15]
 
print("list of items is", items)
 
x = int(input("enter item to search:"))
 
i = flag = 0
 
while i < len(items):
	if items[i] == x:
		flag = 1
		break
 
	i = i + 1
 
if flag == 1:
	print("item found at position:", i + 1)
else:
  print("item not found")
```

5. Use these examples to modify and refine your code. 

<blockquote>Q4: Submit a functional code block (with comments) that executes a linear search in Python. Be sure to credit sources you used to refine your code.</blockquote>

## Basic Algorithm for a Binary Search in Python

6. Open a new Python document in Geany to build a basic binary search algorithm.

7. The binary search algorithm we will build in Python will include the following steps or elements:
  a. define an array with a list of items
  b. define an `x` value to search for
  c. compare `x` with an element in the middle of the array
  d. use `else...if` statements to define what happens if `x` is greater or less than the middle element
  e. output the position of `x` if `x` is present in the array
  f. output some kind of message if `x` is not present in the array

<blockquote>Q5: Based on our previous work in Python, how would you approach writing this program? What elements are you not sure how to structure?</blockquote>

8. Search for sample code that you could modify or adapt to refine your code. 

9. A few examples I found:

From [GeeksForGeeks.org](https://www.geeksforgeeks.org/binary-search/):
```Python

# Python Program for recursive binary search. 
  
# Returns index of x in arr if present, else -1 
def binarySearch (arr, l, r, x): 
  
    # Check base case 
    if r >= l: 
  
        mid = l + (r - l)/2
  
        # If element is present at the middle itself 
        if arr[mid] == x: 
            return mid 
          
        # If element is smaller than mid, then it  
        # can only be present in left subarray 
        elif arr[mid] > x: 
            return binarySearch(arr, l, mid-1, x) 
  
        # Else the element can only be present  
        # in right subarray 
        else: 
            return binarySearch(arr, mid + 1, r, x) 
  
    else: 
        # Element is not present in the array 
        return -1
  
# Test array 
arr = [ 2, 3, 4, 10, 40 ] 
x = 10
  
# Function call 
result = binarySearch(arr, 0, len(arr)-1, x) 
  
if result != -1: 
    print "Element is present at index % d" % result 
else: 
    print "Element is not present in array"
```

From [TheCrazyProgrammer.com](https://www.thecrazyprogrammer.com/2017/11/python-binary-search.html):
```Python
# Python program for iterative binary search

def Binary_search(arr,start_index,last_index,element):
	while (start_index<= last_index):
		mid =(int)(start_index+last_index)/2
		if (element>arr[mid]):
			start_index = mid+1
		elif (element<arr[mid]):
			last_index = mid-1
		elif (element == arr[mid]):
			return mid
	return -1
	
arr = [2,14,19,21,99,210,512,1028,4443,5110]
element = 4443
start_index = 0
last_index = len(arr)-1
found = Binary_search(arr,start_index,last_index,element)
if (found == -1):
	print "element not present in array"
else:
	print "element is present at index " + str(found)
```

10. You'll notice the two examples I found provide two different ways of structuring a binary search algorithm in Python, using recursion in the GeeksForGeeks example and iteration in the CrazyProgrammer example.

<blockquote>"Recursion and iteration both repeatedly executes the set of instructions. Recursion is when a statement in a function calls itself repeatedly. The iteration is when a loop repeatedly executes until the controlling condition becomes false. The primary difference between recursion and iteration is that is a recursion is a process, always applied to a function. The iteration is applied to the set of instructions which we want to get repeatedly executed." (<a href="https://techdifferences.com/difference-between-recursion-and-iteration-2.html")"Difference Between Recursion and Iteration,"</a> <em>TechDifferences</em>, 30 May 2016.</blockquote>

11. Use these examples to modify and refine your code. 

<blockquote>Q6: Submit a functional code block (with comments) that executes a binary search in Python. Be sure to credit sources you used to refine your code.</blockquote>

# Sorting Algorithms

12. We'll cover algorithms in greater depth in the next lab, but let's take a quick look at the different algorithms that can be used for searching and sorting.

<blockquote>"A sorting algorithm is an algorithm that puts elements of a list in a certain order. The most frequently used orders are numerical order and lexicographical order. Efficient sorting is important for optimizing the efficiency of other algorithms (such as search and merge algorithms) that require input data to be in sorted lists." (<a href="https://en.wikipedia.org/wiki/Sorting_algorithm">"Sorting algorithm,"</a> <em>Wikipedia</em>)</blockquote>

13. There are any number of sorting algorithms: selection, bubble, recursive bubble, insertion, recursive insertion, merge, iterative merge, quick, iterative quick, and heap, just to name a few.

<blockquote>Check out Wikipedia's <a href="https://en.wikipedia.org/wiki/Sorting_algorithm">"Sorting Algorithm" article</a> to learn more about these different algorithms.</blockquote>

14. According to [GeeksForGeeks.org](https://www.geeksforgeeks.org/analysis-of-different-sorting-techniques/), we can evaluate or compare sorting algorithms using a few key critera:
  * how much time and computer memory are required to execute the search
  * whether the algorithm uses comparison-based sorting (array elements compared with each other)
  * whether the algorithm uses non-comparison based sorting (array elements are not compared with each other)
  * whether the algorithm can accept new data while the procedure is ongoing (called an "online" sorting technique)
  * whether the algorithm is unable to accept new data while the search procedure is ongoing (called an "offline" sorting technique)
  * whether the algorithm deploys a stable search technique (elements with the same value do not change order)
  * whether the algorithm deploys an unstable search technique (elements with the same value may change order)

15. These critera (and others) can be used to determine what sorting algorithm will be the best fit based on the type and amount of data being sorted, as well as the computational resources available.

<blockquote>Q7: Choose one of the sorting algorithms documented in the Wikipedia article. Explain how the algorithm operates or functions in your own words, citing external sources as needed.</blockquote>

<blockquote>Q8: Evaluate this algorithm based on the critera outlined in the previous section's list (comparison vs. non-comparison, online vs. offline, stable vs. unstable, amount of time/memory needed to execute the search).</blockquote>

<blockquote>Q9: Based on what you know about how this sorting algorithm works, where would you start with writing Python code to execute the sort?</blockquote>

16. The [`examples.md` file](https://github.com/kwaldenphd/searching/blob/master/examples.md) in this repo has sample code for various sorting algorithms. 

<blockquote>Q10: Take one of the sample programs for your sorting algorithm and add additional comments to explain what each line of the program is doing. Be sure to credit your sources. OR (alternative): Submit a functional code block (with comments) that executes a particular sorting algorithm in Python. Be sure to credit sources you used to refine your code.</blockquote>

# Boolean Operators 

17. We were introduced to the logic of Boolean operators earlire in the semester when talking about gates and switches. Here will will see how the logic of Boolean operators can help us search more efficiently through online database systems.

## What are Boolean Operators

18. As described by [MIT Libraries](https://libguides.mit.edu/c.php?g=175963&p=1158594), "Boolean operators form the basis of mathematical sets and database logic. They connect your search words together to either narrow or broaden your set of results."

19. Boolean logic and its operators come to us from George Boole, an 18th Century British mathematician whose work is the foundation for much of the computational work that underlies digital technologies, from conditional statements to XOR circuits.

<blockquote><a href="https://en.wikipedia.org/wiki/George_Boole">Click here</a> to learn more about George Boole.</blockquote>

20. The syntax for Boolean operators is based on five key elements:
```
AND
OR
NOT
()
""
```

21. We can think of the first three operators (`AND`, `OR`, `NOT`) in terms of Venn diagrams.

22. An example from [Duke University Libraries](https://library.duke.edu/using/catalog-search-tips/expert):

<p align="center"><a href="https://github.com/kwaldenphd/searching/blob/master/images/image_1.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/searching/blob/master/images/image_1.png?raw=true" /></a></p>

### Brackets 

23. Brackets (or parenthesis) function much like parenthesis work in a mathematical operation.

24. For example `12 + 2 x 2` has a different result than `12 + (2 x 2)`. 

25. Similarly, searching `game NOT chess OR checkers` will have different results than `game NOT (chess OR checkers)`. (Example from [Duke University Libraries](https://library.duke.edu/using/catalog-search-tips/expert))

### Quotation Marks

26. Surrounding a phrase in quotation marks (`"Grinnell College"`) allows you to search for the entire phrase, rather than two distinct terms.

<blockquote>Q11: Develop a list of three related terms. Describe and illustrate the relationship of those terms using the <code>AND, OR, NOT</code>, Boolean operators.</blockquote>

<blockquote>Q12: Describe how the other two Boolean operators (brackets and quotation) marks function in your own words. Include examples in your explanations.</blockquote>

## Boolean Operators and Database Systems

27. As we have already talked about this week, search engines have different ways of moving through the metadata associated with digital information objects. Our previous work in the XML lab explored how library and information systems interact with this metadata to extract discrete pieces of information. 

28. In this section of the lab, we will look at how different information retrieval systems interact with Boolean search operators.

29. We are going to run the same (or similar) searches using three different information retrieval systems.
  a. [Google Search](https://www.google.com/) is a leading search engine platform with over 90% of the market share.
    * Browse [InternetLiveStats.com](https://www.google.com/) to see more information about Google search volume.
  b. [Primo](https://grinnell.primo.exlibrisgroup.com/discovery/search?vid=01GCL_INST:GCL&lang=en&sortby=rank) is the Grinnell College Libraries' search system.
  c. [EBSCOhost](https://grinnell.idm.oclc.org/login?url=https://search.ebscohost.com/) 

30. Use the search terms and phrases you developed for Q7 and Q8 to execute searches that use each of the Boolean operators. Run each search in all three platforms:
  a. AND 
  b. OR
  c. NOT
  d. brackets
  e. quotation marks

<blockquote>Q13: Describe your experience using Boolean operators in Google Search.</blockquote>

<blockquote>Q14: Describe your experience using Boolean operators in Primo.</blockquote>

<blockquote>Q15: Describe your experience using Boolean operators in EBSCOhost.</blockquote>

<blockquote>Q16: How did your search results vary across the three platforms? Include examples.</blockquote>

# Lab Notebook Questions

Q1: Provide a brief description of how a linear search works. Include a written and graphical explanation.

Q2: Provide a brief description of how a binary search works. Include a written and graphical explanation.

Q3: Based on our previous work in Python, how would you approach writing this program? What elements are you not sure how to structure?

Q4: Submit a functional code block (with comments) that executes a linear search in Python. Be sure to credit sources you used to refine your code.

Q5: Based on our previous work in Python, how would you approach writing this program? What elements are you not sure how to structure?

Q6: Submit a functional code block (with comments) that executes a binary search in Python. Be sure to credit sources you used to refine your code.

Q7: Choose one of the sorting algorithms documented in the Wikipedia article. Explain how the algorithm operates or functions in your own words, citing external sources as needed.

Q8: Evaluate this algorithm based on the critera outlined in the previous section's list (comparison vs. non-comparison, online vs. offline, stable vs. unstable, amount of time/memory needed to execute the search).

Q9: Based on what you know about how this sorting algorithm works, where would you start with writing Python code to execute the sort?

Q10: Take one of the sample programs for your sorting algorithm and add additional comments to explain what each line of the program is doing. Be sure to credit your sources. OR (alternative): Submit a functional code block (with comments) that executes a particular sorting algorithm in Python. Be sure to credit sources you used to refine your code.

Q11: Develop a list of three related terms. Describe and illustrate the relationship of those terms using the `AND OR NOT` Boolean operators.

Q12: Describe how the other two Boolean operators (brackets and quotation) marks function in your own words. Include examples in your explanations.

Q13: Describe your experience using Boolean operators in Google Search.

Q14: Describe your experience using Boolean operators in Primo.

Q15: Describe your experience using Boolean operators in EBSCOhost.

Q16: How did your search results vary across the three platforms? Include examples.
