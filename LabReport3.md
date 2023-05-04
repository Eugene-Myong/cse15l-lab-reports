# grep (That's it that's the title)
## A tutorial for UCSD Students

![Image](hishitpost.jpg)

---

Ah, how do you do? We are always happy to have returning customers. In fact, you've been so loyal to us we'd like to offer you a new rate! (Wow! So cool!) I know right?
Your new rate is $150 USD per hour. You may be thinking, "Wait, that's more!" And you are right, but hear me out. Using my supreme knowledgeof numbers as a math major, 
I have made it so that one of us benefits off of this new arrangement. Who is it? I don't know, but maybe we'll find out later. Let's get started.

---
## Part 1: grep
### No I didn't misspell grab

Ok so, imagine that there's some random word you are trying to find in a file. Let's say this file has thousands of lines of words. It seems impossible to find this
one word right? Thousands of words stand in your way, how are you going to find it? Well fear no more, becasue grep is here! 

Here's how you would use it:
```
grep (argument1) (argument2)
```
`grep` is the command itself, so you gotta write that out. `(argument1)` is the thing you are searching for, most often a string. `(argument2)` is the file that
you are searching in.

Here's a real life example of it. Let's start in the directory **technical**. This directory has four sub-directories in it, **911report1, biomed, government**, and
**plos**. Let's start in **plos** (because it sounds funny). In **plos** there are a lot of text files. Let's go into the
first one, **journal.pbio.0020001.txt**. 

Let's now say we're searching for all lines that have the word "science" in it. We would type this command in:
```
grep "science" journal.pbio.0020001.txt 
```
And we would see this:
```
the clear inequalities in science between developing and developed countries and to the
        importance of reducing the inequalities in science between developed and developing
        It is rather obvious that richer countries are able to invest more resources in science
        contributions to science, despite the fact that the average proportion of gross domestic
        product (GDP) invested in science in Latin America throughout this 10-year period was only
        productivity is remarkable when we compare it with the relatively low investment in science
        rate as well as in financial investment in science and technology. Some countries have
        funding to the most productive scientists from the national science development programs
        and global change biology) between 1990 and 2002 in both the two top general science
        American researchers are not shying away from the two top-ranked general science journals.
        ecology and environmental sciences emphasizes the overwhelming contributions of authors
        conspiracy, but rather it implies that the perception of the most important science is
        science is most interesting to them. Another consideration is that more local journals from
        developing world (Goldemberg 1998; Annan 2003). One is that science, as a discipline, would
        Brazil (Goldemberg 1998) and biomedical sciences in Cuba (Castro Díaz-Balart 2002). These
        to the sciences will be an excellent investment by developing nations in terms of
```

That's a lot of science. Go figure.

Even better, that's the basics of grep. Now you can find any word in any text file that you could think of! 

But what if you wnat to ignore capitalization, or find all the lines without that word? Or pay me less?

Well you can't do that last one, but I can help you with the other two, and more! Enter: Part 2.

---
## Part 2: grep (but more!)
### There's a lot here, make sure you save your game!

Ok so, here's the deal. Below, you can find four additional ways to use grep. Each one will be using the **journal.pbio.0020001.txt** text file in the **plos** 
directory. Additionally, unless I otherwise state, assume that `(argument1)` is the string you are searching for and `(argument2)` is the file that we are searching
in.

---
### grep -i

First up is `grep -i`! What this version of grep does is ignore capitalization, so using `grep -i` on the same file as before with the same word, *science*, will 
return all the lines that have *science* in it regardless of capitalization, so *Science*, *ScIEnCe*, and *SCIENCE* are all fair game.

Here's the format for that:
```
grep -i (argument1) (argument2)
```
Here's the call:
```
grep -i "science" journal.pbio.0020001.txt
```
And here's the result
```
        the clear inequalities in science between developing and developed countries and to the
        importance of reducing the inequalities in science between developed and developing
        88% of all scientific and technical publications registered by the Science Citation Index
        It is rather obvious that richer countries are able to invest more resources in science
        contributions to science, despite the fact that the average proportion of gross domestic
        product (GDP) invested in science in Latin America throughout this 10-year period was only
        productivity is remarkable when we compare it with the relatively low investment in science
        rate as well as in financial investment in science and technology. Some countries have
        funding to the most productive scientists from the national science development programs
        and global change biology) between 1990 and 2002 in both the two top general science
        Science ; with impact factors of 27.96 and 23.33, respectively) and in
        Science and
        Science and
        American researchers are not shying away from the two top-ranked general science journals.
        Science and
        ecology and environmental sciences emphasizes the overwhelming contributions of authors
        conspiracy, but rather it implies that the perception of the most important science is
        science is most interesting to them. Another consideration is that more local journals from
        developing world (Goldemberg 1998; Annan 2003). One is that science, as a discipline, would
        Brazil (Goldemberg 1998) and biomedical sciences in Cuba (Castro Díaz-Balart 2002). These
        to the sciences will be an excellent investment by developing nations in terms of
```
As you can see there are now a bunch of *Science*s in there as well! If there were any *SciEnCe*s in there I'm sure they would show up, but this seems to be a 
scholarly article so it's probably for the best they aern't there.

---
### grep -v

What if you wanted to do the opposite? What if you wanted all the lines that don't have a certain word in it? That's what `grep -v` is for!

`grep -v` does exactly what was described above: returns all the lines that does not have `(argument1)`. 

For this example, I'm not going to use *science* as my word because I tried that and can't even fit all the lines in a screenshot. Instead, we shall use the letter
*e*, because *e* is very common and will still show how `grep -v` works. The implementation is as follows:
```
grep -v "e" journal.pbio.0020001.txt
```
The result:
```











        2002).


            Canada?




        programs.


        journals (
        In


        world.




        built.



```

Something interesting: I didn't add those spaces/empty lines. That was part of the result. What this means (or at least I'm guessing it means) is that grep also
searches through spaces and empty lines as well. Because an empty line or a space is not *e*, it will still print that out as a result. Perhaps not particularly
useful, but something to keep in mind.

---
### grep -f
