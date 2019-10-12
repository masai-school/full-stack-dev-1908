# Week 2 - Day 3

### Session 1

**SUBMISSION:**

- Download this file
- Fill the answers
- Place the file into the location `~/repos/cohort_2/submissions/<your_folder>/week_2/day_3/session1` 
- Push the file  back to the online repo

<u>Don't use the web browser or any online tool to answer these questions. Only refer to the notes and apply the basic concepts</u>

Sample Submission

1. Color
```
black
```
2. Font Size
```
14px
```
3. Background Color
```
white
```
4. IDs
```
#id1
#id2
#id3
```

The CSS for each problem is mentioned above the HTML Code

### FSD.W2.3.1_1

```css
p {
    font-size: 16px;
    color: green;
}
div {
    font-size: 20px;
}
div, p {
    color: red;
}
```

```
<div id="id1">
	First DIV
</div>
<p id="id2">
	First P
</p>
```

Fill the below property values for the `div` having `id1`

1. Color

```

```
2. Font Size

```

```

Fill the below property values for the `p` having `id2`

3. color


```

```
4. Font Size


```

```

### FSD.W2.3.1_2

```css
div.class1 {
    color: red;
}
p.class1 {
    color: green;
}
p.class2 {
    font-size: 10px;
}
div.class2 {
    font-size: 12px;
}
```

```html
<div id="id1" class="class1">
    First DIV
</div>
<div id="id2" class="class2">
    Second DIV
</div>
<p id="id3" class="class1">
    First Para
</p>
<p id="id4" class="class2">
    Second Para
</p>
```

Fill the below property values for the `div` having `id1`

1. Color


```

```

Fill the below property values for the `div` having `id2`

2. Font Size


```

```

Fill the below property values for the `p` having `id3`

3. Color


```

```

Fill the below property values for the `p` having `id4`

4. Font Size


```

```

### FSD.W2.3.1_3

```css
p + div {
    background-color: red;
}
.class1 + p {
    background-color: green;
}
```

```html
<div id="id1" class="class1">
	<p id="id2"></p>
	<div id="id3"></div>
</div>

<p id="id4"></p>

<div id="id5"></div>

<div id="id6" class="class1"></div>

<p id="id7"></p>

<p id="id8" class="class1"></p>

<p id="id9"></p>

<div id="id10"></div>

<div id="id11">
	<p id="id12" class="class1"></p>
	<p id="id13"></p>
	<p id="id14"></p>
	<div id="id15" class="class1"></div>
	<p id="id16"></p>
	<p id="id17"></p>
</div>

<p id="id18" class="class1"></p>
<p id="id19"></p>
<div id="id20"></div>
```

All the `div` tags whose background color will be `red`

1. IDs


```

```


All the `p` tags whose background color will be `green`

2. IDs


```

```

### FSD.W2.3.1_4

```css
div ~ p {
    background-color: red;
}
.class1 ~ div {
    background-color: green;
}
```

```html
<div id="id1" class="class1">
	<p id="id2"></p>
	<div id="id3"></div>
</div>

<p id="id4"></p>

<div id="id5"></div>

<div id="id6" class="class1"></div>

<p id="id7"></p>

<p id="id8" class="class1"></p>

<p id="id9"></p>

<div id="id10"></div>

<div id="id11">
	<p id="id12" class="class1"></p>
	<p id="id13"></p>
	<p id="id14"></p>
	<div id="id15" class="class1"></div>
	<p id="id16"></p>
	<p id="id17"></p>
</div>

<p id="id18" class="class1"></p>
<p id="id19"></p>
<div id="id20"></div>
```

All the `p` tags whose background color will be `red`

1. IDs


```

```

All the `div` tags whose background color will be `green`

2. IDs


```

```

### FSD.W2.3.1_5

```css
div > p {
    background-color: red;
}
.class1 > div {
    background-color: green;
}
```

```html
<div id="id1" class="class1">
	<p id="id2"></p>
	<div id="id3"></div>
</div>

<p id="id4"></p>

<div id="id5"></div>

<div id="id6" class="class1"></div>

<p id="id7"></p>

<p id="id8" class="class1"></p>

<p id="id9"></p>

<div id="id10"></div>

<div id="id11">
	<p id="id12" class="class1"></p>
	<p id="id13"></p>
	<p id="id14"></p>
	<div id="id15" class="class1">
        <div id="id16"></div>
    </div>
	<p id="id17"></p>
</div>

<p id="id18" class="class1"></p>
<p id="id19"></p>
<div id="id20">
    <p id="id21"></p>
</div>
```

All the `p` tags whose background color will be `red`

1. IDs


```

```

All the `div` tags whose background color will be `green`

2. IDs


```

```

### FSD.W2.3.1_6

```css
.class1 p {
    background-color: green;
}

#id20 p {
    background-color: red;
}
```

```html
<div id="id1" class="class1">
	<p id="id2"></p>
	<div id="id3"></div>
</div>

<p id="id4"></p>

<div id="id5"></div>

<div id="id6" class="class1">
    <p id="id7"></p>
    <p id="id8" class="class1"></p>
    <p id="id9"></p>
</div>

<div id="id10"></div>

<div id="id11">
	<p id="id12" class="class1"></p>
	<p id="id13"></p>
	<p id="id14"></p>
	<div id="id15" class="class1">
        <p id="id16"></p>
    </div>
	<p id="id17"></p>
</div>

<p id="id18" class="class1"></p>
<p id="id19"></p>
<div id="id20">
    <p id="id21"></p>
    <div id="id22">
        <p id="id23"></p>
        <div id="id24">
            <p id="id25"></p>
            <div id="id26">
                <p id="id27"></p>
                <div id="id28">
                    <p id="id29"></p>
                </div>
            </div>
        </div>
    </div>
</div>
<p id="id30"></p>
```

All the `p` tags whose background color will be `red`

1. IDs


```

```

All the `p` tags whose background color will be `green`

2. IDs


```

```