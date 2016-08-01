# Sparkle
---

## Table of Contents

0. [Summary](#summary)
1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [FAQ](#faq)
4. [Contributing](#contributing)
5. [Contact](#contact)
6. [License](LICENSE)

## Summary

Sparkle is an all-in-one, completely open-source tutorial for learning and developing the underlying architecture for a matchmaking social network using prominent data {science | engineering} and web tools. Designed for beginners, Sparkle provides a series of detailed tutorials, modules, and examples that will introduce you to and develop your proficiency with Python, PySpark, SparkSQL, and Cassandra[0]. By the end of the modules, you'll have:
 
 * Installed and configured (if you hadn't already): [Python](https://www.python.org/), [Spark](http://spark.apache.org/), and [Cassandra](http://cassandra.apache.org/)[0].
 * Learned about the benefits of the Spark computational engine and Cassandra as a database.
 * Written your own Spark scripts for lightning-fast data analysis and data ingestion.
 * Implemented a solid back-end for a morally-bankrupt matchmaking social network.
 
## Introduction

At its core, Sparkle is aimed at people who know a few programming basics and are interested in #bigdata, but find the material daunting to learn (indeed, this project was born out of my frustration with the lack of dead-simple, straight-forward tutorials). Let's cover what you should probably know how to do before following the examples:

* **Python**: you should have a decent understanding of Python, including introductory material (loops, conditionals, functions), some intermediary concepts (recursion, data structures), and *maybe* peek at some harder stuff (MapReduce, functional programming). If you don't know the last stuff, don't worry: neither do I :)
    * That said, there are great resources on the internet for learning Python (like [codecademy](https://www.codecademy.com/learn/python) and [Learn Python the Hard Way](http://learnpythonthehardway.org/book/)) and a great community over at [/r/LearnProgramming](https://reddit.com/r/LearnProgramming), for example.
* **Terminal**: you should know the basics of using the terminal. This includes stuff like `ls`, `cd`, `mkdir`, `alias`, and maybe even some `vim` for quick and easy text editing.
* **SQL**: you might want to know *some* SQL (pronounced "sequel") so that when we start with Cassandra's own query language (CQL), it isn't too alien.
    *  Again, there are great resources for learning SQL on the internet for free. Check out [w3schools](http://www.w3schools.com/sql/), [SQLCourse](http://www.sqlcourse.com/), and my personal favorite, [SQL Bolt](http://sqlbolt.com/).

If you don't know some of the above you might find the material a bit tougher, but hopefully still follow-able. Again, this series of tutorials and modules are designed with beginners in mind so if you're a beginner and don't understand something, let us know!

Most of the material for each module will be housed in a `README.md` file, so if you `git clone` this repository you'll be able to learn Spark both under and way, way above  ground.

## Getting Started

You're interested in learning more about Spark and how to add fancy skills to your resume? Maybe just the former (or the latter)? **Sounds good!**

If you'd rather bookmark this for later, feel free to star this repository (at the top of this screen) or clone the entire thing to read later (on a bus, train, plane, etc.). Just run the following from your terminal:

`git clone https://github.com/dannyfig/sparkle.git`

If you'd rather start now, head over to the folder at the top of this page titled `m0_setup` (that's module 0, "setup") to get details on what you'll need to download and install to get started. Don't worry, we'll be right there with you every step of dependency-hell.

## FAQ

**How long will this take?**

There's no time limit! Take as long as you'd like (I know I sure will).

**I can't install *package_xyz*. Help?**

I'd suggest hitting up your friend (and mine), Google. Something like: 

`<package_xyz> <error message you're getting> <your operating system>` 

should do the trick. If the issue persists and you can't find a solution, check out the issues (use the nifty search bar!) to make sure it hasn't been asked (and answered) already, *then* open an issue.

**Who're you?**

~~Mostly nobody~~ I'm Danny, a junior at NYU studying computer science. I'm passionate about data science, software engineering, and everything in between. Learning Spark on my own (via [Learning Spark: Lightning Fast Data Analysis](https://www.amazon.com/Learning-Spark-Lightning-Fast-Data-Analysis/dp/1449358624)) was annoying and riddled with error messages (and, probably, my fault), which I know can be daunting for beginners (of which I consider myself). I thought I'd turn that frustration into an opportunity to help lower the barrier for learning Spark.

That said, this is **forever a work-in-progress**. I'll be writing this as I'm learning Spark/Cassandra as well, and I'm sure many places will be rough around the edges. Feel free to contribute if you'd like!

**What's the point?** (Nobody has really asked this question, but I think it's important)

Throughout college I've been able to learn about tons of cool companies and philosophies that encourage open learning and reducing the complexity of getting people on the same page. Some notable examples are:

* [Basecamp](https://basecamp.com) and how they're changing what it means to work together
* The Airbnb Data Science team's [efforts to scale knowledge](https://medium.com/airbnb-engineering/scaling-knowledge-at-airbnb-875d73eff091#.eyeq3ayze)
* KhanAcademy's entire premise, which is to to [provide a free, world‑class education for anyone, anywhere](https://www.khanacademy.org/about).

As a summer data science intern at Basecamp, I got to experience what it meant for people to put people first. That's exactly how this entire idea started: take something hard I've struggled with, make it accessible for other people. Simple as that.

### Contributing
---
I'm an open-source noob in every sense of the phrase, but feel free to follow GitHub's best practices (open an issue, make a branch, submit a PR) if you'd like! We'll add your name to a contributors list...somewhere.

---
---
### Contact
Feel free to contact me through [email](<mailto:danny.vilela@nyu.edu>) or on [Twitter](https://twitter.com/danny_figgy). Thanks!

### LICENSE
Check out `LICENSE`

### TODO
[0] Front end (Ruby on Rails + HTML/CSS) mention?

---
---