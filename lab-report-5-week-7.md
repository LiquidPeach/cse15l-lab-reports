# Week 7 Lab Report

## **PART 1**
---

For part 1 this lab, I was instructed to give the shortest set of `vim` commands to perform a certain task. The task I will complete is changing the name of the `start` parameter to `base` in the `DocSearchServer.java` file from a previous lab. 

The shortest line of commands I found is this: `:[range]s/[old]/[new]`. `s` will substitute one word with another, and `[range]` will command it to search the file from a given range for every instance of the word to be replaced. Here is how this command sequence can be used for the lab:

In Normal Mode, enter `:13,23s/start/base`

![Image](screenshots/lab4/before.png)

After hitting `<Enter>` every instance of `start` from line 13 to 23 should be replaced with `base`.

![Image](screenshots/lab4/after.png)

## **PART 2**
---
After performing the task I did in part 1 of the lab on my local machine and using Visual Studio Code to edit the code and`scp` to send it to my remote server to run it, it took approximately 25 seconds to finish. To compare, it only took 10 seconds to finish editing and runnning the program when I was already logged into the remote server. I did not have any difficulties performing the tasks but it was tedious navigating from the local to the remote server and making sure the correct folders and files copied over in the right directory.

If I had to wor on a program that I was running remotely, I would rather edit it on the remote server using `vim`. It is easier for me and it takes less time than going back and forth from my local and remote servers just to share the edited program.

The task would preferably be easy to do in a few commands if I were to always use this method. I imagine if editing the code using `vim` becomes to strenuous of a task then I would just edit the code on my local machine and copy it over to the remote. 