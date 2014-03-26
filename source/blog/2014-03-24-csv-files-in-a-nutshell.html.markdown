---
title: CSV files in a Nutshell
date: 2014-03-24 16:18 UTC
tags: dev, code, csv
---

It has been a whirlwind of activity since the start of gSchool. We have covered git, OOP, TDD, and of course, Ruby. We have been given a number of simple problems to solve, much of which we are left to fend for ourselves, scouring the ruby-docs, the people sitting next to us, and google. Having stumbled through a few problems that required the use of a csv file, I thought it would be a good time to finally understand the basics of Ruby's CSV class, since you know... I hacked my way through 3 problems requiring csv an I *still* didn't know what was going on.

So I started simply, worked through many lines of IRB code and realized I needed to do just a few things:

1. Open the csv file
2. Get information from the csv file
3. Edit the csv file

I found out that these three things where all I needed to do. That being said, they are also ordered by increasing level of difficulty, so bear with me.

### Opening csv files

This one is pretty straight forward. At least I am going to show a very straightforward way. This is assuming that your file has headers and is not too big... 

~~~ ruby
@file = CSV.read(@filepath, headers: true)
~~~

This is basically returning a CSV object to `@file`, allowing us to manipulate it as we fancy.

### Getting Information from a CSV Object

This is the fun part. This CSV object essentially is an array of hashes. The 'rows' are arrays, and the 'columns' are hashes.

Let's take the following csv file:

~~~ 
Id,Name,Sign,Favorite Color
1001,Cory,Sagittarius,Orange
1002,Bob,Cancer,Blue
1003,Jane,Aries,Yellow
~~~

When the file is read in via the `read` method, it creates this array of hashes with the headers as the `key` in a key-value pair. Each row is represented by a standard 0-index array. We need to note that each row is actually a CSV::Row class, but we can access its information like any other hash.

For example:

~~~ ruby
@file[0]['Id'] # => "1001"
@file['Id'][0] # => "1001" (same as above)
@file[2]['Favorite Color'] # =>  returns "Yellow"
~~~

Using just `@file[1]` returns a CSV::Row object (hash) with values from that row, and `@file['Name']` returns an array of values form that column. We can even return an array of headers by calling the headers method: `@file.headers`.

We can also easily iterate through rows with an each method like below. 

~~~ ruby
@file.each do |row|
  puts "#{row['Name']}'s favorite color is #{row['Favorite Color']}"
end

# =>

# Cory's favorite color is Orange
# Bob's favorite color is Blue
# Jane's favorite color is Yellow
~~~

Great, we can now get the information from the file, but what if want to add a row? What about deleting, or editing information?

### Editing the CSV file

We have to make a distinction here. We can edit and modify the `@file` as much as we would like, but we are just editing the 'instance' of a CSV object. If we want to change the `file.csv` itself, we will have to write to that file. Let's take a look at how we can add and edit the instance first.

#### Adding a row

In this case, it is pretty simple. We just need to shovel an array into our CSV instance. This may seem a bit odd, because we know that a row in a CSV object is a special hash. This is the magic of the CSV object. We know that in the file itself is just a bunch of values separated by a comma. So the `<<` method lets us just shovel that in there.

~~~ ruby
@file << [1004,Marta,Scorpio,Green]
~~~

After adding the row above, our csv instance looks like this:

~~~
Id,Name,Sign,Favorite Color
1001,Cory,Sagittarius,Orange
1002,Bob,Cancer,Blue
1003,Jane,Aries,Yellow
1004,Marta,Scorpio,Green
~~~

#### Editing Values

If you though that was easy, check this out!

~~~ ruby
@file[0]['Favorite Color'] = "Red"
~~~

That is it! You can iterate through a row to change all of its values, but I won't cover that here... I think you can figure that one out on your own!

#### Deleting a Row or Column

Once again, the CSV class makes this easy. We can just call the `delete` method on the CSV class and pass it a row *OR* a header. Take a look at these two statements below:

~~~ ruby
@file.delete(1)
@file.delete('Id')
~~~

The first command deletes the second row of our csv instance. This works just like an array, so `index 0` is our first row. Due to the magic of the CSV file, we can pass it a header name, deleting all the info in that column! After the previous two commands, our csv instance will look like this:

~~~
Name,Sign,Favorite Color
Cory,Sagittarius,Orange
Jane,Aries,Red
Marta,Scorpio,Green
~~~

Pretty cool, huh?! We have seen how easy it is to delete, change, and add information our instance here. But it is only our instance. Our little ol' file.csv (or whatever it is called) is still out there, unchanged, unaffected by our edits. Let's remedy that.

#### Writing Back to our csv file

This isn't so difficult either, but it is a step we have to remember. There are many way one can do this step, but I have chosen just one to show. Note that is is a File class rather than csv... it is no problem. We just need to get the text to the file. Take a look at the code:

~~~ ruby
File.open(@filepath,"w") do |file|
  file.puts(@file)
end
~~~

### Wrap Up

So while this may not be the best way, it is a simple way to get into the basics of working with a CSV file in Ruby. We didn't cover how a file is opened or closed, or passing in an IO wrapped file to the open method (because I don't yet understand it). We did however cover the basics that should help you work with csv files a bit more easily.

A special thanks to Darko, as much of my understanding came from a [tutorial by Darko Gjorgjievski](http://www.sitepoint.com/guide-ruby-csv-library-part-2/)


