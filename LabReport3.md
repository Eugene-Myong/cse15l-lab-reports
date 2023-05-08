# grep (That's it that's the title)
## A tutorial for UCSD Students

![Image](hishitpost.jpg)

---

Ah, how do you do? We are always happy to have returning customers. In fact, you've been so loyal to us we'd like to offer you a new rate! (Wow! So cool!) I know right?
Your new rate is $150 USD per hour. You may be thinking, "Wait, that's more!" And you are right, but hear me out. Using my supreme knowledge of numbers as a math major, 
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
you are searching in. The command will return all the lines that have that `(argument1)`.

Here's an example of it. Let's start in the directory **technical**. This directory has four sub-directories in it, **911report1, biomed, government**, and
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
directory for it's first example, and the **1468-6708-3-1.txt** text file in the **biomed** directory for the second. Additionally, unless I state otherwise, assume that `(argument1)` is the string you are searching for and `(argument2)` is the file that we are searching in.

---
### grep -i

First up is `grep -i`! What this version of grep does is ignore capitalization, so using `grep -i` on **journal.pbio.0020001.txt** as before with the same word, *science*, will return all the lines that have *science* in it regardless of capitalization, so *Science*, *ScIEnCe*, and *SCIENCE* are all fair game.

Here's the general format for that:
```
grep -i (argument1) (argument2)
```
Here's example 1's call and result: 
```
grep -i "science" journal.pbio.0020001.txt
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

In addition to finding all the lines that have *science* in them, it also lists all the lines with *Science*! This is useful for when you don't care about capitalization, and just want to see how plentiful a word is in a file.

For example 2, lets use the word *after*:
```
grep -i "after" 1468-6708-3-1.txt
          brief telephone interview 6 months after each scheduled
          7 years after baseline. YHL is the number of years in
          data when there were known values before and after the
        income and education (data not shown). After adjusting for
        After adjustment for income and education, the difference
        after adjustment for age, but the difference disappeared
        after adjustment for the entire set of health-related
```
And here we have all the lines that use *after*. 

Overall, `grep -i` is quite simple: return all the lines that have that word while ignoring capitalization. That doesn't limit its uses though, as being able to ignore capitalization is quite useful.

---
### grep -v

What if you wanted to do the opposite? What if you wanted all the lines that don't have a certain word in it? That's what `grep -v` is for!

`grep -v` does exactly what was described above: returns all the lines that does not have `(argument1)`. 

I'm not going to use *science* as my word in **journal.pbio.0020001.txt** because I tried that and can't even fit all the lines in a screenshot. Instead, we shall use the letter *e*, because *e* is very common and will still show how `grep -v` works. 

Here's the template:
```
grep -v (argument1) (argument2)
```
And here's example 1:
```
grep -v "e" journal.pbio.0020001.txt











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

Here's how it works for example 2, also using *e*: 
```
grep -v "e" 1468-6708-3-1.txt




        Introduction



          Study




          ] .
          findings.




          Analysis



        groups.
        YOL or YHL.


        Discussion



          Implications for clinical trials
          YHL.
          mortality.





        Conclusion




        poor?




```
Even more weird spacing. Hmm. That's odd. Perhpas we'll find a reason for it later in the quarter, or just by experimenting with it.

`grep -v` is incredibly useful in many scenarios, I just can't list them all out because I'm just a student learning about this stuff. Being able to omit certain words in a search though is helpful for filtering out bad/inaccurate results, and I can see `grep -v` being used for something like that.

---
### grep -f

It would be useful if we could use something other than a string to search for, wouldn't it? Well guess what, `grep -f`s got your back.

`grep -f` takes a file instead of a string for its `(argument1)`. Most commonly this is a text file, and that's what the `-f` stands for: file! What using a file instead of a word means is that the command `grep` will run for each line in that file.

Here's how it looks:
```
grep -f (argument1) (argument2)
```
Remember: `(argument1)` is a file, not a word. Just for `grep -f`.

Before we use it: let's create a text file to use. Here, I've created a new text file and called it `grepf.txt` which has two lines:
```
America
Europe
```

This text file resides in `techincal`. We will be using this file to search through **journal.pbio.0020001.txt**.

To use `grepf.txt` on **journal.pbio.0020001.txt**, we type in the following:
```
grep -f /c/Users/eugen/Documents/GitHub/docsearch/technical/grepf.txt journal.pbio.0020001.txt
        (SCI). North America and Europe clearly dominate the number of scientific publications
            North America and Europe clearly dominate the number of scientific
        represents North American and European publications far better than those of the rest of
        developing countries. For example, Latin America and China, although representing,
        much higher percentage than the increments reached by Europe (10%) and industrial Asia
        (26%). The percentage of global scientific publications from North America actually
        Publishing Trends in the Americas
        focusing on the Americas as a case study. Not surprisingly, there was a huge disparity in
        lion's share (84.2%), followed by Canada (10.35%). Latin America as a whole contributed
        1990 as a comparison, revealed that scientific publishing in Latin America increased the
        most rapidly in the Americas, far outpacing the United States and Canada (Figure 1).
        Canada and United States, the trend in Latin America has been an increase in relative
        research money available to researchers, Latin America actually out-published the United
        of publications per amount of money allocated to research and development in Latin America,
        demonstrate that such developing regions as Latin America are making substantial
        product (GDP) invested in science in Latin America throughout this 10-year period was only
        itself as compared with the GDP of Latin America as a whole. In fact, Albornoz (2001)
        concluded that, as a group, Latin America could afford to invest a much higher proportion
        of its resources in scientific research and development. Latin American investment in
        Among Latin American countries, there is a high degree of variability in publication
            development been increasing in Latin America while decreasing in United States and
        Explaining the Increase in Publishing Productivity in Latin America
        One potential explanation for the increase in scientific productivity in Latin America
        Latin America compared with the relatively flat increases in the United States and Canada,
        research and development has been increasing in Latin America while decreasing in the
        measure of scientific productivity is becoming more important in Latin America. Increased
        scientific collaborations among scientists in Latin America, Europe, and the United States
        may also have increased the relative number of publications in Latin America. In contrast,
        Scientific Impact from Latin America
        What, exactly, is the relative impact of such developing regions as Latin America on the
        For the top 20 ecological journals, the American subcontinents of South, Central, and
        North America accounted for 62% of the publications worldwide. Within the Americas,
        however, Latin America represented only 6%, while Canada and United States accounted,
        the top 11–20 (impact factors 3.28–2.47), the Latin American countries contributed nearly
        regions as Latin America are falling short of reaching the top journals. In contrast, the
        Interestingly, the proportion of publications from Latin America, the United States, and
        Nature , Latin America had 7% of the publications within the Americas
        American researchers are not shying away from the two top-ranked general science journals.
        from North America (73%) and Europe (21%) (ISI 2001b). No researcher working in a Latin
        American institution was included in the remaining 6%. Overall, these data indicate that
        the scientific output in the field of ecology in Latin America is having a relatively low
        they are the exception. Why, in general, do Latin American scientists often fail to reach
        The positive trends in scientific productivity in Latin America should not be
```
I'm sure theres an easier way to type the path to `grepf.txt`, but I like to use the absolute path just to be sure.

Notice how there aern't any *america*s or *europe*s. This is because grep is naturally case sensitive. To see how to ignore cases, scroll up until you hit **grep -i**.

Also notice how each line has to have **either** *America* or *Europe*. This is because `grep -f` runs each line in the `grepf.txt` file as it's own grep command. Because there were two lines in `grepf.txt`, the terminal ran grep twice, one for *America* and one for *Europe*. 

Let's do that one more time. I have created another file called `grepf2.txt` which looks like the following: 
```
Before 
After
```
Now let's try using `grep -f` with this file on **1468-6708-3-1.txt**
```
grep -f /c/Users/eugen/Documents/GitHub/docsearch/technical/grepf2.txt 1468-6708-3-1.txt
        income and education (data not shown). After adjusting for
        After adjustment for income and education, the difference
```
Well that's not a lot of lines. There's also no lines that have *Before* in them. Interesting.

In the end, `grep -f` is probably my favorite command here because it allows us to do multiple grep searches in one go. A very useful command that takes what would be multiple terminal commands and turns it into one. It even comes with the feature of reusability in the form of a new file that you can freely manipulate. Also the process of creating a new file and putting text in that file then using that new file in a command for another file seems very tech-savvy, and it makes me feel smart *pushes up glasses anime style*.


---
### grep -o

Probably the simplest one here in terms of results, but using `grep -o` will return only the word searched for from all the lines that have it. 
```
grep -o (argument1) (argument2)
```
Note: `(argument1)` is back to being a string here.

Suppose we want to find all the instances of only the word *science* in **journal.pbio.0020001.txt**:
```
grep -o "science" journal.pbio.0020001.txt

science
science
science
science
science
science
science
science
science
science
science
science
science
science
science
science
```
Yeah, it's literally just a bunch of *science*s. This could be useful for counting all the instances of a single word, but there is most definitely a better and easier command to use for that than manually counting them all. Perhaps we'll see it late in the quarter, or we already have.

Here's another use of it though, this time looking for "after" in **1468-6708-3-1.txt**:
```
grep -o "after" 1468-6708-3-1.txt
after
after
after
after
after
```

As we can see, there are exactly five lowercase *after*s in **1468-6708-3-1.txt**. Do what you will with that information.

There is, however, something special I want to cover with `grep -o`.

I initilly wanted to use this command as it's own section, but upon creating that section I realized I have no idea what is going on. Instead, you get to see the bonus section where I can show this off because I think it's cool. Presenting...

---
### grep -oE

Disclaimer: I really don't know much about this command, I got it from the website that I will link below.

`grep -oE` is like grep, but more specific. It utilizes something called "Regular Expressions" which sounds very, well, not regular.

Since I don't know too much about it, here's how one version of it looks:
```
grep -oE '\w*(argument1)\w*' (argument2)
```
With `(argument1)` being the string you want to use to search and `(argument2)` being the file.

What this version does is searches through `(argument2)` and returns all the words that either are or have `(argument1)` in them.

Here's me using it on **journal.pbio.0020001.txt** to find all instances of *scie* and any words that have *scie* in it:
```
grep -oE '\w*scie\w*' journal.pbio.0020001.txt
science
scientific
science
scientific
scientific
scientists
scientific
scientific
scientific
scientific
scientific
science
scientific
scientific
scientific
scientific
scientific
scientific
scientific
scientific
scientists
science
science
scientific
science
scientific
science
scientific
scientific
scientific
scientists
science
scientific
scientists
scientific
scientific
science
science
sciences
scientific
scientific
scientific
scientific
scientists
scientific
science
science
scientists
scientist
scientific
scientific
scientific
science
scientific
scientific
scientists
scientific
scientific
sciences
scientific
scientific
scientific
scientific
sciences
scientific
```

As you can see, not only is *science* returned, but *sciences*, *scientific*, *scientist*, and *scientists.* This grep version has returned all the words that have *scie* in it.

This is definitely above my pay grade, so I won't try to explain what any of the syntax means, but I do speculate that the `\w` part means something like "word" or "has word", and the `*` means all (if I recall correctly). The website states that `-E` sets the pattern to look for, which is this part `'\w*(argument1)\w*'`. 

I do know what the `-o` thing is though, that means only the word that has the `(argument1)`! See I learned something while making this.

---
### Where I got this all

Ok so belive it or not, I did not create these. Nor did I know all of them off the top of my head. I got them from this website:
http://www.compciv.org/recipes/grep/basics-of-grep/
that goes into further detail everything I described here, as well as `grep -oE`. 

All credit goes to them, except the money. That's mine.

And that concludes this tutorial. I hope you learned a lot about `grep` and how to use it. Now if you'll excuse me, I have procrastinating that needs to be done.

Thanks for reading!
