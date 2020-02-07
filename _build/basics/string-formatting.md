---
interact_link: content/basics/string-formatting.ipynb
kernel_name: python3
has_widgets: false
title: 'String Formating'
prev_page:
  url: /basics/strings
  title: 'Strings'
next_page:
  url: /data-structures/intro
  title: 'Data Structures'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---
# String Formatting

Concatenating strings can sometimes be cumbersome and hard to automate. If you need to include variables and/or values in your string, you may be better off using string formatting. We will use this technique more extensively later on.

There are a few ways to format strings. We will cover one of the ways introduced in Python 3. That is using the `string.format()` method.

This method treats everything contained in curly braces`{}` in the string as a replacement field, everything in and including the braces are replaced with the arguments of format in the output string.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('Hello {}, how are you?'.format('world'))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Hello world, how are you?
```
</div>
</div>
</div>



As you can see above, the blank curly braces were replaced with the string argument `'world'`.

Note that the method does not change the string itself but returns a new string.



You can make multiple replacements at a time if you have a string with multiple replacement fields:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('{}, {}, {}'.format(1, 2, 3))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
1, 2, 3
```
</div>
</div>
</div>



Sometimes you will want more control over how the arguments of format are placed into the string. There is a specific syntax for formatting which you can read in the [documentation](https://docs.python.org/3.4/library/string.html#format-string-syntax). We will cover a few examples.



## Specify Arguments by Position

If you want to specify the order in which the arguments of format are placed into the string, you can put numbers in the replacement fields to reference the positional arguments:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('{0}, {2}, {1}'.format(1, 2, 3))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
1, 3, 2
```
</div>
</div>
</div>



Note that this also allows you to repeat elements:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('{0}, {2}, {1}, {2}'.format(1, 2, 3))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
1, 3, 2, 3
```
</div>
</div>
</div>



## Specify Arguments by Name

You can also specify arguments by name, the arguments must then be presented as keyword arguments:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('You can find the point at position ({x}, {y}).'.format(x = 2, y = 6)) #Arguments with names 'x' and 'y'

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
You can find the point at position (2, 6).
```
</div>
</div>
</div>



## Specifying Numerical Types and Precision

To put it simply, when formatting numerical arguments the format specifier (to be placed in the replacement field) is of the structure:
`[argument_reference]:[width][.precision][type]`

Where
- `argument_reference` is the position of or name of the argument. 
- `width` specifies the minimum width that a replacement will take (look to the docs for alignment options)
- For floats `precision` can be seen as the number of decimal places.
- `type` specifies what type you want to display the number as. Multiple types exist for both integers and floats, but the most commonly used types are `d` for decimal integer and `f` for fixed point number (which you can use for floats)

Each of these parts of the format specifier are optional.



As a first example, lets display an integer:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('{:d}'.format(5))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
5
```
</div>
</div>
</div>



Now, lets see how the width affects the output:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('{:d}'.format(5)) #minimum width of 0
print('{:1d}'.format(5)) #minimum width of 1
print('{:2d}'.format(5)) #minimum width of 2
print('{:3d}'.format(5)) #minimum width of 3

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
5
5
 5
  5
```
</div>
</div>
</div>



As you can see the first 2 outputs are the same. That is because the output is of length 1.



If you want to display a float to 2 decimal places, specify precision:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('{:.2f}'.format(1.232435455))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
1.23
```
</div>
</div>
</div>



If you want to specify the position of the argument, include a reference to the argument position:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('{1:.3f}'.format(1.232435455, 5.35362)) #argument position of 1

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
5.354
```
</div>
</div>
</div>



## Including Curly Braces in Formatted String

If you want to include curly braces in a string you are formatting you can double them up:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('Format a {} while keeping {{}}'.format('string'))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Format a string while keeping {}
```
</div>
</div>
</div>



You can also enclose the replacement field in double braces:



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('{{{}}}'.format('Text inside braces'))

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
{Text inside braces}
```
</div>
</div>
</div>
