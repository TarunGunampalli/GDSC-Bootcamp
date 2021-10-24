# GDSC Developer Basics Bootcamp
## Command Line
#### Basic Mac/Linux Commands
- ```pwd``` (shows the path to the current directory)
- ```ls```  (lists the files in the current directory)
- ```cd <directory_name>``` (navigates to a specified subdirectory)
- ```ssh``` (can be used to remotely connect to another machine's terminal)
- ```clear``` (clears all previous terminal output)
- ```touch <filename>``` (changes a file's timestamp)
- ```mkdir <directory_name>``` (creates a new directory with a specified name)
- ```rm <filename>``` (deletes a file or directory)
- ```vim <filename>``` OR ```nano <filename>``` (opens a text editor for quick changes to a file)
- ```cat <filename>``` (displays the contents of a file)

#### Windows Equivalents
- ```cd```  (shows the path to the current directory)
- ```dir``` (lists the files in the current directory)
- ```cd <directory_name>``` (navigates to a specified subdirectory)
- ```(ssh is not available directly on Windows)```
- ```cls``` (clears all previous terminal output)
- ```type nul > <filename>```  (changes a file's timestamp)
- ```mkdir <directory_name>``` (creates a new directory with a specified name)
- ```del <filename>```    (deletes a file or directory)
- ```micro <filename>```  (opens a text editor for quick changes to a file)
- ```type <filename>```   (displays the contents of a file)

#### Flags and arguments
- These are further specifications on what a Linux Command should do
- A command might be "go buy milk"
- A command with an argument might be "go buy 2 gallons of milk"

#### What is WSL?
- Windows Subsystem for Linux
- WSL is a Linux terminal that you can use from within Windows, without dual booting or using a virtual machine.
- WSL is very useful for developers on Windows since many tutorials/instructions are given in Linux commands, most of which don't work on Windows. Using Linux commands to interface with your Windows filesystem is very useful.
- Things to know
    - You can access your windows filesystem by running ```cd /mnt/c``` . This takes you to your Windows C: drive.
    - Packages in WSL are completely separate from your Windows machine. For example, if you install python on WSL, you'll only be able to run python programs with the ```python``` command from within WSL and not from your default command line, and similarly if you install it on Windows instead. Pick either WSL or Windows for packages now and make sure to stick with it. 

<br>

## Code Editors and IDEs
Code Editors vs IDEs
- Code editors like Visual Studio Code and Atom are text editors at the core. When you install one, you won't be able to run programs directly or get specific features like debugging out of the box. In their most basic form, they are just glorified notepads.
- IDE stands for Integrated Development Environment. They come with everything you need for developing using a specific language.
    - For example, Eclipse is an IDE for Java. It will come with a package manager for importing external Java classes, a debugger that can trace through your code and provide useful information on what's going on as your code runs, and Intellisense, a useful autocomplete feature that helps you write code faster.
- Pros and Cons
    - VS Code may seem ineffecient, but with the use of extensions you can work in basically every feature that a full IDE like IntelliJ would give you. This includes Intellisense, a debugger, and many other useful features.
    - VS Code is more versatile. IntelliJ is only for Java, and there's other IDEs for other languages, but VS Code can be used for any popular language today with community or professionally maintained extensions.
    - IDEs are often faster than VS Code because everything is natively built-in.
    - Good code editors like VS Code have features where you can pull up a terminal below your code window, making it easy to run your code with simple commands

Parts of VS Code
- Sidebar
- File explorer
    - Used to browse through files in your project folder.
    - You can search through your files by using ```Ctrl + P``` or by clicking into the file explorer window and typing.
    - Global Search
        - Searches through every file in your project folder
    - Source control
        - GUI that's very useful for using git/github without having to memorize a ton of commands.
        - Using an extensions like Gitlens, VS Code source control allows you to see previous commits, branches, and histories in easy to read GUIs compared to git on the command line.
    - Extensions
        - Extend the versatility of VS Code by adding in a ton of useful features.
        - Popular useful extensions:
            - Language Extension Packs (Java, C/C++, Python): Add IDE-like features for each language into VSCode
            - Gitlens: Provides way more information about git/github commits, branches, and histories.
                - Fun Fact: Gitlens is the most downloaded extension on VSCode.
            - Live Share: A live collaboration tool for working on the same codebase simultaneously.
- Bottom Window
    - Shortcut to open and close: ```Ctrl + ` ```
    - Terminal
        - A normal command line that's integrated into VS Code
    - Debug Console
        - Debugging in VS Code is a little advanced, but the console is how you interface with the debugger, allowing you to do things like print the values of variables, see stack traces, and use any other features that traditional debuggers have.
- Command Palette
    - The source for any command that VS Code has, built in or from extensions
    - Open it with ```Ctrl + Shift + P```
    - Commonly used commands automatically appear at the top
    - Start typing to search for specific commands

Eclipse
- Eclipse is an IDE, or Integrated Development Environment catered to Java developers. In a nutshell, IDEs share many characteristics with code editors, but go one step further and provides more comprehensive facilities to software developers, such as the ability to run your code with the click of a button, more powerful debugging capabilities, and live unit testing for those working a professional Software Engineering job.
- For our purposes, we will simply demo how to use Eclipse. The installation and setup requires a bit of work as well as downloading a Java Runtime Environment and possibly also a Java Development Kit.
- If you would like to try out Eclipse for yourself in your computer, you can follow the tutorials at this link: http://eclipsetutorial.sourceforge.net/

<br>

## Git and GitHub

#### What is Git?
- Git is software for tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development

#### What is GitHub?
- GitHub is a provider of Internet hosting for software development and version control using git. It offers the distributed version control and source code management functionality of git, plus its own features.

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

Pull Requests and Merging
- After you are done working on a branch, you can create a pull request, in which a request will be made to merge the changes in that branch to the main branch. This process is done so that your collaborators can perform a "code review" and make sure all the changes look good before bringing them into the main code
- In the industry, this is an important practice because the main branch is typically set up with automated testing and deployment configurations, so developers should NEVER push code changes directly to the main or risk breaking entire applications
- More on this in the live demo

<br>

## Virtual Environments 

#### What is a Virtual Environment?
-  A virtual environment is a Python environment such that the Python interpreter, libraries and scripts installed into it are isolated from those installed in other virtual environments, and (by default) any libraries installed in a “system” Python, i.e., one which is installed as part of your operating system

#### Conda
- There are multiple different ways to create and activate virtual environments, but today we will use Conda since it's very easy to manage

#### Installing Conda
- https://docs.conda.io/en/latest/miniconda.html
- You don't have to do this right now if you don't want to since the installation can be a little tricky depending on your machine

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
