---
interact_link: content/basics/comments.ipynb
kernel_name: python3
has_widgets: false
title: 'Comments'
prev_page:
  url: /basics/variables
  title: 'Variables'
next_page:
  url: /basics/types
  title: 'Type Conversion'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---
# Comments
<!--- Add a section about using comments as headers? -->

Comments make it possible to write messages in our scripts that are not to be read by the computer, but fellow humans.

In Python you can write an in-line comment by using the `#` symbol. Everything after this symbol until the end of the line will be considered a part of the comment and the computer will not read this as code. For example:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('Not a comment') # This is a comment print('Part of the comment')

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Not a comment
```
</div>
</div>
</div>



Comments can be useful for explaining what a script/section of a script does or why you've made the choices you have made in a particular line. It is not normally necessary to explain what each line of code does, as it should be easy enough to read the actual code to determine this.



## Commenting on a Line of Code

If you want to comment about a particular line of code it is common practice to put the comment at the end of that line of code: <!--- construct better examples -->



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('some code') #comment on code

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
some code
```
</div>
</div>
</div>



If the comment is too long to fit on the line, you can write the comment on a separate line above the code: 



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
#Comment line that is too long to fit on the end of the line of code
print('some code')

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
some code
```
</div>
</div>
</div>



## Commenting Out Portions of Code

Sometimes you may want to comment out code to temporarily remove it from the program without deleting it. It is especially useful when you want to isolate code snippets during debugging or print statements used in debugging during normal runtime. For example: <!--- Need to add debugging into the glossary --> <!--- Show example of this?-->



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
var1 = 3
var2 = var1

#print('Variable 1 is', var1)
#print('Variable 2 is', var2)

var1 = 2

#print('')
print('Variable 1 is', var1)
print('Variable 2 is', var2)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Variable 1 is 2
Variable 2 is 3
```
</div>
</div>
</div>
