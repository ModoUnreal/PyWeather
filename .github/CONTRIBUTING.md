# Contributing to PyWeather

**Warning: This document is undergoing renovation. Please excuse our apperance.**

Hey, thanks for your interest in contributing to PyWeather. If you don't mind taking a few minutes of your day to read this, you'll get the run-down on how things work.

# A quick blurb about PyWeather & contributing
PyWeather has been the result of thousands of hours of worked poured in by people who want to help PyWeather be the best it can be. I apprecipate every single person who reports an issue, makes a pull request, and in general helps PyWeather in any shape or form.

Contrary to popular belief, you don't need to know how to code Python to contribute to PyWeather. Reporting bugs is tremendously helpful in contributing to PyWeather, or even making a pull request with one line of code helps out PyWeather. 

When contributing to PyWeather, start small. Reporting bugs and issues, OS compatibility reports, or even suggesting enhancements is a great way to get started in contributing to PyWeather. If you feel more comfortable reading code and making pull requests, you can without a doubt code in a small feature in PyWeather that's relevant, or you can quickly fix a bug you found. If you feel really comfortable, try coding in a larger feature. Please make sure to contact me first, however.

Please note that contributing is optional, you don't need to finish something you start, and if you don't want to work on a feature or a particular part of a feature that's completely fine. However, it's recommended that you work with me on issues that I spot in your code.
# Contacting me
If you need to ask me any questions about PyWeather without using GitHub, the best place to do so is on Reddit. I'll usually respond within 48 hours, since I get a notification on my phone whenever I get new Reddit mail.

My reddit username is `therealo355`. I have about 3100 karma if that helps to verify my account.

If you'd rather do email, you can email the PyWeather project email at `pyweather <at> owenthe <dot> ninja`. I usually don't respond as quickly to that email, so a response may take up to a few weeks. 

# Code of Conduct
When contributing to PyWeather, please make sure to follow the code of conduct, available here: https://github.com/o355/PyWeather/blob/master/CODE_OF_CONDUCT.md

# Bug reports
An easy, yet substantial way to contribute to PyWeather is in the form of bug reports. When you create an issue, you'll see an issue template, and this is the general format on how issues are created and formatted. This document will expand on what should ideally be in a report.

Just note, if at any time you are confused about if you should report an issue or not, just report the issue. I'd much rather have you report the issue and for me to fix a potential bug, versus not knowing about it.

## Doing the to-do list in the issue template
It's really important to run down this list to save your time, and my time from unnecessary reports. This to-do list also includes steps to help your report be the best it can be. In summary:
* Don't report known issues (check the Wiki page)
* Make sure your copy of PyWeather is up-to-date
* Make sure PyWeather is set up correctly

## Reporting indev code
Reporting indev code is ok, under certain circumstances. As mentioned in the issue template, you'll not want to report config errors. At every PyWeather QA, this is automatically tested about 30x on 6 platforms. However, if PyWeather is close to release, and you find a config bug, you'll want to report a config error.

In addition, please don't make a bug report on a feature that's incomplete. However, feel free to report bugs on complete features.

## Necessary things for a report
When making a report, you'll want a full traceback (if applicable), System information, a detailed description, and some other extra information. Below I'll expand on what necessary things are needed for a report.

## A full traceback
A full traceback looks something like this:
```
Traceback (most recent call last):
  File "<stdin">, line 1, in <module>
ValueError: could not convert string to float: 'hello'
```
A traceback does not look like this:
```
Some horrible thing occurred that prevented PyWeather from loading!
I can't remember the actual error messages in PyWeather and I'm too lazy to reference one.
Press enter to exit.
```

You'll want a full traceback in your error report. In PyWeather, you'll deal with 2 types of tracebacks. Catched errors at a potential point of failure, or a random traceback that randomly exits PyWeather.

For catched errors, a traceback will be outputted, given you turn on tracebacks in the config file. Turning on tracebacks can be done in the setup script, or by making the `tracebacks` option in the `[TRACEBACKS]` section in the config file `True`.

It's important to know that you shouldn't report *some* catched errors. As an example...
* Reporting the geocoder rate limit error - Don't report this
* Reporting a config error when you've properly configured your config - Report this
* Reporting missing data for Wunderground at your location (and it's caught with a message that's similar to "no data") - Don't report this
* Reporting odd data without any message of bad data - Report this

If you also enable verbosity, please don't report non-critical errors. Most of them are due to bad conversions of data, and that actually helps to catch bad data.

However, for random tracebacks, report these! As soon as your PyWeather randomly quits, report the traceback. This is easy if you launch PyWeather in a terminal, but tricky if you double-click PyWeather. 

If you end up double-clicking to launch PyWeather, you'll want to immediately run PyWeather in a terminal and attempt to get the traceback. Here's how you can do it on certain platforms:
* OS X - Launch `Terminal`. Type in `~/pyweatherdirectory/`, where `pyweatherdirectory` is. Then type in `python3 pyweather.py`.
* Windows - Launch explorer and go into the folder in which PyWeather is stored. Click file in the top left, Open in Command Prompt (If you have Windows 10 1703 or newer it's PowerShell), and then type in `python pyweather.py`
* Linux - You know what to do

Do exactly what you did to produce the traceback and put it in your issue. You'll want to make sure you save this traceback as you'll need it later.

## System Information
In a report, you'll want what OS you're on, and the Python version you have.

To get the version you have, remember what version is installed on your box, or enter `python3` (sometimes `python` for python 3) into a terminal, and put down the Python version you have. Examples:

* `Python 3` - Doesn't help. PyWeather runs on Python 3.
* `Python 3.6` - Good, but having a specific version is better.
* `Python 3.6.3` - Great! That's what I need.

Please note: If you're running a Python version that ends in `.0`, please report your Python version as `3.x.0`.

For system information, make sure you give me what you're computer is running on. Examples:

* `my computer` - It really doesn't help
* `Windows` or `OS X` - Basic information, but it can be better.
* `Windows 10` or `Ubuntu 16.04` - Good. This type of info can be enough in 99% of cases
* `Ubuntu 16.04.4 LTS with kernel (version)` or `Windows 10 1709` - Plenty of system information!

Also listing your hardware information (device type & CPU are the most helpful) can help with device-specific bugs.

## A description
Having a description is quite useful for an issue. A good description generally checks off these boxes:
* Describes the issue with a good amount of detail
* Describes the steps (in a detailed way) to produce the bug
* A full traceback
* Describes the location where it happened, what time it happened, etc.

### Your privacy when reporting issues
As a general rule of thumb, when reporting location-based bugs you should **never** put an exact address in the issue. Always attempt to generalize the location.

Generalization generally means taking this information: `123 5th Avenue, New York, NY`, and shortening it down to `New York, NY`.

If the issue you're reporting only occurs at a specific address, please send the report over reddit mail. For confidentiality, after 48 hours from first seeing an issue of this type, I'll delete the message from my reddit inbox. I'll send back a screenshot of my reddit inbox without the message once those 48 hours are up.

To iterate on what I said about an optimal description above, here's an example issue report. In this example, I'm having an issue with PyWeather crashing on boot when entering in a location.

```
When I launch PyWeather and enter in the location "New York, NY", PyWeather crashes after a few seconds. This only occurs at 12:00am, but it occurs every night. To reproduce this step, at 12:00am every night, enter in "New York, NY", and PyWeather crashes.

This is the traceback that occurs when this happens:
Traceback (most recent call last):
  File "<pyweather.py">, line 2000, in <module>
KeyError: whatever the error message for a non-existant key is

I have a Windows 10 machine running Python 3.6.3. As stated above this issue only happens at 12:00am every night when entering in "New York, NY"
```

The description above has detail for what happens, detail for reproducing the bug, a traceback, and system information, along with detailed information about when and where it happens.

I generally only care about the traceback, but the extra detail can sometimes help with some tricky bugs. 


# Enhancements
At this time, PyWeather is not accepting any enhancement requests so that we can refine the already existing features. However, if you really feel as if your enhancement idea is useful, make an issue or PM me on reddit.

# Pull requests
**PR = Pull request**

Pull requests are a great to way to contribute to PyWeather, and you'll get all the credit in return. There are a few types of pull requests I'll go through:
* Minor PRs (typos, one-line bug fixes, etc.)
* Standard PRs (fixing a data type issue, larger bug fixes, etc.)
* Feature PRs (adding in a new PyWeather feature, adding in a new data type, etc.)

I'll also go through the process of forking PyWeather, making your additional changes, and the acceptance process.

## Should I make a PR or an issue (bugs, etc.)?
It depends, to be blatant.

If you see an issue in PyWeather, and have absolutely no idea how to fix it, or have no interest in fixing the bug yourself (even if you know what's going on), then report an issue.

However, if you see a bug in PyWeather, and you feel as if you can fix the bug yourself, go ahead and attempt to fix the bug yourself, and make a pull request.

## Before you start the contributing process...
You'll need to think, and to contact if you're nice.

### Contacting me about doing a PR
Before starting a pull request, it's best to tell me that you'll be working on PyWeather in some shape or form. For minor/standard PRs, doing this is recommended, but not required. For larger PRs, this is extremely recommended.

You can contact me on Reddit, or even commenting on a commit will do just fine. However, try to avoid making a GitHub issue, if you can.

### Coding in a scheduled feature - feature PRs only
I do my best to track features that are scheduled to make their way into PyWeather by using the projects tab. In the projects tab, you'll find the "To Do", "In progress", and "Done" columns.

In the to-do column, the features I'll work on after I'm done with a feature will be at the top, and vice versa.

You'll first want to notify me about working on a scheduled feature by contacting me, and this is required.

### Coding in a new feature/data type - large PRs only
If you'd like to code a new feature into PyWeather, please get in touch with me, and we can discuss if the feature or data type would work well with PyWeather.

### Your IDE & system requirements
You'll want to consider some system requirements before contributing to PyWeather, which involve having a working Git bash and a good IDE.

Having a good IDE is extremely important, and having one with code-checking features is highly recommended. The IDEs below is what I can recommend:
* PyCharm - Highly recommended
* PyDev with Eclipse - Recommended
* LiClipse - Recommended
* Eclipse Che - Recommended
* IDLE - Ok, has basic code-checking if I can recall.
* Vim - Seems good?

These IDEs can pass, but aren't recommended:
* Atom - No code-checking
* Sublime Text - No code-checking
* nano - No code checking

These IDEs are frowned upon, and shouldn't be used:
* Notepad++ - I've had indentation errors
* Notepad - Why are you developing in Notepad?

Of course, this is a non-exhaustive list of IDEs, and you can use whatever you like in the end.

You'll also want to make sure you have a functioning Git bash. On Windows, this can be achieved by downloading the old GitHub desktop app:

https://github-windows.s3.amazonaws.com/GitHubSetup.exe

You can use the new GitHub desktop program, but it's frowned upon because it's Electron and doesn't include a real Git bash.


For OS X/Linux, you can easily install Git and set up Git with GitHub.

On OS X, you'll want to install the Xcode developer tools, just type in `git` into a terminal and follow the instructions to download.

On Linux, if it's not preinstalled, use your package manager to install Git.

You can set up Git in a command line by using this guide: https://help.github.com/articles/set-up-git/

## Forking PyWeather
Forking PyWeather is easy, press the big fork button. It's forked, hurray!

(more down here)


# QA
Helping out with PyWeather QA is easy. Once I write how to do it in a few months, of course.

# Wiki

# Translating
At this time, PyWeather is an English-only project. I considered the logistics of attempting to translate PyWeather, but it would end up being extremely hard, and to do it effectively it would require basically a refactor.

You are welcome to fork PyWeather and create a translated version of PyWeather for your language, and I'll happily advertise it in the readme as long as you keep it updated.

# Contributing Rewards/Acknowledgements
In return for contributing to PyWeather, I'll acknowledge how much of a cool person you are through acknowledgements and contributing levels. The levels are as follows:

* Contributor: You've reported at least 1 issue that required code changes, and/or made 1 pull request.
* Awesome Contributor: You've reported 3 issues that required code changes, and/or made 3 pull requests.
* Ultra Contributor: You've reported 10 issues that required code changes, and/or made 6 pull requests.
* Is PyWeather your side job? You've reported 20 issues that required code changes, and/or made 12 pull requests.
* Bug Snatcher: You've reported 40 issues that required code changes.
* Senior Reporter: You've reported 60 issues that required code changes.
* PR master: You've made 16 pull requests.
* PR legend: You've made 24 pull requests.
* Secondary developer: ~15% of PyWeather's codebase is code that you've provided.
* Main developer: ~25% of PyWeather's codebase is code that you've provided.
* Feature developer: You've coded in at least 3 features into PyWeather.
* Data type developer: You've coded in at least 3 data types into PyWeather.

Contributors are acknowledged in the about page of PyWeather (updated each new release), and are updated on an as-needed basis in the readme file.

Anything that a contributor has done (report an issue, code in a new feature) will be given full acknowldegement in the changelog for each new release.
