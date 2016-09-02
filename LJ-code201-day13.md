#Learning Journal - Day 13

Today, when I was working on storing user information to localStorage and pulling the data on a refresh, that you have to be careful about the final state of your data before passing it. For instance, because I rely on having an array of indexes to pull from so I can quickly access objects or dictionary items corresponding to the given index, then if I don't regenerate the pulled values, then eventually you reach a case where the entire index array has -1 and we get an infinite loop within my while condition because every value is -1. I realized this because my code kept breaking on the 7th refresh. Since we take out 3 items from the index array each refresh, it took the 7th refresh before the entire array had only -1. Again, methods that may be very modular may require a little bit more coding when passing pre-existing conditions to another part of your code or when starting from that point.

So basically, when I refresh, I want to make sure a new set of images are shown (this is due to the fact that after 25 clicks, no new images appear). That way I don't double count. But I don't want to count those images as viewed until actually viewed (the way I render images in normal flow is to generate an array of indexes and then calculate views and then render) so then I had to change up the render flow a little to accommodate storing my data. Overall, it reminds me that you have to always stress test your code before you submit. Fortunately I noticed the bug as I kept testing my code across refreshes.

Got an interesting talk from Mike. I feel a little bad because I discovered the bug during his presentation and my mind set into high gear to figure it out and fix. But from what I understood, he does product management and that comes with a lot of considerations before submitting your work. I definitely understand his sentiments that sometimes we can be so absorbed in our own worlds as developers we forget user experience entirely because things are intuitive to us. Certainly, I have an engineering mindset so I use intuition and experimentation and other tricks to figure things out, given some interface. Also, there were some practical reminders that were useful such as, unless you have something to contribute, you shouldn't be too critical. Certainly voice concerns, but show that you thought about the problem to show it's a concern and possible ways to circumvent it.

Now the real test for the week is to start thinking about a project....