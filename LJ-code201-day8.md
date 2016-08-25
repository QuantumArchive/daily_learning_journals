# LJ Code 201 - Day 8

Today we had to be able to have a form on our cookie stand sales page that allowed us to submit new data and append the data to our current tables and recalculate the totals for each hour. This was where the extra time put into make the code more modular really helped. By returning actual DOM elements, we had pointers to those elements that we could act on or even remove later on. Events were a new thing though. It's not immediately intuitive how events are triggered. For instance, you put the submit event listener on the form html tag, but submit is relegated to a button. That's not clear why that is specifically done, but it works. Really the next challenge will be to be able to remove rows at will and recalculate them.