---

title: Interview Speaking Template
date: 2015-06-12 20:19:28
tags:
published: false

---

* TOC
{:toc}

## Common behavior questions

- Tell me about yourself?

- What do you know about LinkedIn?

- What did you do in this Job?

- What is the most challenging part in this project?

- How did you accomplish it?

- If you can do it again from scratch, what parts that you can do better?

- Where do you see yourself five years from now?


## What they look for from the perspective of interviewers?

1. Analytical ability - Intelligence
2. Understanding of CS
	- Not only the definition, but also the trade-off
3. Coding Skill:
	- correct,  simple, clear code (so called good clean code)
	 - correct, no bugs, work as expected, **whenever there is a bug/mistake made, think it through (why it happens) before fixing it**.
	 - simple, straight forward logic, no complex design, KISS
	 - clear, easy to understand, clear intent, good naming, good abstraction
4. Personal compatibility
	-  Personality, arrogant? nice? Do I want to work with you?
     - Smile  
	 -  Aways be positive, be interested in new approaches.
	 -  Whenever an interviewer suggest sth, do not say sth negative.
	-  Communication skill
		-  walk through your idea with your interviewer
		-  show how you think to solve the problem

## Tips

- Talking your way through problems is great, but it's also okay to pause and think when asked a question.
- Write pseudocode before writing your real code,.
- Use some auxiliary function instead of your detailed implementation while in writing pseudocode or actual code,  it makes your code clean and readable.
- When coding, it's typically useful to have  an example of the data structure on the board to refer to.
- Write down your cases/thoughts, it will be harder to remember them otherwise.
- Listing "known facts" can be useful. For example, you always want to include a positive number.
- Think about your "known facts" and what the conclusions you must draw from them are.
- If you feel your interviewer has been "leading" you too much, you should use those pauses to regain control.
- How do you regain control? By doing stuff! Write down your approach. Walk through an example. Talk about your thoughts.
- Listen for pointed questions. If your Interviewer says "are you sure?", it's a good indication that you've made a mistake.
- Check for your cases being mutually exclusive and complete. They probably should be!
- When writing code for an interview, write as formally as possible - method, declarations, return types, etc.
- Getting confused while coding? Try pulling things out into other methods. E.g, use a method leftMost(Node n). This will make your coding easier and show that you care about writing maintainable, easy to read code.
- In longer problems, it may be useful to stop part way through coding to test what you've written.
- If there's a problem that you will deal with later, say so. Don't make your interviewer wonder or ask.
- If your interviewer keeps poking you about an issue, you need to deal with it immediately.
- When fixing a bug, think through the cause and solution very thoroughly (Have you truly understand the problem?). Making a change can have unexpected consequences.
- Remember to always check that you've handled your terminating cases.
- Always, always test your code.  Test at your beginning, test at the end.

## Templates

### First meet

- Pleasure to meet you
- I really appreciate for your time to interview me today.

### Ask for clarification

- I don't remember that *sth* is ..... `(asking for clarify implicitly)`
- How is the *sth* presented to us?
- How is the *sth* represented?
- Who is using it?
- What can I expect of the input?
- What can you expect of the output?
- Is it OK to assume ... Can we assume that ...
- Do you want me to *do sth* ...
- Do I have to *do sth*... `(E.g. processing the result)`

### Describe an algorithm

#### Starting

- My intuition is .... (How I am gonna do it?)
- I am gonna start with an example to see find I can find an algorithm.
- I didn't think it through, **I will start with an example to see how to work it out.**
- **I am gonna walk through one or two test cases first.** `(First thing before writing code, must do!)`

#### Thinking / Building ideas

- I am trying to think about a way that ....
- I am thinking maybe we can *do sth ...*
- I probably need some sort of pre-processing step that collecting information of .... so that I could narrow down the possible words.
- There is a couple of approaches, the naive way to do it is ..., the most straightforward one is ...., a easy one is ....,  the second one could be ...., the last one could be .....

#### Explaining the algorithm

- I will first *do sth*, and *do sth,* then *do sth,* at last *do sth*.
- go through the array with two pointers i, j,  i starts at the beginning, j starts at the end of the array, and walk towards each other.
- When the total counter hits zero, we can stop iterating, so it can save a little time, a partial iteration, a short circuit.
- We will have a HashMap, from String being the anagram to Set<String> being set of words, call it *XXX*
- What it will do is ....
- We are gonna see if the key is in the map, if so ..., if not ....
- If  *condition is true/ sth happens* `(Expression of a condition)` in which case we would *do sth*. `(在这种情况下做...)`
- If it contains the word, we will get *sth*, if not we will ....
- If ... , we might want to do/ not want to do .... Else, we might want to *do sth*
- And now we are sure that *XXX* `(E.g. that we have the HashSet)`.
- We would only want to add/delete it in this case.

#### Describe a function or class

- We would want `a name of function` to *do sth*.
- It would take *sth,  sth* ... (a String word, a String array dict). `(Define input arguments)`
- What it will do is ....

#### Describe a data structure

- we could have a class called *XXX* that contains ...
- so that maybe it would allow users to do *sth* ...

### Describe pros and cons, trade-off

- What the other algorithms / data structures are we comparing to?
- What the other algorithms / data structures would be?
- The advantages are ... ; the downside/disadvantage is ...
- One advantage could be ....
- In this case, it's best off *doing sth*  (在这种情况下，最好是做....)
- *sth* .... could be one major drawback/downside/disadvantage.
- I think those are the major pros and cons of *doing sth*
- Clarity,  it's more clear for people to read the code
- Simple, easy to implement
- Time,  good/poor cache performance (linked-list), etc.
- Space, Light-weight,  overhead of next pointers, etc.
- Overall, this approach is more efficient in time, but less efficient in space.
- Ultimately, it's a choice / trade-off between being really compact in space and writing  more general algorithms.

### Describe a bug

- The problem was that ....
- But here what I was doing is .... which didn't consider the *XXX* case.
- We could *do sth* to fix it

### Common confirm response to interviewer

- Confirm: OK, sure, all-right,  no problem, cool, great, awesome
- Agree: yes, right, totally agree
- Compliment: that's really neat, cool, that's really awesome.

---

### Common Questions

#### Why do you want to work for *XXX*?

I love computer since I was a kid.
I have been using *XXX* product personally for several years.
I think they really take an innovative approach to data analysis, `(connect to yourself)` and recently I worked on a project for I got to apply AI to data analysis. `(back to the company, that's why you should hired me)` So I think I could make a significant contribution there.

#### What is the hardest part of your project?


---

### Questions for asking interviewer

- I'm curious what project you and your team is working on?
- If you find an interesting project you want to work on or you feel like there is an important contribution you could make to it, is it flexible to switch team or spend part of your time working on?
- At the end: sounds like a good place.
