## Setup

### Table of Contents

0. [Starting from the Bottom](#starting-from-the-bottom)
1. [Anaconda](#anaconda)
2. [Spark](#spark)
3. [Cassandra](#cassandra)

### Starting from the bottom
---

So let's assume you've just opened your fancy new laptop and it's *completely* clean. This is by no means what your system *must* be, just our assumption going into it.

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

At this point, you should see a massive wall of characters – that means it's working. Once it's done, run the `get-pip.py` script by doing as follows:
 
`python get-pip.py`
 
Once that's finished, rerun the `pip --version` command to make sure pip is properly installed. If all's gone well, pip is now installed and will tell you what version it was installed under.

### Anaconda
---


