# Part1

For first question of the assignment, I implemented three classes; Word, Sentence and Main class. I used composition relationship between Word and Sentence classes, because every sentence has words.  The sentence class has two fields; the sentence and Wordlist. WordList consists of Word objects. 
In Main class, I read the txt file and divide it to words. I created two ArrayLists for words. 
One of the ArrayLists includes the words without punctuation marks. 
[The, term, First, World, War, was, first, used, in, September, 1914… ]
I create Word object ArrayList and assign it to without punctuation mark ArrayList. 
And then ArrayLists<Word> .getName() become like:  
[The, term, First, World, War, was, first, used, in, September, 1914… ]
The other ArrayList includes the words with punctuation marks, 
[n;The, term, "First, World, War", was, first, used, in,…]
Actually I keep array with punctuation to estimate correctly the sentences. 
I define two rules to define sentences correctly. 
First rule to create a sentence is punctuation
•	I traverse the ArrayList to control if any punctuation symbol occurs. Like (. ? !)
I saw there is ... in txt file however it was not the end of the sentence. 
For this reason I decided to put another control to check if this is a sentence or not. 
Second rule is 			
•	If punctuation symbol occurs, it will be sign that this can be the end of the sentence. I control if the first character of the element of the punctuation symbol's is lower case or not.
I can check also if it is uppercase or not. Actually I just want to learn if it is a letter. 
When ... comes, program controls the last dot and then will check the first dot
the first dot is not a lower case; So program will understand this is not the end of the sentence.I will assign all the words before this punctuation symbol as a sentence. 
and I create a Sentence array.
Program is creating Sentence, Word ArrayLists . 
The xml shows that; every sentence and its word values which is stored in WordList field in Sentence object. 
What can be other approaches? 
Instead of creating a composition between Sentence and Word, Inner class can be another approach for this problem. 
It can be like: 
class Sentence {
	class Word{
}

}
Inner classes should be defined in the function of the main class. It does not seem like efficient way for me. Because I have to do all Word operations in a function of a Sentence class.
 I thought that static inner classes can be a solution because static inner class works like normal class, you do not need to instantiate it in the class and you can think static inner class as subgroup of the class. It can be better than normal inner class however I think it is still not good enough to implement. I would like to write clean code and from a maintenance point of view, I find the inner class difficult to understand. 

The other approach, most known approach is Abstract class . 
However Word is NOT a Sentence  and Sentence is NOT a Word. Abstract class is a strong statement and child class fundamentally extends a parent class. Moreover, abstract classes cannot be instantiated by itself. I exactly needed Word objects in my object-oriented design.

An interface can be defined for the common features for Sentence and Word. However it does not seem like an efficient approach. I especially based on Java-Object model. 

Why I used ArrayList? 
•	Array lists manage arrays internally, traversing in array is very fast.
•	Getting a particular item is very fast.
•	ArrayList structure looks like Arrays [0][1][2][3][4].
I would like to use ArrayList with that reasons. I do not prefer linked list because 
Other approach LinkedList:
Linkedlists consist of elements each elements has a reference to the previous and next element. It is structure is like  [0]->[1]->[2] ...
For this reason iterating thru in LinkedList is not efficient for looking for a word. 
I would use LinkedList used it  if I have a large number of insert or delete operations but I do not.
Other approach Set:
Whether my favorite data structure is set, set will be the worst approach for this problem. Because it store unique values. 
The nsp_data.txt file contains more than one “the” word. So it will be a problem.
It is more likely greate for removing duplicates. However set will be perfect for checking particular object because it is very fast.

Limitations of Composition and ArrayList	
The disadvantage of composition, you must be able to use the subtype anywhere where the supertype is expected. 
 I need to create WordList for every Sentence object. However it was what I would like to do. 
In addition that that, using ArrayList is kind of more expensive to create and maintain.

