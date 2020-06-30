# rstash
r[emote]stash is a bash script that was created to make remote pair programming easier.

Pair programming usually follows the [Driver-Navigator approach](https://martinfowler.com/articles/on-pair-programming.html#DriverAndNavigator). This means that both developers have the same view in front of them, but only one of them controls the mouse and the keyboard, whereas the other one says what should be done. After a previously defined duration, the roles are swapped. This works without any problems if both are sitting in front of the same computer. In times of home office this is not always the case. The local changes must therefore be transferred from one computer to the other when swapping the roles. You can do this by sending patches to each other or by working on a branch. We work with branches very rarely, so this script was created to simplify and speed up the workflow.

## Installation
- Goto [Releases](https://github.com/otto-de/rstash/releases)
- Download the latest rstash script
- Move the script to a directory in your PATH

## Usage
Alice:
- Open any git repository
- Make some changes
- Execute ```rstash``` without any arguments
- rstash creates a new branch with a unique name
- Press [Enter] to discard the changes locally

Bob:
- Open the same git repository
- Execute ```rstash 123```, whereas ```123``` is the rstash pin which was displayed in Alice's command line after executing ```rstash```
- Or execute ```rstash list``` to get a list with all rstash branches to find the right pin
- rstash pulls the changes in your modification stage
- Press [Enter] to remove the temporary rstash branch
