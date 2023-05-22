# Command Line
## Bro your are literally vim

![Image](hishitpost.jpg)

---

Greetings and welcome back. Today we have a shorter tutorial for you, and don't worry, I'll only charge you $145.

I apologize for the weird side scrolling bars thing with the last Lab Report. I do hope it doesn't happen with this one. Never seen anything like it either, and google 
surprisingly had nothing for me. Weird. 

Nevertheless, let's get started.

---
## Part 1: Vim
### No I didn't misspell him these commands are just spelled weird ok

Today I shall show you how I made a simple edit through the command line. I know right, you don't have to edit the file directly, you can use **vim** 
and the command line and still make any edits! Pretty cool.

Before we get started though, you need to understand what I'm doing. Well, you've come to the right place. Enter: Vimtutor Eugene Edition!

---
### Vimtutor: Eugene Edition

Note: Keys on your keyboard will be shown as `key`, and when the key looks like `<key>`, that means press that key.

**Moving around**: When you enter a file with the **vim** command, you will be able to freely navigate the contents of that file using your cursor. The easiest way to do this is through the arrow keys, with each arrow key corresponding to their directions. If you don't have any arrow keys though, fear not, for you can use `h` to go left, `l` to go right, `k` to go up, and `j` to go down. 

**Normal Mode**: Normal mode is where you can naviagte the file with your cursor. Whenver you enter another mode and want to get back to normal mode, press `ESC`.

**Deleting a character**: To delete a character, all you have to do is press `x` and the character under your cursor will be sent to the shadow realm. Sorry buddy.

**Insertion Mode**: To insert a character, press `i` and you will enter insertion mode. Move your cursor to wherever you want to insert the character and start 
typing away. The character that was under your cursor will be pushed to your right. In other words, your cursor will cover the same character the entire time you're typing,
and insert characters directly to the left of your cursor.

**Appending Mode**: To append test, press `SHIFT` and `A` at the same time (press and hold `SHIFT` and press `A`). This will send your cursor to the end of the line, and from there everything you type will be added to the end of the line. 

**Repeated commands**: Sometimes you need to perform a command multiple times. Well instead of pressing `DOWN` 43 times like I did, just type: 43 `<DOWN>`, and your cursor will move down 43 times. Putting a number before a command will execute the command that many times. Very handy.

**File commands**: Now that you have the basics of how to interact with the contents of a file, here is how you actually do that in a file.
1. First in the command line, type: vim (filename) `<ENTER>`, with (filename) being the name of the file you want to edit. This will pull up the entire file in the command line and start the **vim** editor, which is what you've been learning this whole time! Now you can navigate your file freely, and edit its contents!

Once you are done, you have two options:
1. **Exiting and saving all changes**: To exit and save all changes, type :wq `<ENTER>`
2. **Exiting and deleting all changes**: to exit and not save any changes, type :q! `<ENTER>`

And that's it! Hopefully now you have a basic understanding of how to use **vim**. I've only included what I think is necessary to complete what this Lab Report entails, but if you'd like to learn more about vim, log into your ieng6 account and type: *vimtutor* `<ENTER>`.

---
## Part 2: The Steps
### 

Here are the steps that I will be doing today:
1. Log into ieng6
2. Clone your fork of the repository from your Github account
3. Run the tests, demonstrating that they fail
4. Edit the code file ListExamples.java to fix the failing test (as a reminder, the error in the code is just that index1 is used instead of index2 in the final loop in merge)
5. Run the tests, demonstrating that they now succeed
6. Commit and push the resulting change to your Github account

I'll include pictures of every step one I have completed them. I also have to record **every single button that I press** (😡), so you'll be able to follow along with me too.

For my starting point, I have Visual Studio Code open and the terminal ready. I have also forked and cloned this repository `https://github.com/ucsd-cse15l-s23/lab7`.

Also, here is a handy list of things to copy and paste with ease:
ssh cs15lsp23__@ieng6.ucsd.edu
git clone https://github.com/ucsd-cse15l-s23/lab7

### Step 1: Long into ieng6

*Keys Pressed*: `<CTRL>`(hold) `<V>` `<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<LEFT>``<DELETE>``<DELETE>` `<E>``<R>``<ENTER>`
