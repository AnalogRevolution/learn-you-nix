# Welcome, and Let's Learn You Some *nix For Greater Good

## Purpose
The purpose of this short document is to introduce the reader to what a *nix shell is, and how to maneuver it. We shall be concise and get you using the shell in no time.  

Please don't fret and worry, the shell looks intimidating at first but within a few minutes you'll start to get the hang of it. Just remember that it's super important to remember that by using a shell we are communicating more directly with our operating system (OS). Userland, usually maneuvered through a GUI (graphical user interface, pronounced 'goo-ee'), is comprised of programs for interacting with your OS - think games, browsers, notification apps, a GUI file system, etc. - but by using a shell you are provided with a new suite of programs for interacting with your computer one level deeper than GUI Userland.  

If you want to accomplish more, stay out of GUI Userland. It's not comfortable there.

### Terminology Thus Far
* shell - a suite of programs for interacting with your OS, and one level deeper than a GUI Userland. Repeat after me: What you can do in the GUI Userland you can do in the shell! (even browse the 'net!)
* userland - where a computer user exists
* operating system - the core programs that make a computer 'work'. Most people refer to a 'computer' as what they are interacting through, but that is not the case. This is known in geek speak as Userland. 
* programs - a set of 'things' that take input and give output - It's the way you speak to your computer (browsers, file systems, games, etc.)
* GUI - Graphical User Interface, that is, a way of interacting with a computer through programs that are more visually appealing than the shell


### What the shell is and what is a command
Before we start we need to clarify one more time what a shell is, and then tell you about commands. A shell is the way to communicate more directly with your computer. It is important to note here that the 'shell' is typically used only when talking about a *nix operating system - that is, a system that is either Unix itself, or mimicks the behaviour of a Unix system. For more info on Unix click [here](https://en.wikipedia.org/wiki/Unix).  

You may have heard of the Linux operating system - this is actually a group of projects which sought to replace the Unix OS with a 'free' version that anyone in the world can use. For more on this philosophy you can click [here](https://en.wikipedia.org/wiki/Free_and_open-source_software).  

So the shell - how does it work? Well, it is actually comprised of small programs that have very niche purposes. Usually these programs are refered to as 'commands', and by issuing commands to your shell you are interacting with your operating system. That's it!  

1. Your shell uses small programs known as commands which allow you to accomplish what you can in the GUI Userland
2. Each command is a small program that accomplishes only one task. Thus, it is important to learn a number of commands to be able to successfully use the shell. That's where this guide comes in!

---

### Ready to begin?
Hopefully by now you've at least a vague understanding of what I mean when I say 'shell', and how it differs from the typical method of interacting with a computer. Now it's time to learn some commands.  

The commands we are going to learn are:  
* cd
* ls
* pwd
* nano
* rm
* touch
* mkdir
* man

When you use the shell, you interact with it using something called a _terminal_. What's a terminal? It's the cool thing you see people in _The Matrix_ and other hacking movies use; you are prompted to input some letters, and the computer does what you want!  
![xTerm](https://upload.wikimedia.org/wikipedia/commons/b/b3/Xterm_45.png?raw=true)

The commands listed above will get you up-to-speed so that you can start maneuvering your server with ease; _trust me_, once you start you can become addicted! Let's jump in, shall we. It'd be best to have your terminal up and running.

As I demonstrate commands for you to try, I'll be using a syntax like so: `$>___`. This means anything after the `>` I want you to input yourself into your terminal. :)

### Commands
* pwd
 - print working directory
 
 Most of you are familiar that in GUI Userland, you have a file system where you have your `Documents`, `Pictures`, `Music`, etc. folders. These folders are commonly called directories. Well, in the terminal, if you want to know where you are among your folders, you can `$> pwd`. Give it a go now.
 
 Eg, 
 `$> pwd`  
 `$> /home/noah`
 
 This means that I am in the subfolder of the folder `/home`. 
 
 But what about looking at what's currently in your directory?
 * ls
  - list everything in your current directory  
  
  So, if I `$> ls`, I see that in my current folder I have: `Mail public_html sent`. These can be a mixture of directories and individual files. Take some time now messing about with these two commands and start picturing in your head that you're doing the same thing that's possible in GUI Userland.
---
But what if I want to move through these folders? 
* cd
 - change directory
  
  You can `$> cd` into other directories. You do this by typing the `cd` command and then an _argument_, or the value that the program/command will evaluate and manipulate for you. So by doing `cd <destination>`, you move into that destination! 

```
$> cd public_html
$> ls
$> index.html notes.txt
```  
 If I changed into my `public_html` folder, and then `ls` in that directory, I see that the shell returns _2_ files for me; `index.html` and `notes.txt`.  

Now, what if I want to move back a directory? You simply `cd ..`. `..` Is the syntax that the terminal understand for meaning _move back one directory_. 

```
$> cd ..
$> ls
$> Mail public_html sent
```

Are you getting the hang of this now?

So let's say you want to `cd` back multiple directories; simply add `/` in between the number of directories you want to change. Let's break this down. `cd ../..` means you want to `cd` _back_ two directories, and `cd ../../../..` means you want to `cd` back _four_. But what if you want to move _forward_ 4 directories?  
`cd /path/to/your/destination`.  
So this means that you simply have to append `/` in between the destination arguments that you are giving to `cd`.

Lets say I have a directory structure as so:
```
/home/noah/
          /       |           \
    directory1  directory2  directory3
      /   |    \
  pics   music  pdfs
        /    \
     Sinatra  metal
```
Let's print our working directory. `$> pwd`. We get `/home/noah/`. _Perfect_. Let's just `ls` real fast and see what we're working with. `$> ls`.  
`directory1 directory2 directory3`. _Brilliant_.  

If I'm looking for all of my Sinatra tunes (ooooo', Franky!), then instead of `cd`ing a bunch of individual times, I can  
`$> cd directory1/music/Sinatra`.  
Let's `pwd`, and we get `/home/noah/directory1/music/Sinatra/.` Great!  
```
$> ls

```  
You see that blank stuff? It means I've got no files or folders. :( I forgot to upload my Sinatra mp3's to the server!!  
Now let's just go back to `/home/noah/`.  
```
$> cd ../../..
$> pwd
$> /home/naltun
```  

You're doing great!
