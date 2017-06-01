---
title: Behavior Questions
date: 2015-02-06 16:39:28
tags:
---

* TOC
{:toc}

## Starting

### Tell me about yourself

**Tips**: *Start with the present and tell why you are well qualified for the position.*
**Answer**:
My name is Yazhou, or Asia. I finished my bachelor degree of software engineering in Beijing University of Technology, and got my master degree of CS from SUNY at Buffalo this Feb,
Before I came to United States,  I had an 3-month internship in Honeywell Solution Lab,  I developed a small web application of safety management just for demo use.
I also had worked about 7 months in a software consulting company in Beijing China. During that time, my teammates and I developed a recommender system for CNTV.com. My job was to implement the  video recommendation related backend services.
(Recently, I am working on a project with a professor of Purdue University about influence propagation of tweets and retweets in Twitter.)


## Common Behavior Questions

### What are your greatest weaknesses?

**Traps**: *Beware this is an "eliminator" question, designed to shorten the candidate list. Any admission of a weakness or fault will earn you an "A" for honesty, but an "F" for the interview.*
**Tips**: *Disguise strength as a weakness*.
**Answer**:
I sometimes push myself too hard, especially when I am determined to finish something. It might be not good in the long term. E.g. When I was writing the program of the database course project. There was a period that I only spend 5 hours a day for sleeping in a week. In short term, it might help me achieve a good score,  but in the long term, it hurts  my efficiency on programming as well as my health.

### Why should I hire you?

**Answer**:
As a fresh graduate student, I have a good understanding of computer science, as a coder, I have practiced 1000 questions or more during my recent 2 years, which built me a solid coding skill. In addition to that, I have some work experience in backend, and I know *XXX* has lots of backend services, I think that's where I could make a significant contribution.


### Where do you see yourself five years from now?

**Traps**: *One-reason interviewers ask this question is to see if you're settling for this position, using it merely as a stopover until something better comes along. Or they could be trying to gauge your level of ambition.*
**Tips:** *Reassure your interviewer that you're looking to make a long-term commitment...**that this position entails exactly what you're looking to do and what you do extremely well**. As for your future, you believe that if you perform each job at hand with excellence, future opportunities will take care of themselves.*
**Answer**:
I might see myself as a senior engineer or a team lead in XXX company working on a exiting project. I believe to stay grounded, focusing on the job I am doing currently, try my best to perfect it, and future will take care of itself.


## Status Questions

### What position do you want to do?


### How much salary do you prefer?

I would prefer average salary.

### What's the progress of your interviews? (Any other interviews, offers?)

I just started, applied several companies, I am currently interviewing with XXX as well.

### Why do you want to leave (or did you leave) your present job?

.....
(Instead of allowing the interviewer’s question to focus your response on why you want to leave or have left an employer, refocus your response on why want to move to the prospective employer. Consider something like, “*I just don’t get enough challenges at XYZ Company. I am eager to take on more challenges, and that I believe I will find with your company. I want an opportunity to apply my skill where I can really make a difference in the future of the company.*” Not only does this response transform a gripe into a laudable, positive motive, it adds the dimension of “what’s in it for the employer.”)


---

## Companies

### What do you know about TheLadders?

TheLadders provides a relatively high-end job-matching/job-searching services, so means it helps people finding jobs they want,  especially for experienced professionals, and also help employers finding the right people to hire.
It has 8 million users and more than 95,000 jobs, and there are three platforms: website, the mobile app on Android and iOS. I figured it must have a lot of data and requests coming in and out everyday, so it must have a fast and robust backend supports them. And I think that's where I could make a significant contribution.

**Pros**: the UI is simple and easy to use, I tried searching for jobs, what impressed me is that in the list of searching results, each job has summary that shows the salary and required years of experience, that's very neat.

**Cons**: It seems to me that It's more like a high-end job searching/matching tool, it's good for people has years of experience, not quite fit for new grads.

---

### Zenefits

**What do you know about Zenefits?**
Zenefits is a fast growing technology company in San Francisco which provides free online services of human resource management, like health insurance, pay roll, 401k etc. It makes money from insurance company as a broker and provides an one-stop easy and free HR service. I watched the video of Parker's presentation at the disruptive Startup Battlefield, it was very impressive.

**Why Zenefits?**
Zenefits is a super fast growing technology company. The number of customers grows from 0 to 10k in 2 years which is amazing, so I guess it must have a lot of data to deal with and it must be challenging for software engineers to build softwares around it.  And I love challenges.

The position I applied is Data Engineer, which need people familiar with database and SQL and has excellent coding skill.  AndI am familiar with relational database, especially internals since I implemented one back in school last year, besides I have practiced hundreds of coding question to improve my coding skill as you can see in my github, so I believe I can make a significant contribution to Zenefits.


### Connectifier

Connectifier is a platform for recruiting, it improves recruiting by helping recruiters target the right candidates and connect to them more effectively.


### Booking.com

Booking.com is a global online booking website for booking hotels, flights, renting cars.

**Motivation**
Booking.com is a fast growing company which deals with Terabytes of data everyday, data like booking information, transactions of hotels, flights, cars, and users' comments of the experience, etc.
I personally have used booking.com several times. It's very helpful to me for finding good hotel deals. Compare to its competitor Expedia,  it has more options for hotels, and moreover, it sometimes has a even lower price than Expedia.
As for the position, I do have related backend development experiences, besides,  I have been practicing my coding skill for a year which made me a much better coder than I was before.
So I believe I can make a significant contribution to booking.com.

**Insights**
In a few of the hotels, some of the pictures they posted are photoshoped, or its real condition does not look like the condition in the pictures, although it's just a very few of them, it could mislead customers, could give customers an illusion of how good the place is.

To improve it, we can add a report function for the users, so that users can report this kind of scenarios.
And for booking.com, if we received many of such reports, we could take some kind of actions to punish the hotel, like warning the hotel to change the pictures, or lower its recommendation level, etc

And recently, personal


## Behavior Questions - STAR

**Situation**: the general situation about the question.
**Task**: the task you are going to complete.
**Action**: what you did, how you did it.
**Result**: the result, compact after you finish the task.

---

## Freeborders

### General Situation

Freeborders is software consulting company, the project we undertook was a data mining platform.
The system has three main parts,
the first is the infrastructure for data mining(which has a cluster of HBase for data warehousing, and a mongoDB for low latency applications),
and the second is the backend services of video recommendation(which used Netty framework as server, and socket + json for communication),
the last part is the front-end including a website for administration and APIs for outside.

### My Job

My job was to develop the backed services of recommendation and two recommendation algorithms.

### Collaborative Filtering Algorithms:

I implemented two collaborative filtering recommendation algorithms, one is user-based, the other is item-based. They are pretty similar, the ideas of them are both to find the k-nearest-neighbors.

**The basic ideas**
For users-based, we are going to find the top-k similar users who have the same taste for every user, and do the recommendation based on the-k users..

For item-based, we are going to find the top-k similar items for every item, and then do recommendation based  on it.

-->

So the next question is how to calculate the similarity between users/items?

-->

**How to calculate the similarity?**
Let's take the item-based as an example.
Out goal is to calculate all the similarities between every two videos by their user activities.
More specifically, we can think of each video as a vector of users who watched it, in this case, we can calculate the similarity by calculating the distance of two vectors.
And then we just need to store the similarity information in an big matrix,
then we just find the top-k similar videos and recommend to users.

### Challenge:

The most difficult part is I found out is how to store and calculate the big matrix efficiently?
Because it's a huge matrix, it can't be loaded in memory.
When we updating the matrix, we had to load it partially, and update it partially. This turned out to be very time-consuming because there are lots of IO operations occurred. So what we did is keep caching the updated data until the partial matrix is big enough, then do a batch IO operation. This approach boosted the calculation process a lot.

And also, I found out it's a symmetric matrix, so I cut it in half when store it in database which saved half of the space.

And besides, I used a third-party collection library called Trove that supports primitive type instead of the original Java collection, it boost both the memory usage and running time of the program a little bit.

After these optimizations, it became a lot more faster.

### User-based vs Item-based

**User-based**
UserCF is easy to recommend the popular items among a group of people have the same taste.

**Pros**
Good for applications that number of users won't change too much, but the number of items changes rapidly. E.g. News Recommendation

**Cons**
1. With the number of users grows, the computation cost grows quadratically.
2. There is no direct explanation for such a recommendation result.
3. Low real time recommendation,  the result may not change after the user made a new action.
4. Has the problem of cold start, one user needs more actions in order to do recommendation

**Item-based**
ItemCF is more like to recommend items based  on the items that the user has visited before, it focuses on one's personal browsing history.

**Pros**
1. Good for applications that the number of items is far less than the number of users. E.g. E-commerce, Books, Movies recommendation.
2. It has a direct explanation for the recommendation result.
3. The result may change immediately after the user made a new action.
4. Cold start won't be a big problem, once the user made a action, we can do recommendation.
5. It can have a better coverage and diversity rate than UserCF because it recommends based on the user history.

**Cons**
Not good for applications that the number of items changes rapidly.

---
**To be added**
Inverted table,  Firstly, when calculating the matrix, we used a inverted table to calculate the matrix instead of calculating vectors directly,
Take the user-based as an example, when we calculating the matrix, we need table of users’ browsing history, we view each row as a vector, and calculate the similarity, which cost n square time.
However, we do it in a reverse way, we calculate a items browsed history table, we calculate user similarity.

Profiling



---

## Honeywell

### General

It's an individual project, my supervisor wanted me to write a web application that supports safety management on Google Map.
The idea of this program is to make life easier for people like building administrators.
The traditional safety management is someone sitting in a room and watch and check those all kinds monitors and sensors, now we want to integrate the information of alarms, cameras and censors into a Google Map, so that we can visualize all the information on one platform, people don't have to stay in a room to watch it, and we can use computers, smart phones to check everything.

### My Job

My job is to implement a prototype for just demo.
The basic functionality is create, save or load those information of alarm, censors, monitors.  I used one single web page as a User Interface which embed with a Google Map, and using ajax to communicate with backend services which was written in C#, and store information in SQLServer.

**Describe how it works to the create a camera on Google Map:**
we can set up an camera on Google Map by creating a camera-like marker, with a panel that you need fill out for the information of this camera. And whenever you want to check the camera, you can click the marker, it will pop up a panel that shows the status of the camera and also it will play a video to simulate the streaming data of the camera.

### Challenge

Because I was a senior student who didn't have much experience on web development, so I had to learn everything myself. At the same time, there was a timeline that I had to finish it in three month.
So the challenge was how to balance my time between finishing my job and learning some new stuff, to make it cooler.
Decompose my project to several sub-problems, prioritize them and make schedule when to finish what.
Communicate with my supervisor, let him know my progress.
If he thinks is good progress, then I will save some time for studying other things.


---

## Twitter Data Crawler

### General Situation

I am working with a professor on a project of researching the influence propagation of tweets and retweets. We want to know how the influence propagates between tweets and retweets, for example CNN posted a tweet, and how many people retweeted it, and how many people retweeted their retweets, and so on and so on.

### My Job

My job is to crawl all the tweets and their corresponding retweets. For each tweet, it propagated like a tree structure, and I am trying to restore the tree for each original tweet.

### Challenge

The challenge is how to make the crawling faster. Because twitter APIs has a rate limit for each API, we can only a certain API certain times in a time period like 15 minutes, otherwise, we have to wait.
My solution for now is creating multiple accounts, and then using them simultaneously, so that we can double the throughput.

---

## Simple Relational Database Engine

### General Situation

It's my database course project. our goal was to implement a simple relational database engine that can parse and execute SQL which included most of the statements like insert/update/delete/select etc.

### My Job

**It has three check points through the entire semester:**
The first is to build the skeleton of the program, make the program to be able to evaluate some simple queries.
The second is to test its capability of out-of-core processing, that is to say to fetch a relatively big dataset given only limited memory. In this check point, we have to implement the external version of some of the relational operators.
The third check point is to integrate index, and also make the program to support all kinds of queries like nested select, complex joins etc.

**It has three parts:**
The first part is a SQL Parser, which parse SQL to an expression object that contains all the parsed information.
The second part is the SQL engine that create relation algebra operators based on the expression object, and connects them to form a tree structured logical plan of execution.
The third part is a set of implementations of relational algebra operators like selection, projection, hash-join, etc.

**The execution process is like:**
first parsing the SQL String to an expression object,
based on the expression, we create the related relational operators and connect them to form a tree structured logical plan,
finally we execute from the root operator, use a while loop, to get one tuple at a time, until all the tuples are read and processed.

### Challenge

The challenge was how to implement the out-of-core join operation efficiently.
I tried several algorithms, my naive implementation was an external sort-merge join, which was very slow, so then I built an index and used an index-join. I thought it should be the fastest solution, because it's the typical solution for a join operation in a commercial database, however it turned out to be slow as well.
So I looked into the dataset, found out that most of the tables that joined together have a large intersection, so when we do the index join, it makes the disk head jump around, so that's why it was slow.
Finally, I changed it to the external hash join, which fully make use of the property of sequential read and write,  and turned out to be the fastest solution.

### Query Rewrite

**Some rewrites are always good ideas:**
> $\pi_a(\sigma_c(R)) \equiv \sigma_c(\pi_a(R))$
> Selection commutes with Projection (but only if attribute set a and condition c are compatible)
> a must include all columns referenced by c
>

- Always push down selection, projection to leaf node.
- When do Join operation, always use the smaller table as HashTable.
- When there are multiple joins,
 - Rearrange them to a left-deep join, so that every right child join input is always a table.
 - When rearranging, try to do the join that has the smaller result size first.
 - Pipelining joins, a pipelined operator is one that does not block.
- When the index column is involved, use a index scan instead of a full table scan.

**Some are depend on the statistics** --> Cost-estimation based optimization
