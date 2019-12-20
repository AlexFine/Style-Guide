# Style & Push Guide
I wrote this style & push guide to maintain a high code quality in teams. I hope it can help others as well. 

## Push Guide
  To push any code make sure you can answer yes to the following five questions:

  <ol>
    <li> Are you proud of this commit? </li>
    <li> Does the code always work? </li>
    <li> Is it styled correctly? </li>
    <li> Is it an isolated change? </li>
    <li> Is the terminal error free? </li>
  </ol>

  A little more on each of these.

  <b>Are you proud of this commit? </b><br>
  As a team we have committed to a certain level of excellence. We don't believe in doing anything less than this level of excellence. For pushing code to the team server, ask yourself, is this code you're truly proud of? Does this code meet, and exceed the standards of our organization? Over time, over many commits, if the commits are shallow and poor, our code base and product will degrade. However, if the first question we always ask is "Am I proud of this?", our code base will continue to improve. <br>

  <b>Does this code always work? </b><br>
  Sometimes code will work in one environment, but not in another. Have you stress tested this code? If you have a timed function, have you tested if it works as well at 20 minutes as it does at 2?  <br>

  <b>Is it styled correctly? </b><br>
  Maintain style on a big repo is hard. It must be done one commit at a time. As soon we start to lapse the whole system is weakened. Make sure style is correct before pushing.   <br>

  <b>Is it an isolated change? </b><br>
  This is very important. All commits should be a specific change, not a general days' work. This way, if you fuck up and have to revert the change, you only have to revert what's broken, and not the other good code you wrote that works. It helps to isolate problems. <br>

  <b>Is terminal error free? </b><br>
  Remember Angular can reload a broken app, but it can't recompile one. Make sure your terminal is error free before pushing, or else someone who pulls might have their system break. <br>



 ## Style Guide
<b> Decompose </b><br>
Ensure all functions are properly decomposed
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
this.example_val = function {
	// Do calculations here
}
```

<p > <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
function decompose(){
	// Do calculations here
}

this.example_val = decompose();
```

<hr>

<b> Comment </b><br>
All functions have their purpose commented above. All non-obvious lines of code have their action commented.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
function sum_of_squares(a, b) {
  let ret = a*a;
  ret += b*b;
  return ret;
}
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
/* return the sum of two squares */
function sum_of_squares(a, b) {
  // square number a
  let ret = a*a;
  // Add square of a to square of b
  ret += b*b;
  // Return both values
  return ret;
}
```


<hr>

<b> If Else </b><br>
Normalize our syntax on if else statements.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
/* return if sum is even */
function is_sum_even(a, b) {
  // Check if sum is even
	if ((a + b) % 2 == 0)
  {
    return "Even";
  } else
  {
    return "Odd";
  }
}
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
/* return if sum is even */
function is_sum_even(a, b) {
  // Check if sum is even
  if ((a + b) % 2 == 0) {
    return "Even";
  } else {
    return "Odd";
  }
}
```


<hr>

<b> Naming JS </b><br>
All javascript is lowercase & abbreviated words.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
/* return if sum is even */
function IsSumEven(a, b) {
  // Check if sum is even
	if ((a + b) % 2 == 0) {
    return "Even";
  } else {
    return "Odd";
  }
}
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
/* return if sum is even */
function is_sum_even(a, b) {
  // Check if sum is even
  if ((a + b) % 2 == 0) {
    return "Even";
  } else {
    return "Odd";
  }
}
```



<hr>

<b> Naming CSS </b><br>
All CSS is lowercase & abbreviated words: with DASHES.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```css
.className {
  ...
}

.class_Name {
  ...
}
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```css
.class-name {
  ...
}
```


<hr>

<b> Avoid Globals </b><br>
Avoid global variables wherever possible.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
let global = 5;

// Example class
class example {
  public square;

  ngOnInit{
    // square global
    this.square = global*global;
  }
}
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
// Example class
class example {
  public square;

  ngOnInit{
    let local = 5;
    // square global
    this.square = local*local;
  }
}
```

<hr>

<b> Function Spacing </b><br>
Have one line in between functions.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
/* description */
function temp(){
  ...
}
/* description */
function temp2(){
  ...
}
/* description */
function temp3(){
  ...
}
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
/* description */
function temp(){
  ...
}

/* description */
function temp2(){
  ...
}

/* description */
function temp3(){
  ...
}
```


<hr>

<b> Proper Indenting </b><br>
Indent lines which serve a new purpose.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
/* print hi nine times and the number two once  */
function temp(){
for (let i = 0; i < 9; i++){
if (i == 2){
console.log(i)
} else { console.log("hi")}
}
}
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
/* print hi nine times and the number two once  */
function temp(){
  // Iterate 0 through nine
  for (let i = 0; i < 9; i++){
    // on the third item print 2
    if (i == 2){
    console.log(i)
    // Else print hi
    } else {
      console.log("hi")
    }
  }
}
```




<hr>

<b> New View New Class </b><br>
If we create a new view, create a new class, on a new page.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
// Class one
export class page1 implements OnInit{
  public page1info = ...;
  public page2info = ...;
}
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
// Class one
export class page1 implements OnInit{ ... }
```
```javascript
// Class two
export class page2 implements OnInit{ ... }
```


<hr>

<b> How to Issue </b><br>
Use issues in GitHub when you have a specific code improvement you need fixed. When an issue is described well, there is no ambiguity about what needs to be done. A good issue should have photos if necessary.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

Issue Name: Create login page <br>
Issue Description: Create a page for users to login on.

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

Issue Name: Fix navbar coloring <br>
Issue Description: Current navbar is colored dark gray, it should be a light gray. On hover the change should have an opacity of 0.8 as opposed to 0.6.





<hr>

<b> No Dead Code </b><br>
Don't leave useless code laying around.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
// Class one
// export class page1 implements OnInit{
//   public page1info = ...;
//   public page2info = ...;
// }

// function description
function something_helpful() { ... }
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
// function description
function something_helpful() { ... }
```


<hr>

<b> No Long Comments </b><br>
All lines of code should be under 100 characters. If longer decompose
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```javascript
//All the world’s a stage, And all the men and women merely players; They have their exits and their entrances; And one man in his time plays many parts, His acts being seven ages. At first the infant, Mewling and puking in the nurse’s arms; And then the whining school-boy, with his satchel And shining morning face, creeping like snail Unwillingly to school. And then the lover
```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```javascript
/*
  All the world’s a stage,
  And all the men and women merely players;
  They have their exits and their entrances;
  And one man in his time plays many parts,
  His acts being seven ages. At first the infant,
  Mewling and puking in the nurse’s arms;
  And then the whining school-boy,
  with his satchel And shining morning face,
  creeping like snail Unwillingly to school.
  And then the lover
*/
```

<hr>

<b> Code In Correct Category </b><br>
This comment is most appropriate for CSS coding, but can also be applied to HTML & JS code. We compartamentalize our code a lot. Make sure to write code in the appropriate section.
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```css
/*
  NET WORTH NUMBER
  ==============================================================================
*/
.global-btn{
  ...
}

```

<p> <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```css
/*
  RELATIVE GLOBALS
  ==============================================================================
*/
.global-btn{
  ...
}

```

<hr>

<b> Proximity – <a href="https://en.wikipedia.org/wiki/Principles_of_grouping#Proximity"> Link </a> </b><br>
Humans think items physically close together are related. Thus, add a line break between conceptually different variables, and group together conceptually similar variables. It makes code much more readable. 
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```python
# Iterate through each interval
    for i in range(len(intervals)):
        # Shares in this interval
        intShares = ownership_arr[intervals[i]]
        # End price (which is the closer price remember)
        end_price = price_arr[intervals[i]]
        # Start price
        start_price = price_arr[intervals[i+1]] 
```

<p > <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>

```python
# Iterate through each interval
    for i in range(len(intervals)):
        # Shares in this interval
        intShares = ownership_arr[intervals[i]]
        
        # End price (which is the closer price remember)
        end_price = price_arr[intervals[i]]
        # Start price
        start_price = price_arr[intervals[i+1]] 
```

<hr>


<b> Similarity – <a href="https://en.wikipedia.org/wiki/Principles_of_grouping#Similarity"> Link </a> </b><br>
Humans think items which look similar are related. Thus, when declaring variables in a list align equal signs if the variables are related, and keep naturally spaced if they're independent. 
<p ><span style="color:rgba(230, 50, 50, 0.8); font-weight:500;"> Bad </span> </p>

```python
# Prices
priceOne = 20
priceFiftyEight = 925
priceOneHundo = 1058

# Shares 
sharesOne = 24
sharesFiftyEight = 853

# Other 
date = '2018-01-29'
firstName = 'Alex'
```

<p > <span style="color:rgba(50, 230, 50, 0.8); font-weight:500;">  Good  </span></p>


```python
# Prices
priceOne        = 20
priceFiftyEight = 925
priceOneHundo   = 1058

# Shares 
sharesOne        = 24
sharesFiftyEight = 853

# Other 
date = '2018-01-29'
firstName = 'Alex'
```

<hr>

