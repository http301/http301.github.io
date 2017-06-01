- 算法
- LeetCode


# Class 1

自我介绍

* LinkedIn，一年，
* 现在也是algorithm & coding面试官
* 刷过很多题，看过大部分市面上的算法书，所以觉得有很多经验和技巧可以和大家分享，少走一些弯路

我的功能

* 讲课：技术:总结&归类 题目；分享经验，技巧
* Q&A：作业问题，一起改简历，如何准备，下一步怎么办
* 最后冲刺：mock interview，申请公司的策略，最后的把关

课堂上一定要提问，如果你不问我不知道你不会
* 没听说过名词
* 某个东西，没听明白

优势就是面对面，快速反馈

---

# Motivation

**Q: What's your motivation?**

* 捷径
 * 技术面试，相对**客观**，会做题就能解决
 * 确确实实的路，很多成功案例，努力就能达成
* Salary
* 成就感
 * direct impact on the real world
* A lot of benefits
 * free food
 * high end equipments
 * gym
 * education reimbursement
 * company culture, open, free, trust

# Mindset

* 不是一条轻松的路，不是只要上课刷题，就能躺着拿offer了
* 长时间，高密度的准备，GRE；
* 一旦度过这个门槛，后面就舒服多了

> 没刷完题不睡觉


# 零基础转CS，如何准备？

**从申请到拿到一个Offer有几步**

* 拿到面试 - 简历
* 通过面试 - 刷题

## 对于转专业的同学来讲，如何拿到Offer

- 专业背景弱，很难拿到面试
- 对面试流程，标准不熟悉，不知道bar在哪里
- 有太多需要准备，不知道如何下手
- 刷了一段时间题，不知道自己是否准备好了

思路：`三击必杀`

`简历不用完美，看起来professional就够了`
`不需要太多面试，在面试前准备好自己，一旦有面试机会，就能拿下`

## 如何准备面试

### 技术面试的通常流程

Software Engineer

* 1～2轮电话面试：背景，Coding
* Onsite:
 * 两轮或多轮Coding
 * 系统设计,OO design
 * Communication： resume, experiences, personality

### Communication

* 大思路：提前准备好
* 自我介绍
* 项目经历，吃透，用英语写出来，背下来:简洁，逻辑清晰
* 做题时的英文，模版，就那么几句

### 系统设计

* 涉及的知识点太多了，系统的学习看不过来
* bar很低
* 大思路
 * 遇到了，就搞明白
 * 注重high-level理解，不要花太多精力研究细节，没有时间
 * 多看这方面的面经

### Coding Interview

#### 一道典型的面试题

> Reverse digits of an integer.

Example1: x = 123, return 321
Example2: x = -123, return -321

1.思路 － 解法，最优解？
2.Time complexity, space complexity
3.Corner cases:
 * 负数怎么处理
 * Overflow怎么处理

```java
public int reverse(int x)
{
    int result = 0;

    while (x != 0)
    {
        int tail = x % 10;
        int newResult = result * 10 + tail;
        if ((newResult - tail) / 10 != result)
        { return 0; }
        result = newResult;
        x = x / 10;
    }

    return result;
}
```


#### What they look for from the perspective of interviewers?

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


#### 技术面试的流程模版：

当你拿到一个具体问题时，可以按照如下流程回答：
1. 明确题意：通过与面试官交流明确需要解答的问题。这部分主要为了让自己放松心态，并且给面试官留下你具有良好团队意识和交流能力的印象。

2. 描述大体思路：描述你打算用什么算法，什么数据结构。主要是为了让面试官了解你的思维过程，如果你给出的解答与他想要的答案偏差太多，可以及时纠正。同时，描述思路也给了你自己思考的机会。

3. 实现算法：先处理边界条件。对于重要的算法模块，加一些注释或者与面试官进行交流。目的是让面试官始终了解你在做什么，算法框架是什么。

4. 跑一个test：用一个test case走一遍你写的程序。目的在于和面试官一起确保你的算法是有效的，可以在过程中及时发现并纠正自己的错误。同时，给面试官留下你有写unit test习惯的良好印象。

5. 描述算法复杂度，回答面试官的问题。

---

#### DEBUG流程：
1. 通过TEST CASE定位BUG所在位置
2. 不要立即修改代码，重新梳理逻辑。因为很有可能还有其他BUG。
3. 走完所有逻辑之后，心里有数怎么改了，再动手开始改
4. 用TEST CASE再走一次新的代码。
5. 在整个过程中，不停的告诉面试官你在干嘛(在不影响正常写程序的情况下)
这样，成功排解BUG，不但不会减分，还会因为你优秀的DEBUG能力和与此同时展现出来的沟通能力而加分。

---

#### 怎么准备

> 不要一味地为了刷题而刷题

##### 问题

> 太多题了，LC->500, CC150->150~200，etc.
> 看完答案，过两天又忘了
> 思路看不懂，花太多时间在网上找最优解

* 思路，最重要的是思路，举一反三
* 总结Coding题中常用的tricks
* 如何把code写的clean，simple，readable

> 最后的苦功夫还是刷题，尤其当你记不住这么多东西的情况下
> Practice makes the perfect



# JAVA语言怎么入门？



## 如何准备简历

### Recruiter 看什么

> look like a professional

- 相关实习，工作经历
- 学校＋专业
- Project Experiences
- Portfolio: github

### 如何准备简历

- **Project Experiences**
 - **大思路**：时间有限，找一些需要时间少，出活快的东西做
 - 网上公开课的作业，边学边想如何能把这个东西写到简历里
 - 做一个个人网站
 - 网上有现成教程和代码的project

- **Portfolio: github**
 - 把刷过的题放上去
 - 做过的作业放上去
 - 看过的代码，加星，收藏起来
 - 找一些简单的bug改改

### 如何写简历

[如何准备杀手级简历]()




# 


## Tools
* Oneline Ide: https://www.compilejava.net/
* 