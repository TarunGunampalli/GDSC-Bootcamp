# GDSC Developer Basics Bootcamp
## Command Line
#### Basic Linux Commands
- ```pwd```
- ```ls```
- ```cd```
- ```ssh```
- ```./```
- ```clear```
- ```touch```
- ```mkdir```
- ```rm```
- ```vim```
- ```cat```

#### Flags and arguments
- These are further specifications on what a Linux Command should do
- A command might be "go buy milk"
- A command with an argument might be "go buy 2 gallons of milk"

#### What is WSL?
- 

## Git and GitHub
#### What is Git?
- Git is software for tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development

#### What is GitHub?
- GitHub is a provider of Internet hosting for software development and version control using Git. It offers the distributed version control and source code management functionality of Git, plus its own features.

#### How Git and GitHub are interrelated
- Git is a command line tool that is used to manage code versions across a user and GitHub is the medium that allows multiple individual users to sync all of their changes with each other
- GitHub is an actual website and therefore provides visual feedback on all code changes, making it easy to see the version history of files, the exact changes made with every code update, and easy resolution when there are conflicts in the changes made (more on this shortly)

#### Installation
- For Mac/Linux, git comes pre-installed with your machine!
- For Windows, git can be downloaded by going to:\
https://git-scm.com/book/en/v2/Getting-Started-Installing-Git#:~:text=https%3A//git-scm.com/download/win

#### Creating a Repository
- For our demo today, please follow these steps:
    - Go to this repository: https://github.com/TarunGunampalli/GDSC-Bootcamp
    - In the top right of the screen, click "Fork"
       - This creates a copy of the codebase that you now are the owner of (like making a copy in Google Drive)
    - Go to the forked repository that you now own and click the green button that says "Code". Copy the URL that is displayed
    - Open your command line, use the cd command to navigate to your desired directory, and run the following command:
    ``` 
    git clone <paste the copied url here>
    ```
    - Now you have the codebase on your machine and can start editing. Since you cloned it off of GitHub, it is already synchronized and ready to go
- This can also be done the other way around. You can create a new directory on your computer, run the command ```git init```, go to your GitHub profile online, create a brand new repository, and follow the instructions to connect it with your locally initialized git directory.

#### How Does Git Work?
- Everytime you are writing code and editing files in your codebase, git will track the line-by-line changes in every file as you make changes and save locally. Once you have made a decent amount of changes, it is good practice to commit and push your changes to GitHub. This is done by running a few commands that we will talk about in the next section such as add, commit, and push. When you make a commit, git will take all the changes you made to the files you specified via add and save them to your local git history. When you push, these changes will be reflected in the online GitHub repository. From there, other programmers you are collaborating with can run the pull command in their local directory that is connected to the same GitHub repository and your changes will now be reflected on their machine.

#### Basic commands
- ```git add```
  - Specifies which modified files to include in a new code change
  - Can add individual files by specifying them as an argument
  - Can add all modified files in or below the directory you are currently in by saying ```git add .```

<br>

- ```git commit```
  - Must perform add before running this command
  - Takes all the modified files specified in the add command and saves them as a single "change"
  - The great thing about commits is that they are all logged both locally and on GitHub after they are pushed, making it easy to revert back to previous versions of code in case something breaks as a result of a code change
  - Should be run as ```git commit -m <commit message>``` with the commit message specifying what the code change entailed
    - For example, the message could be "changed output of the process_text function"

<br>

- ```git push```
  - Must perform add and commit in that order before running this command
  - Push takes all the latest local changes and applies them to the remote repository on GitHub

<br>

- ```git pull```
  - If the remote repository on GitHub has new changes that are not reflected on your local directory, this command will bring in those changes

<br>

- ```git restore```
  - This will discard all local changes in between commits

<br>

- ```git log```
   - This will print out your entire commit history

<br>

- ```git status```
  - This will show you what files have been modified, deleted, created, etc. between commits
  - It will also show you what differs between your local code and the remote repository on GitHub

<br>

- ```git branch```
  - This will create a new "branch" in your local directory
  - A branch is essentially a copy of the codebase within the same directory and repository. Branching allows multiple collaborators to work on different copies of the files rather than all working on the same ones. Branches can be easily merged back into one "main" branch. As a whole, it minimizes the chances of "merge conflicts" when multiple people are editing the codebase. We will talk more about this in the live demo.
  - ```git branch``` by itself will just list all your branches
  - Run ```git branch -b <branch-name>``` to create a new branch and name it

<br>

- ```git checkout```
  - This allows you to switch from one branch to another
  - Must run ```git checkout <branch-name>``` to specify what branch to switch to
  - As a shortcut, you can simply run ```git checkout -b <branch-name>``` to create a new branch and switch to it all at once

<br>

- Pull Requests and Merging
  - After you are done working on a branch, you can create a pull request, in which a request will be made to merge the changes in that branch to the main branch. This process is done so that your collaborators can perform a "code review" and make sure all the changes look good before bringing them into the main code
  - In the industry, this is an important practice because the main branch is typically set up with automated testing and deployment configurations, so developers should NEVER push code changes directly to the main or risk breaking entire applications
  - More on this in the live demo


## Virtual Environments 

#### What is a Virtual Environment?
-  A virtual environment is a Python environment such that the Python interpreter, libraries and scripts installed into it are isolated from those installed in other virtual environments, and (by default) any libraries installed in a “system” Python, i.e., one which is installed as part of your operating system

#### Conda
- There are multiple different ways to create and activate virtual environments, but today we will use Conda since it's very easy to manage

#### Installing Conda
- 

#### Creating and Activating a Virtual Environment
- To create and activate a new virtual environment, run the following commands:
```
conda create -n <environment_name> python=3.8
conda activate <environment_name>
```

#### Installing Packages in a Virtual Environment
- Once a Conda Virtual Envrionment is active, it's name will show up in parentheses to the very left of the command prompt. In order to install dependencies in it, simply run the following:
```
pip install <package_name>
```  
- You can also install multiple packages at once by simply listing the names in a file called requirements.txt and running the following:
```
pip install -r requirements.txt
```

#### Deactivating Virtual Enviroments
- To deactivate or exit out of a Virtual Environment, run the following:
```
conda deactivate <environment_name>
```

#### Summary of Virtual Environments
- When working on a Python project, you should always use a Virtual Environment for your directory so that you can install specific dependencies only for projects that need them and not globally on your machine


VSCode
Difference between a code editor and an IDE
Parts of the window
SideBar
File explorer
Source control
Extensions
Bottom Window
Terminal
Debug Console
Command Palette
Keyboard shortcuts
Ctrl + space for intellisense
copy/move commands
Debugging
Why use vscode debugger?
GUI makes it easier to use
Can automate multiple tasks
launch.json
tasks.json

IDE
IntelliJ/Eclipse for Java

