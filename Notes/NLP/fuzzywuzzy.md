# fuzzywuzzy 介绍

In this tutorial, you will learn how to approximately match strings and determine how similar they are by going over various examples.

### Python exact matching

```python
Str1 = "Apple Inc."
Str2 = "Apple Inc."
Result = Str1 == Str2
print(Result)
```
output
```python
True
```
 <br /> 
In this case, the variable Result will print True since the strings are an exact match (100% similarity), but see what happens if the case of Str2 changes:

```python
Str1 = "Apple Inc."
Str2 = "apple Inc."
Result = Str1 == Str2
print(Result)
```

output
```python
False
```
<br /> 

To solve this:
```python
Str1 = "Apple Inc."
Str2 = "apple Inc."
Result = Str1.lower() == Str2.lower()
print(Result)
```
output:
```python
True
```
---

### The Levenshtein Distance
The Levenshtein distance (also called edit distance) is a metric to measure how apart are two sequences of words. In other words, it measures the _**minimum number**_  of edits that you need to do to change a one-word sequence into the other. 
```python
Str1 = "Apple Inc."
Str2 = "apple Inc"
Distance = levenshtein_ratio_and_distance(Str1.lower(),Str2.lower())
print(Distance)
Ratio = levenshtein_ratio_and_distance(Str1.lower(),Str2.lower(),ratio_calc = True)
print(Ratio)
```
output 
```python
The strings are 1 edits away
0.9473684210526315
```
---

### The fuzzywuzzy package
FuzzyWuzzy has a ratio function that computes the standard Levenshtein distance similarity ratio between two sequences.

```python
from fuzzywuzzy import fuzz
Str1 = "Apple Inc."
Str2 = "apple Inc"
Ratio = fuzz.ratio(Str1.lower(),Str2.lower())
print(Ratio)
```
output:
```pyhon
95
```
#### 1. Substring  matching
```python
Str1 = "Los Angeles Lakers"
Str2 = "Lakers"
Ratio = fuzz.ratio(Str1.lower(),Str2.lower())
Partial_Ratio = fuzz.partial_ratio(Str1.lower(),Str2.lower())
print(Ratio)
print(Partial_Ratio)
```
output:
```python
50
100
```
#### 2. different order matching
The fuzz.token functions have an important advantage over ratio and partial_ratio. They tokenise the strings and preprocess them by turning them to lower case and getting rid of ***_punctuation_***. In the case of  ***__fuzz.token_sort_ratio()__***, the string tokens get sorted alphabetically and then joined together. After that, a simple fuzz.ratio() is applied to obtain the similarity percentage.

```python
Str1 = "united states v. nixon"
Str2 = "Nixon v. United States"
Ratio = fuzz.ratio(Str1.lower(),Str2.lower())
Partial_Ratio = fuzz.partial_ratio(Str1.lower(),Str2.lower())
Token_Sort_Ratio = fuzz.token_sort_ratio(Str1,Str2)
print(Ratio)
print(Partial_Ratio)
print(Token_Sort_Ratio)
```
output:
```python
59
74
100
```
#### 3. different order and length matching
***__fuzz.token_set_ratio() __***

```python
Str1 = "The supreme court case of Nixon vs The United States"
Str2 = "Nixon v. United States"
Ratio = fuzz.ratio(Str1.lower(),Str2.lower())
Partial_Ratio = fuzz.partial_ratio(Str1.lower(),Str2.lower())
Token_Sort_Ratio = fuzz.token_sort_ratio(Str1,Str2)
Token_Set_Ratio = fuzz.token_set_ratio(Str1,Str2)
print(Ratio)
print(Partial_Ratio)
print(Token_Sort_Ratio)
print(Token_Set_Ratio)
```
output:
```python
57
77
58
95
```
#### 4. process
The fuzzywuzzy package has a module called process that allows you to calculate the string with the highest similarity out of a vector of strings.

```python
from fuzzywuzzy import process
str2Match = "apple inc"
strOptions = ["Apple Inc.","apple park","apple incorporated","iphone"]
Ratios = process.extract(str2Match,strOptions)
print(Ratios)
# You can also select the string with the highest matching percentage
highest = process.extractOne(str2Match,strOptions)
print(highest)
```
output
```python
[('Apple Inc.', 100), ('apple incorporated', 90), ('apple park', 67), ('iphone', 30)]
('Apple Inc.', 100)
```




