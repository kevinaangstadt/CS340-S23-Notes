# **Lecture 2**

## Overview
- Within this class there are two different sections that we go over.
- We first go through our presentations and faulty software and it's repercussions.
- We then go through some notes about about how to connect to linux labs with some basic bash commands
- we end with notes on for loops that will be continued in the next day's lecture

## Class presentations

 ### Problems caused by issues in software
#### Northeast Blackout of 3003
- There was a software bug called the “Race Condition”, that once triggered stalled FirstEnergy’s control room alarm system for over an hour. System operators were unaware of the malfunction
- Loss of water pressure led to water contamination. So, 4 million people were under boil water advisory until August 18th. 4 Days after the power outage.
- Power outage along the eat coast. 55 Million people were affected during this and 100 people died.
- “A race condition occurs when two threads access a shared variable at the same time...” – Microsoft. “in some homes, there are multiple light switches connected to a common ceiling light. When these types of circuits are used, moving either switch from its current position turns the light off.” – tech target

#### Aviation – 737 MAX
-	##### Software MCAS – maneuvering characteristics augmentation system
o	Built to enhance pitch stability of 737 MAX so that it would work like older models (newer models had bigger engines which pushed nose up)
o	Meant to make it easier to train flight crews on newer models 
o	Flight crews not well trained on use
-	##### Issue Caused by false AOA inputs to 1 sensor which triggered MCAS (tipped nose down during takeoff and kept malfunctioning as crew tried to correct nosedive because they could not override the software).
o	AOA – angle of attack (angle between wing and airflow on the wing)
o	2 crashes, 346 people died
-	##### Changes MCAS software has been modified to use 2 sensors instead of 1 (in case one fails), and flight crew can now completely override the software.
o	Pilots now go through training on managing MCAS and problems that might arise

#### ETCS software malfunction
-	During the trial embedded systems expert who reviewed Toyota’s electronic throttle source code testified that they found Toyota’s source code defective, and that it contains bugs – including bugs that can cause unintended acceleration.
-	“we’ve demonstrated bow as little as a single bit flip can cause the driver to lose control of the engine speed in real cars due to software malfunction that is not reliably detected by any fail-safe.” Michael Barr, CTO, and co-founder of Barr Group told us in an exclusive interview. Barr served as an expert witness in this case.

#### Ariane 5 flight 501
-	Problem came from reused code from the inertial reference platform (IRS) on the Ariane 4
-	Ariane 5’s flight path caused certain values, specifically the horizontal bias variable to be much higher than the code was meant to handle.
-	Greater values of horizontal bias data were converted from 64-bit floats to 16-bit int values causing an overflow, meaning the numbers were too large to represent with just 16 bits.
-	Only 4 of the 7 variables used were protected from overflow, designed only to handle the assumptions about the Ariane 4 flight path. 
-	The overflow halted the IRS modules, and the one active module send a diagnostic bit patter to the on-board computer, bit it was interpreted as flight data. 
-	This caused the rocket to bank to an angle of more than 20 degrees, causing it to rip apart and then self-destruct.
-	Supplier of the nav software was told to stop the processor when an exception occurred, so the exception which occurred was due to a flaw in the design, causing the shutdown of two good units when they could have still provided best estimates of the required info. 
o	Simulations should have been completed prior to launch
o	Identify all previous assumptions and make sure they are still valid
o	Ranges of variables should have been explicitly quantified instead of just assuming a range, in this case a 16-bit range
-	The failure brough to light the risk with complex computation and increased the support for research on ensuring the reliability of safety critical systems.

#### Patriot Missile defense system error
-	 ##### What happened
o	Failed to intercept an incoming missile. 
o	The incoming missile hit a United States Army Barracks in Dhahran, Saudi Arabia during the Gulf war.
-       ##### How was SW involved
o	Source Code Reviews after incident revealed errors.
o	Software calculated the position of the incoming missile.
o	Failure due to rounding error over 100 hours.
-	##### Why so Bad
o	28 Americans killed, over 100 injured.
o	This flaw exists in ALL Patriot missile Defense Systems.
o	Purely software, completely preventable.
-	 ##### Implications
o	Now this type of software undergoes endurance tests (what happens if we run this code for a long time).




## Class Notes
	
### Using a computer

#### Graphical User Interface
	- GUIs are convenient, but slow.

#### Command line access
	- gives us access to run tools “under the hood”.
	- can increase productivity by learning these command line tools.

#### Linux based OS
             - Windows makes up 75% of all desktop/laptop operating systems
             - MacOS makes up 15% of all desktop/laptop operating systems			
             - We will focus on a Linux-based OS for learning a set of tools				
             - Linux is the dominant OS

#### Sshing and other definitions
	- We will use virtual servers running Linux for this class

	#### Definition
**Shell** is a program that exposes an OS’s services to a human user or other programs
- textual interface (terminal, git-bash, PowerShell)
	#### Definition
		**Secure Shell** remote access to a shell on another computer

	###### how to ssh
		- the xx is each student’s unique number
		- cslinuxlab-xx.stlawu.local

#### Using terminal on the secure shell

	###### Logging into Linux labs
		- ssh {full email address}@cslinuxlab-xx.stlawu.local
		- type yes
		- enter your St. Lawrence password     
		- Control d to exit Linux labs 

	###### Creating password 
		- ‘ssh-keygen -o’ Generating public/private rsa key pair
		- hit enter
		- chose passphrase
		- type It again
		- Your certificate is created

	###### Using a certificate
		- ‘ssh-copy-id’ {full email address}@cslinuxlab-xx.stlawu.local 
			- this is how you get your public key onto the other machine
	
-	Enter your passphrase
-	Now your certificate is on the Linux lab machine

#### Basic bash commands
	- ‘pwd’ (present working directory)
- ‘ls’ (list all files/directories/etc.)
- ‘cd’ (change directory)
	- ‘cd .’ (stay in that level)
	- ‘cd ..’ (takes you up one level)
	- ‘cd /../../..’ (can give a path)
- ‘clear’ (clears the screen without deleting)
- ‘mkdir’ <directory name> (makes directories)
- ‘which’ <program> (tells you where program lives on machine/if it has it)
- ‘curl’ -O -k <URL> (download files/ignores certificates/with the same name)
- ‘man’ <program> (brings you to manual page)
- ‘less’ <filename> (new version of more/lets you view file)
- ‘tar’ xzf <filename> (extract a file in gzip format)
- ‘find’ (will show every file in that level of directory)

#### Directory structure Linux
-	Starts with a leading / (can cd to /)
-	Bin is below / (binary – executables live here)
-	Lib is below / (library – support files)
-	Home is below / 
-	Below home is our account where we can make files and directories

#### Setting up CS340 directory 
-	Use mkdir CS340 in your Linux lab directory
-	Enter CS340
##### Scraping from the internet
o	Use curl and a URL to download random.tar.gz

#### How to use less and the man pages 
-	Options are the flags that we use with commands to make them do things
-	/ allows you to type and hit enter to search 
-	Man gets you to the manual
-	Less allows you to view files
-	Get out of less with q



#### How to use for loops in bash
	###### Example 1
	```
	for I in {0..100}
		do
		echo  $i
		done
	```
	###### Example 2
		Stepping through by 2’s
	```
	for I in {0..100..2}
		do
		echo  $i
		done
	```



	 
