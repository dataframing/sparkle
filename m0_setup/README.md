# Setup
---

## Table of Contents

0. [Keeping things neat](#keeping-things-neat)
1. [Starting from the Bottom](#starting-from-the-bottom)
2. [Anaconda](#anaconda)
3. [Spark](#spark)
4. [Cassandra](#cassandra)
5. [Anaconda (Part II)](#anaconda-(part-ii))
5. [Extras](#extras)

## Keeping things neat

Installing everything below can (and, likely, will) get messy. To avoid polluting your laptop with files upon files, I recommend making a directory in your home directory, and in that directory keeping all things related to Sparkle. This way, when you're done with this tutorial, it's just a matter of moving a folder as opposed to keeping track of separate files. Here's what I'd suggest:

1. Make a repository in your home directory to hold *everything*. The following code will make a directory called `learning-spark` in the home directory.
  - ``mkdir ~/learning-spark``
2. Clone (or "copy") this repository within `learning-spark` so that you have access to the entire thing just in case something happens (like war, or worse, a Trump presidency).
  - ``cd ~/learning-spark``
  - ``git clone https://github.com/dannyfig/sparkle.git``
3. Good to go! Hopefully this'll keep things tidy.

## Starting from the bottom

So let's assume you've just opened your fancy new laptop and it's *completely* clean. **This is by no means what your system** *must* **be**, just our assumption going into it.

To get started, we have to install [Python](https://www.python.org/). To check and see whether you've already got Python installed, open the Spotlight tool (<kbd>Command</kbd> + <kbd>Space</kbd>), type "terminal", then press <kbd>Enter</kbd>. From there, a terminal should pop up. Enter the following command:

`python --version`

Mac OS X 10.8 comes with Python 2.7 pre-installed by Apple. If you don't have python installed, head to the [Python 2.7 download page](https://www.python.org/downloads/release/python-2711/) and download the appropriate installer. 

Once installed (or if you already had Python installed), the following line of output should give you something like (note: `x` can be any number):
 
`Python 2.7.x` or `Python 3.x.x`
 
If for any reason you get something different, make sure to Google your error message and (carefully) try fixing it. For the sake of building Sparkle, we'll be relying on using **Python 2.7 instead of 3**. This is mostly a compatibility thing, and I'll consider porting the code to Python 3 in the future (Spark 2.0.0?).

Next, we want to install `pip`, which is a package manager for installing Python modules. First, check to see if you don't already have pip by entering the following into the terminal:

`pip --version`

You'll either get an error message complaining that your computer doesn't have pip, or you'll get something like:

`pip 8.1.2`

If pip is already installed, skip to [Installing Anaconda](#anaconda). Otherwise, we need to install pip.

The [official pip installation page](https://pip.pypa.io/en/stable/installing/#id8) asks us to securely download their script, `get-pip.py`. We want that script! Let's get it. Make sure you're connected to the internet, then run the following from the terminal:

`cd ~ && curl https://bootstrap.pypa.io/get-pip.py`

**Note: whenever you see a** `#` **sign within the code, that's just my commentary telling you what's going on. Any line starting with a** `#` **on the terminal is ignored by the system.**

At this point, you should see a massive wall of characters – that means it's working. Once it's done, run the `get-pip.py` script by doing as follows:
 
`python get-pip.py`
 
Once that's finished, rerun the `pip --version` command to make sure pip is properly installed. If all's gone well, pip is now installed and will tell you what version it was installed under.

## Anaconda

According to [Anaconda documentation](https://docs.continuum.io/anaconda/index):

>Anaconda is an easy-to-install free package manager, environment manager, Python distribution, and collection of over 720 open source packages offering free community support.

In short: Anaconda is fantastic. Before Anaconda there was chaos in the package management world, and Anaconda showed us the light. Some say that Anaconda rested on the seventh day. Regardless, let's get it.

Head over to the [download page on Continuum's website](https://www.continuum.io/downloads) and scroll down until you see "Anaconda for OS X". Here's where we have a minor fork in the road: if your Python version from earlier was `2.7.x`, you'll obviously download the installer for Python 2.7 (and likewise if you have Python 3.5). Feel free to choose either the graphical or command-line installers — it doesn't really matter. Here's what you do for either:

### Graphical

I don't think this needs much instruction, but:

1. Click the download button, wait for it download.
2. Once it's done, open the download (probably in your 'Downloads' folder.
3. Follow the instructions.
4. ???
5. You're done! Skip the command line installer instructions.

### Command-Line

Cool!

1. Download the command-line installer (save it to your Desktop, if you'd like).
2. Run the following from the terminal (note: we'll assume you downloaded the Python 3 installer, but just change the **3** to a **2** below):
  1. `cd ~`
  2. `mv Desktop/Anaconda3-4.1.0-MacOSX-x86_64.sh .`
  3. `bash Anaconda3-4.1.0-MacOSX-x86_64.sh # 3 -> 2 if applicable`
3. You'll get a few prompts here or there, mostly just type `yes` and you're good to go after a few minutes.

---

At this point, you should be good to go with both Python and Anaconda! To be sure, just run the following and make sure there's no error message:

`conda --version`

Once that's done, you're good to go! Let's get some #bigdata going.

## Spark

According to [Spark documentation](https://spark.apache.org/docs/1.3.0/):

> Apache Spark is a fast and general-purpose cluster computing system. It provides high-level APIs in Java, Scala and Python, and an optimized engine that supports general execution graphs. It also supports a rich set of higher-level tools including Spark SQL for SQL and structured data processing, MLlib for machine learning, GraphX for graph processing, and Spark Streaming.

Spark is pretty cool. Feel free to say so out loud – I won't judge you. Much like Anaconda, we also want this (and we get what we want), so let's get it.

We'll actually be using a slightly older version of Spark, *version 1.3.0*. This is so that I can borrow examples from that "Learning Spark" book I talked about :)

Follow these instructions and we'll be well on our way to messing around with Spark:

1. Visit the [Apache Spark downloads page](http://spark.apache.org/downloads.html)
2. Select the following options on the dropdown:
  - Choose a Spark release: `1.3.0 (Mar 13 2015)`
  - Choose a package type: `Pre-built for Hadoop 2.4`
  - Choose a download type: `Direct Download`
3. Download the Spark binary `spark-1.3.0-bin-hadoop2.4.tgz`

Great! I'll assume you downloaded the file so that it's on your desktop now. Let's properly unzip the file and keep things neat by running the following in the terminal:

```
cd ~
mv Desktop/spark-1.3.0-bin-hadoop2.4.tgz ./learning-spark
cd learning-spark

# Extract files from the spark-1.3...tgz tarball
tar -xf spark-1.3.0-bin-hadoop2.4.tgz
```

After extracting files from the tarball, a directory named `spark-1.3.0-bin-hadoop.2.4` should be created within the `learning-spark` directory. To check this, just run `ls` after the above `tar` command and make sure it's there.

Next, we'll change directories into the spark directory by running `cd spark-1.3.0-bin-hadoop2.4.tgz` and list its contents by running `ls`. You should see a few things:

- *README*: a text file containing useful information on how to get up-and-running with Spark. Feel free to read it if you'd like with `cat README.md`.
- *bin*: a directory containing the *binaries*, or executable files, that are used to use and interact with the Spark ecosystem in numerous ways. We'll be interacting with the binaries when using Scala's shell environments.
- *core*, *streaming*, *python*, ...: directories that contain the source code for major components of the Spark project. We won't really be touching these since they're the backbone of the Spark engine.

In the spirit of keeping your computer clean, feel free to delete the tarball that we downloaded with `rm ~/learning-spark/spark-1.3.0-bin-hadoop2.4.tgz` — we won't be needing that anymore.
## Cassandra

## Extras

[I'm a big fan](http://img.directindustry.com/images_di/photo-g/27102-6753807.jpg) of using aliases on the terminal to make my life easier. Aliases let us set definitions on the terminal that can hold numerous commands and make our lives easier. In action:

```
cd ~
alias home="cd ~ && clear && echo Welcome home"
```

From now on, anytime I enter the `home` alias on the terminal, we'll change into the users directory, clear the terminal screen, and print "Welcome home".

Let's make 

# TODO
- Run pyspark in python interpreter
- note logging messages
- change so that only errors show on start
- install ipython and jupyter
- run pyspark in ipython interpreter
- 