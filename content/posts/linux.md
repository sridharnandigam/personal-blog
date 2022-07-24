---
title: "Save Your Old Laptop"
date: 2022-07-22T09:20:09-05:00
draft: false 
tags: 
    - "linux"
    - "fun stuff"
---

Do you have an old laptop lying around that needs just one more Windows update to end it all? Well, like so many others, I implore you to
check out Linux. It's the perfect operating system to bring any PC back to life. There are a wide variety of distros available to choose from based on how much
setup you want to do and how "light" you need it to be. 

At first, I tried to install Ubuntu as it seemed the safest option. However, I ran into a multitude 
of installation issues and decided to switch to Debian. I eventually realized that the cause was an HDD that was at the end of its lifecycle. To save
yourself a lot of hassle, it's probably worth it to check how well your hardware components are doing. You don't need an OS installed to do this. Simply look up your 
computer's model and run a quick diagnostics test. 

In my case, my HDD was too old and slow and I opted to replace it with a faster SSD with a larger storage space. 
However, it may be worth switching to an SSD either way if you are trying to revive an old laptop. SSDs allow for significantly faster boot up times and may be just what you need to make your laptop feel a little bit faster. 

I've been a Linux user since this January and I've loved it. I wanted to make this PC feel like it was truly mine and that was enough to drive me to explore many new 
things. I personalized my terminal, learned to use Vim, set up a Git server, learned some networking as I set up ssh with ngrok, coded some handy CLI tools to make
my life easier, and downloaded some awesome anime wallpapers. As a developer, I can say that coding with Linux has been so much easier and more fun than my Windows 
PC. Most of the world uses Linux and, more often than not, you'll find that softwares and tools are easier to install on Linux.

Before I knew it, I was using this older laptop more than my "main" laptop for almost everything. It just felt...clean. I knew every app that was installed and there
 were no annoying surprise updates or reminders to update. Whenever something went wrong, I could just look up how to fix it and most of the time the solution was a
  few commands away. 
  
The only main issue I ran into was the fact that the hardware of my laptop was severely outdated, leading to performance
 issues and crashes with resource intensive programs. However, I definitely plan on fixing that soon by getting a decent computer and immediately installing Linux. It 
 will probably be fun to try a "harder" distro like Arch and get my hands dirty.

So don't throw away a perfectly good laptop. It might have more potential than you realize.

Pro tip: I learned this the hard way, but it may be a good idea to add something like this to your .bashrc file:
```
alias rm="rm -I"
```
If you ever screw up and accidentally delete files like I did, there is SOME chance of recovering deleted files from your SSD using the photorec tool or other tools
online. However, it's best not to take that chance. Back up your files and add the above snippet to your bash script so that it confirms the deletion of files because
a mistyped "rm -rf" can really ruin your day.
