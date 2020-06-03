---
layout: post
title:      "I updated to Catalina and All HELL Broke Loose"
date:       2020-06-03 16:17:45 +0000
permalink:  i_updated_to_catalina_and_all_hell_broke_loose
---


So when I began my coding bootcamp I was directed to use the following <a href="https://github.com/learn-co-curriculum/environment-mac-os-catalina-setup"> directions </a> to set up my environment locally. 

Well, step one of the directions included installing <b>Command Line Tools</b>, but in order to install those tools I had to update my computer from <a href="https://www.apple.com/shop/product/D6377Z/A/os-x-mountain-lion"> OS X Mountain Lion </a> to <a href=https://www.apple.com/macos/catalina/> Catalina </a>.

Who knew this minor update would cause HAVOC on my life. Before the update, I was able to access my desktop and documents from my Finder application without any issues, even though all of my files were technically in my iCloud directory. For some reason, it did not matter and I was content with it that way. But after the upgrade, I guess my system recalibrated and I could no longer access my documents the way I used to. I had to find a way to access my documents through iCloud.

There was one problem though, when I went into my terminal and typed ``ls`` I realized that <b>iCloud was NOT an option!!!</b> I wanted to cry. I did not have enough memory on my Mac to move all the documents back locally. So, I spent an entire weekend searching for solutions on how I can access my documents again.  Then finally, I found an article on <a href="https://superuser.com/questions/827827/access-icloud-drive-via-terminal?newreg=50681ca1a1374f4497634c6f50f8098c"> Stack Overflow </a>

The solution was to create a link in my home directory to my iCloud drive and then create an alias to easy reference things within my iCloud. Sounded simple to me so I followed the Stack Overflow solution verbatim. 

First, I created a link in my home directory to my iCloud drive by using the following code:

```
cd ~
ln -s ~/Library/Mobile\ Documents iCloud
```

I was then able to type the following to get inside of my iCloud directory through terminal

```
 cd ~/iCloud 
```
Then I created an alias so that I can reference the specific folder obtaining my code. 

```
cd ~
ls -a
sudo nano .bash_profile
```

Entered my admin password.

Within the nano editor. I pressed esc to be able to edit, and using the keyboard, arrow key down to the bottom, I typed

``alias i="cd ~/iCloud/com~apple~CloudDocs/Documents" ``

Then I pressed Ctrl + O to save, and then entered, then pressed Ctrl + X to exit. 

Lastly, I typed alias i="cd ~/iCloud/com~apple~CloudDocs/Documents/" outside of the nano editor to set the alias variable. 

Later on in the day I opened another terminal and pressed ``i`` and guess what, it did not work! (I shed a tear)

So, I had to check what I was doing wrong, I googled: <i>"alias zsh: command not found: i .bash_profile" </i>

And found yet another <a href="https://stackoverflow.com/questions/28289131/aliases-in-bash-profile-not-working-properly"> Stack Overflow </a> solution.

According to Stack Overflow: 
<q><i>The default shell is bash shell on Mac OX. But if you have installed zsh, the default shell is zsh, when zsh shell starting, shell will find out the file named .zshrc, and execute the commands in .zshrc. </i></q>

<i>You can use echo $SHELL to see which shell bash is the default on your computer </i>


With that in mind, I went to my terminal and ran the following code and, of course, I got the following: 

```
-> echo $SHELL
/bin/zsh
```
so I followed the same steps as before but instead of putting the information inside of my bash_profile, I inserted into ``.zshrc``
like so:

```
cd ~
ls -a
sudo nano .zshrc
```

Entered my admin password.

Within the nano editor. I pressed esc to be able to edit, and using the keyboard, arrow key down to the bottom, I typed

``alias i="cd ~/iCloud/com~apple~CloudDocs/Documents" ``

Then I pressed Ctrl + O to save, and then entered, then pressed Ctrl + X to exit. 

Now every time I press ``i`` in my terminal I am able to go straight into my iCloud documents directory. In addition, I added another <a href="https://www.techradar.com/how-to/computing/apple/terminal-101-creating-aliases-for-commands-1305638"> alias </a> called "code" that takes me directly to my directory that holds most of my code.

Although it was a stressful weekend trying to fix my computer, these kinds of "errors" help with learning new ways of doing things. I now know how to create an <a href="https://www.techradar.com/how-to/computing/apple/terminal-101-creating-aliases-for-commands-1305638"> alias </a> on my computer to refer to things easier, faster, and more efficiently. I hope this can help someone else too.


This article/blogpost was originally posted <a href="https://dev.to/sincerelybrittany/day-2-100daysofcode-i-updated-to-catalina-and-all-hell-broke-loose-2h7n"> here </a>
