---
layout: post
title:      "Understanding Iterators"
date:       2020-05-02 14:38:57 +0000
permalink:  understanding_iterators
---

## .map .each .find .select
Originally published at https://medium.com/@sincerelybr/understanding-iterators-8bd23c1f5f1c on May 1, 2020.

Today I had my first project review and I have to say, I struggled. I got so nervous and I definitely understand imposter syndrome now! I knew what I wanted to say but at the time I could not think of any words to convey it. In addition, I struggled to understand or comprehend what was required from me while under the pressure. I know this is something I will need to work on, but for now, I want to review an area I needed to do more research on ITERATORS.

What are iterators:

According to GeeksforGeeks, the word iterate means doing one thing multiple times and that is what iterators do. Sometimes iterators are termed as the custom loops.

1. “Iterators” is the object-oriented concept in Ruby.

2. In more simple words, iterators are the methods which are supported by collections(Arrays, Hashes etc.). Collections are the objects which store a group of data members.

3. Ruby iterators return all the elements of a collection one after another.

4. Ruby iterators are “chainable” i.e adding functionality on top of each other.

Background:
During my project review, I was asked to create a class method that took an input as an argument and to see if the instance variable started with the input. Like so:

def self.get_articles(input)
    @@all.map { |x| x.title.start_with?(input)}
end

Sounds simple right? WRONG. I could not THINK. I was struggling with knowing if .map or .each was required. So I did some research on Iterators and this is what I discovered.

.EACH vs .MAP

Well use the following array as an example: array = [2, 4, 6]

With .map you are essentially creating a new array without manipulating the original array. So if I ran the following in irb:

array.map { |x| x * 3}

The output is a new array and the original array of [1, 2, 3] would not be affected. The output would be:
[6, 12, 18]

Unlike .each, which will return the same array, like so

array.each do |x|
      x * 3
 end
 
.each always returns the original, unchanged object. So the output would be the following:

[2, 4, 6]

So when working with arrays and iterators it is important to note that
.map gives you a new array with updated information, while .each does not edit the original array.


Other important iterators: .find and .select

.FIND

This method returns the first element in the array for which the block is not false, meaning that it meets the criteria. So if we had an array like so arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

arr.find {|a| a > 5} 

The above returns the first element greater than 5 and `nil` if none satisfies the condition. So the output would be: 6
Now lets assume you had the following array = [“a”, “b”, “c”, “d”] and you wanted to find where in the array the “c” was located. Luckily, you can also use the .find method to search by key and value like so:

array.find {|key, value| key == "c"} 

It returns an Array of the first match [key, value] that satisfies the condition and nil otherwise. So the output would be 

[“c”, 3]

.SELECT

Just as it’s name says, with this method you can select a subset of your original array, based on some criteria. As you are selecting only certain elements, the return data will still be an array, but with less or equal number of elements than your original array. So if we had the following

array = [1, 2, 3, 4, 5]
array.select { |num|  num.even?  }  

It returns a new array containing all elements of the array for which the given block returns a true value. So the output would be the following.

[2, 4]

.find gives you the first item to match your criteria and .select gives you a new array with all elements that fit your criteria.
My research on iterators has only begun as there are many others I want to learn now. Such as:

Times Iterator
Upto Iterator
Downto Iterator
Step Iterator
Each_Line Iterator# Enter your title here

The content of your blog post goes here.
