## Anamo Kisho
## Lecture Notes: Day 22
## Date: 04/10/2023

### Using Bisect 
To do an exercise on Bisect, we will use a program that will run the language Ruby
Because the version of Ruby we need is not the one we can install by default on our Linux lab machine there are steps we need to do to set up the environment.  
Steps to set up Ruby environment:
•	sudo apt update
•	sudo apt install git curl autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm6 libgdbm-dev libdb-dev
•	curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
•	echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
•	echo 'eval "$(rbenv init -)"' >> ~/.bashrc
•	 source ~/.bashrc
•	 rbenv install 2.7.8
•	 rbenv global 2.7.8
We will use "git bisect" to find the commit where the failure begins.
Useful commands:
git bisect start: start a bisecting search
git bisect good: mark a commit as "good"
git bisect bad: mark a commit as "bad"
git bisect reset: get out of a bisecting search
git bisect run: run a script to automate the search (needs a good and bad mark)

Phony 
The Job of Phony is to take a phone number that is typed in and turn it correct formatted output 
Phony works with international numbers only such as 61 412 345 678!
The goal of this phony is to be able to normalize/ format/ split all phone numbers in the world
Using phony on our Linux machine:
First, we need to checkout the version of phony that will work for the example we are doing, and we will use its tag.
	The point of tag in a repository is used as a permanent name for the one of the commits. Like a version of phony 
	git checkout v1.9.0
	format command in phony will take a string of different phone numbers and change it to a correct format of phone number
	ruby -e “require “./lib/phony”; puts Phony.format(“13152291875”);’ ------------------------ +1 315 229 1875

	The normalize command will take a string of phone number and change it back to strings of numbers 
	ruby -e “require “./lib/phony”; puts Phony.normalize(“+1(315) 229-1875”);’ --------- 13152291875

Example using normalize:
-	git checkout v2.10.0
-	ruby -e “require “./lib/phony”; puts Phony.normalize(“999”);’ -------- this broke the program, meaning some where between the commit tag v1.9.0 and the commit tag v2.10.0 , we have a commit that broke this functionality for normalize(“999”).
We want to know where along the way this broke or stopped working and to do that, we can do a binary search.
Git allows us to automate that binary search and this tool in git that will do the binary search is called bisect. The function of bisect is:
-	It allows us to mark the good and bad commit, also checks other commit along the way to see whether they are good or bad 
Example:
git bisect start 
git bisect good ---------mark a commit as good
git bisect bad ------------ mark bad
git bisect run <script> Exit 0 “good”
                        Exit 1 “bad”
Philosopher David Lewis: “Actual cause”:
-	When thinking about the good and bad version of our code, the none overlapping parts of the good and bad version of the code, meaning this part are the one that changed, deleted or added is the cause the code is not working
-	Bisect will show us the two permits and show us the cause
-	To fix this, we want most of the code to be the same or we want much overlap between the good and bad version of our code. Also have our actual cause be the minimal amount of change
-	to further minimize the changes that cause the failure 
Minimization is computationally difficult 
Simplifying assumption:
Given a set of changes, if removing any changes makes the set “not interesting”, then we have found a one-minimal set. 
