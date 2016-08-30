#Learning Journal - Day 11

Today, we got to mess around with event listeners on lists this was pretty cool to see how we can use click to gather statistics like that. Really, the world is becoming a wider and wider place. Another thing that was cool was getting to listen to the speaker today. As someone who prefers doing the analysis and coding, it's good to see things from the perspective of the management. Heck, one day I may be manager and have to be able to know how to lead a team. Again, the soft skills really come into play more and more in business. I wonder if we'll learn more about the SCRUM process later, think it would be valuable. Today, also tried maybe doing an unorthodox method for keeping track of clicks and views...I write this hear to hash out my thoughts and my personal reasonings. I find it sometimes difficult to articulate code in way that makes sense to me.

Basically, we want to make sure that we don't produce repeating images on the list that we present to the user for selecting an image. Additionally, we want to make sure we don't show any of those three images in the next round of selections after they pick an image. One way to do this is generate an array of size 3 that contains non-repeating image paths. This would require you to make a while loop that builds this array by using indexOf to check if any new images you may consider inputting to this array to see if it already exists there. You would then use this array and loop through the paths to produce your table.

```javascript
function buildArray(oldArray) {
  var k = 0;
  var random = generateRandom();
  var newArray = [];
  while(k < 3) {
    if (oldArray[random].indexOf(objectArray[random].path) === -1 && newArray.indexOf(objectArray[random].path)) === -1) {
      newArray.push(objectArray[random]path);
      objectArray.totalViews += 1;
      k += 1;
    } else {
      random = generateRadom();
    }
  }
  return newArray;
}
```

My problem with this approach is using indexOf means you're always looping through your array and comparing each element with each selected candidate. This tends to get costly as your newArray gets large. Also, to be consistent when counting clicks, you would need to get the source image path and loop through your array of objects and match the path and increment that click variable. This again is more looping, potentially up to the size of the array.

So to circumvent this, I keep an array of indexes. Basically, when I generate my array of objects from the image names, I produce an index array that goes [0,...,N]. When I generate a random number, I then check against the index array and if they match, put that value into my new array and change the value in the index array to -1. Then as you find more random values, only grab values that don't return -1:

```javascript
indexArray = [0, 1, 2, 3, 4, -1, 6, 7, 8, 9, 10];
newArray = [5];
```

So above, we grabbed index 5 which is 5 and we can't grab this again. After we build our array of unique values, we leave the index array with the -1 values in place. So when we generate a new list, we won't pick those values. After we regenerate, we take the array with our old indexes and return them to the index array. Again, maybe my method is a little more convoluted, but it minimizes looping and comparing through arrays and accesses arrays immediate based on the index. The trick is to making sure you are consistent and that way you can always call any array and be sure you're accessing the correct object given those indexes you saved. Again, this is just a personal method I came up with to avoid looping and I know that it's still fairly modular code. Once I generate the array of objects and add however many image files, I can consistently always get unique indexes and from there, build out the image list.

Whew...that was long but sometimes it's best to hash out why you went a certain route. I certainly am able to understand what I did a little better.
