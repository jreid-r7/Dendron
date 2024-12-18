---
id: wvnlnlk9ozcagec8k05twiz
title: '2024'
desc: ''
updated: 1732550144157
created: 1731575983396
---

## Jack Gibson

Interested in Metasploit and listens to podcasts related to security.

### String reversal - used a stack

Asked to do again without stack - did reverse for loop

\> 0 - knew off by one errors.

Splitting to numerics and alphabetical - thinking about unicode. Two ifs - knows about switch - maybe not enough conditions to warrant a switch.

Moved to implementation and did a good job. Was able to move to an array based approach.

### Coin balance

Got the binary idea with 3 turns fairly quickly.

Took some prompting and got to the 3, 3, 2 solution with two turns.

### Melting candles

Plenty of prompting - understood the solution. Started to think about generalising the problem.

## James Bothwell

### String reversal

Really nice double ended solution with a temp variable. Good understanding of potential issues with assignment cost. Able to optimise the double ended while condition for odd length strings. Knew Java strings are immutable.

### Fibonacci

Good logical work through. Quick to understand limitations and problems with their idea and potential solution.

### Coins

Brute force - worked out quickly 1 - 7 iterations

More efficient - moved to binary nice and quickly 3 iterations

2 iteration solution - he had an intuitive idea that groups of 3 would work. Was surprised that he came to the answer.

## John McKee

### String reversal

Decent stab - listens to guidance, spotted issues, did an n iteration solution then worked to n / 2.

Could also describe a bubble sort - wasn't convinced by the implementation, however.

### Coin balance

Brooklyn 99?

Quick jump to the binary solution.
4 -> 4
2 -> 2
1 -> 1

Tried to discuss brute force, but he was still more efficient than 7! Got iterations.

Was asked to find a solution that does 2 iterations every time. Find a different way of splitting suggested.
3 -> 3 first
Got there

### Candles

Intuitively jumped to 1/2 and 1/4 for the end state and derived 3 hours from that.

## Minsur Choi

### String reversal

Quite clear pseudo code. First person to mention exceptions.

Reasonable understanding of the concepts of strings and arrays but needed prompting. Tendency to maybe over-complicate ideas in his head.

Good conversations and interaction.

### Gold bar problem

1st pass straightforward 4 cuts. Then started to think about how to do fewer cuts. Stuck on dividing into five parts. Got 3 cuts with disgonal lines. Hinted with the term transaction. 

Really good questions at the end showing appropriate curiosity.

## Niamh Mason

### String reversal

Nice solution where we take each char and prepend to the output string. 

Super clarity of thought. Worked through a really good char solution using no temp index. 

### Fibonacci

Has solved before. Knew about the special cases. Introduced a bug in her loop with the start index. Worked through rigorously.

### Gold bars

Straight to 4 cuts, guessed there was a better way. Initially fixated on producing 5 pieces.

### Candles

Overthought initially. Worked out a solution reasonably quickly.

## Rhianne Bassett

### String reversal

Quick to come to reverse iteration. Take char at index and add to new string. index decreasing each time. Append char to result. Was able to optimise using char arrays.

Norman's extension to count alphabetic characters and count the numbers. Talked through well, she's very conversational and relatable.

### Gold bars

Straight to four cuts. Really got caught up and missed the notion that she could take the 1/5 back off the worker. We got there.

## Leo Chartier

### String reversal

Add some validation, is it a string, is it longer than one character.

If statement with for loop inside. Index from 0 up. Thought quickly to start from end of string. Got index out by 1. Confused a bit by static. 

Very wordy, but seems to understand ok.

### Coin balance

Suggested binary search. Initial max 7.

Moved to 4 a side. 4, 2, 1 - binary search. 3 iterations.

Bit of prompting to get to 2 iterations.

## Conor McQuillan

### Reverse String

Straight away thinking about validation. Method to reverse a sequence of characters.

Iterate through each character in the string. Create temporary string and append characters to that. Worked through the iterations on the board without prompt.

Implementation in Python.

Given the idea of using arrays. Asked to implement that. Got the ```for``` loop fine. Worked out the off by one issues with indexes.

### Coins puzzle

Drew coins in a row!

Straight to split in half. 3 iterations. Identified that 3 is always the answer.

Told could be done in 2 - got the answer.

### Candles problem

Straight to drawing. Thinking about rates of burning. Made them 12cm tall, 2cm/hr and 3cm/hr. Moved to graph but not lined up - bit weird. Worked hour by hour and got three hours.

### Questions

Size of team, type of work. What is a micro-service?

## Eben Rainey

### String reverse

Straight to char array in Java. Single iterator. Work backwords through output array, forwards through string. Strings are immutable - got the issue of memory management. Sanity checking - did null or empty. Identified point of first error.

Asked to implement something that runs in half the time. Thought very quickly of pointing at each end and using a while loop. Clever chap, thinking of issues, identifying further optimisations on suggestions.

### Fibonacci

Decided he would give it a go recursively.

### Coin puzzle

Straight to binary search. 3 comparisons. Asked himself if there was a better way. Very quick to 3, 3, 2.

## Eva Barr

### Reverse string

Gosh, she's quiet. Temp variable. Reverse for loop from string ength to greater than zero. Nice pseudo code - using prepend approach. Moved onto implementation. Return and parameter types ok. Suggested could be done in half the iterations she got the while loop and moving from both ends.

### Coin puzzle

Straight to binary and 3 comparisons.

Prompted that it can be done in 2. Some prompting and got there with uneven groups.

### Questions

How are teams structured?

## Grace Coyle

### Reverse string

Had read on leet code - quite unsure as to what she was doing. Confused as to what types things were. Prompted for null. Got NullPointerException

### Coin puzzle

Got to binary quickly. Was able to discuss nicely optimisations of these and how to split things up.

## Aidan Juma

### Reverse string

Got a straight right to left iteration straight away with some clunky pseudo code. prompted to consider how to do it in fewer iterations. Eventually got to going from each end simultaneously. Lots of extra steps. Thinks in TypeScript. Prompted to NullPointerException. Has worked in and knows a bit about other languages and architectures. 

### Coin puzzle

Straight to binary. Can you do it in two? Eventually worked to an answer.
