# Creating Lists

Lists are used to group together related pieces of information so they are clearly associated with each other and easy to read. In modern web development, lists are workhorse elements, frequently used for navigation as well as general content.

Lists are good from a structural point of view as they help create a well-structured, more accessible, easy-to-maintain document. They are also useful because they provide specialized elements to which you can attach CSS styles. Finally, semantically correct lists help visitors read your web site, and they simplify maintenance when your pages need to be updated.

###The three list types

There are three list types in HTML:

- unordered list — used to group a set of related items in no particular order
- ordered list — used to group a set of related items in a specific order
- description list — used to display name/value pairs such as terms and definitions

Each list type has a specific purpose and meaning in a web page.

##Unordered lists

Unordered (bulleted) lists are used when a set of items can be placed in any order. An example is a shopping list:

* milk
* bread
* butter
* coffee beans

Although the items are all part of one list, you could put the items in any order and the list would still make sense:

* bread
* coffee beans
* milk
* butter


You can use CSS to change the bullet to one of several default styles, use your own image, or even display the list without bullets — we'll look at how to do that in the Styling lists and links article.

###Unordered list markup

Unordered lists use one set of **ul** tags wrapped around one or more sets of **li** tags:
```
<ul>
  <li>bread</li>
  <li>coffee beans</li>
  <li>milk</li>
  <li>butter</li>
</ul>
```

## Ordered lists

Ordered (numbered) lists are used to display a list of items that should be in a specific order. An example would be cooking instructions:

1. Gather ingredients
2. Mix ingredients together
3. Place ingredients in a baking dish
4. Bake in oven for an hour
5. Remove from oven
6. Allow to stand for ten minutes
7. Serve


If the list items were moved around into a different order, the information would no longer make sense:

1. Gather ingredients
2. Bake in oven for an hour
3. Serve
4. Remove from oven
5. Place ingredients in a baking dish
6. Allow to stand for ten minutes
7. Mix ingredients together


Ordered lists can be displayed with several sequencing options. The default in most browsers is decimal numbers, but there are others.



### Ordered list markup

Ordered lists use one set of **ol** tags wrapped around one or more sets of **li** tags:

```
<ol>
  <li>Gather ingredients</li>
  <li>Mix ingredients together</li>
  <li>Place ingredients in a baking dish</li>
  <li>Bake in oven for an hour</li>
  <li>Remove from oven</li>
  <li>Allow to stand for ten minutes</li>
  <li>Serve</li>
</ol>
```

#### Beginning ordered lists with numbers other than 1

A common requirement in ordered list usage is to get them to start with a number other than 1 (or i, or I, etc.). This is done using the start attribute, which takes a numeric value (even if you're using CSS to change the list counters to be alphabetic or Roman). This is useful if you have a single list of items, but need to break up the list with a note or other related information. For example, we could do this with the previous example:

```
<ol>
  <li>Gather ingredients</li>
  <li>Mix ingredients together</li>
  <li>Place ingredients in a baking dish</li>
</ol>
 
<p>Before you place the ingredients in the baking dish, preheat the oven to 
180 degrees centigrade/350 degrees fahrenheit in readiness for the next step.</p>
 
<ol start="4">
  <li>Bake in oven for an hour</li>
  <li>Remove from oven</li>
  <li>Allow to stand for ten minutes</li>
  <li>Serve</li>
</ol>
```


This gives the following result:

1. Gather ingredients
2. Mix ingredients together
3. Place ingredients in a baking dish

Before you place the ingredients in the baking dish, preheat the oven to 180 degrees centigrade/350 degrees fahrenheit in readiness for the next step.

4. Bake in oven for an hour
5. Remove from oven
6. Allow to stand for ten minutes
7. Serve


Note that this attribute was deprecated in HTML 4, so it will prevent your page from validating if you are using an HTML4 strict doctype. If you want to make use of such functionality in an HTML4 strict page, and it absolutely has to validate, you can do it using CSS Counters instead. Fortunately, however, the start attribute has been reinstated in HTML5.

##Description lists

Description lists (previously called definition lists, but renamed in HTML5) associate specific names and values within a list. Examples might be items in an ingredient list and their descriptions, article authors and brief bios, or competition winners and the years in which they won. You can have as many name-value groups as you like, but there must be at least one name and at least one value in each pair.

Description lists are flexible: you can associate more than one value with a single name, or vice versa. For example, the term "coffee" can have several meanings, and you could show them one after the other:

```
coffee
  
  a beverage made from roasted, ground coffee beans 
  a cup of coffee
  a social gathering at which coffee is consumed
  a medium to dark brown colour
  
```
Or, you can associate more than one name with the same value. This is useful to show variations of a term, all of which have the same meaning:

```
soda
pop
fizzy drink
cola

  a sweet, carbonated beverage
```

###Description list markup

Description lists use one set of **dl** tags wrapped around one or more groups of **dt** (name) and **dd** (value) tags. You must pair at least one **dt** with at least one **dd**, and the **dt** should always come first in the source order.

A simple description list of single names with single values would look like this:
```
<dl>
  <dt>Name</dt>
  <dd>Value</dd>
  <dt>Name</dt>
  <dd>Value</dd>
  <dt>Name</dt>
  <dd>Value</dd>
</dl>
```

This is rendered as follows:

```
Name
  Value
Name
  Value
Name
  Value
```

In the following example, we associate more than one value with a name, and vice versa:

```
<dl>
  <dt>Name1</dt>
  <dd>Value that applies to Name1</dd>
  <dt>Name2</dt>
  <dt>Name3</dt>
  <dd>Value that applies to both Name2 and Name3</dd>
  <dt>Name4</dt>
  <dd>One value that applies to Name4</dd>
  <dd>Another value that applies to Name4</dd>
</dl>
```

That code would render like this:

```
Name1
  Value that applies to Name1
Name2
Name3
  Value that applies to both Name2 and Name3
Name4
  One value that applies to Name4
  Another value that applies to Name4
```

###Choosing among list types

When trying to decide what type of list to use, ask yourself two simple questions:

1. Am I defining terms or associating other name/value pairs?
    * If yes, use a description list.
    * If no, don't use a description list.
2. Is the order of the list items important?
    * If yes, use an ordered list.
    * If no, use an unordered list.


###HTML list advantages

* Flexibility: If you have to change the order of the list items in an ordered list, you simply move around the list item elements; when the browser renders the list, it will be properly ordered.

* Styling: Using an HTML list allows you to style the list properly using CSS. The list item tags **li** are different from the other tags in your document, so you can specifically target CSS rules to them.

* Semantics: HTML lists give the content the proper semantic structure. This has important benefits, such as allowing screen readers to tell users with visual impairments that they are reading a list, rather than just reading out a confusing jumble of text and numbers.

    
To put it another way, don't code list items using regular text tags. Using text instead of a list makes more work for you and can create problems for your document's readers. So if your document needs a list, you should use the correct HTML list format.

##Nesting lists

An individual list item can contain another entire list, called a nested list. It is useful for things like tables of contents that contain sub-sections:

```
1. Chapter One
    a. Section One
    b. Section Two
    c. Section Three
2. Chapter Two
3. Chapter Three
```

To reflect that in the code, the entire nested list is contained inside the first list item. The code looks like this:

```
<ol>
  <li>Chapter One
    <ol style="list-style-type: lower-alpha;">
      <li>Section One</li>
      <li>Section Two </li>
      <li>Section Three </li>
    </ol>
  </li>
  <li>Chapter Two</li>
  <li>Chapter Three  </li>
</ol>
```

Note that we have used the **list-style-type: lower-alpha** CSS property to sequence the nested list with lower-case letters instead of decimal numbers.

Nested lists are quite useful, and often form the basis for navigation menus, as they are a good way to define the hierarchical structure of the web site. They are also very flexible, as either ordered or unordered lists can be nested inside either ordered or unordered list items. For an example of nesting unordered lists within an ordered list, see "Choosing among list types" above.

Theoretically you can nest lists to any level you like, although in practice it can become confusing to nest lists too deeply. For very large lists, you may be better off splitting the content up into several lists with headings instead, or even splitting it up into separate pages. A good rule of thumb is, don't nest lists deeper than three levels.


##Exercise questions

1. What are the three types of HTML list?
2. When would you use each type of list? How would you choose between them?
3. How do you nest lists?
4. Why should you use CSS rather than HTML to style your lists?


# Styling HTML Lists

Many web page elements can be forgiving in terms of design — if they aren't "just right" it doesn't matter too much. With lists  it's a different story; if you don't get them right, you can cause some serious problems for people trying to use your website.

Links in particular have some key style requirements and user expectations. Poorly styled links can ruin the user experience on a website, as people have to stop and think about where to click. In the worst case, a user might not even be able to tell which items on the page are actually links!

In this article we'll look at the core skills you need to create robust list and link styles. We'll also discuss some ways to avoid key pitfalls of these elements and produce a final result that will work across different browsers, and be accessible to users with disabilities.

###Styling Lists

First, we'll go through the basics of styling lists with CSS, and then move on to look at some more advanced techniques.

####Basic bullets and numbers

The fundamental thing to consider when creating a list style is what form of bullet or numbering you want to use. You might also choose to remove the bullets or numbers completely. As you learned in the HTML Lists article, there are many options available, set using the CSS list-style-type property.

For example, to set all unordered lists on your site to use square bullets, use this CSS:
```
ul li {
  list-style-type: square;
}
```

That will produce something like:

![Screenshot of a list with square bullets](https://static.webplatform.org/w/public/6/66/square-b.gif)

Figure 1: Unordered list with square bullets.

Some common list types:

![Screenshot of some common list types.](https://static.webplatform.org/w/public/f/fe/referenc.gif)

Figure 2: Common list types.

Note that the bullets and numbers will be rendered using the color which is set for or inherited by their li. If you need the bullet to be a different colour from the text, you must use an image instead, or work around the issue using other elements within the list items (this may be easy if all the items are links, for example).

Custom bullets using images

The standard set of unordered list bullets is adequate for basic content; however, it is a common design request to replace them with a custom image.

The CSS specification does include the list-style-image property for adding a custom list image. While this property works for basic image bullets, it has limited positioning options, and in some circumstances doesn't work at all in Internet Explorer. So it has become a far more common practice to set a background image on the list items to serve as graphical bullets.

Imagine you have an unordered list of RSS feeds and you want to change the bullet to the standard orange RSS icon. We'll give the list the class "rss" to differentiate it from other lists:

```
<ul class="rss">
  <li><a href="http://example.com/rss.xml">News</a></li>
  <li><a href="http://example.com/rss.xml">Sport</a></li>
  <li><a href="http://example.com/rss.xml">Weather</a></li>
  <li><a href="http://example.com/rss.xml">Business</a></li>
  <li><a href="http://example.com/rss.xml">Entertainment</a></li>
  <li><a href="http://example.com/rss.xml">Funny News</a></li>
</ul>
```

First we'll set the list to have no list-style-type (removing the default bullets) and remove the margin and padding. Then, we add a background image (the RSS icon) to each list item, some left padding to move the text to the right so it doesn't overlap the image, and some bottom padding to space out the list items:

```
.rss {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

.rss li {
  background: #fff url("icon-rssfeed.gif") 0 3px no-repeat;
  padding: 0 0 5px 15px;
}
```

This produces a list with the RSS image instead of bullets:

![Screenshot of a list with the bullets replaced with images](https://static.webplatform.org/w/public/d/dc/image-bu.gif)

Figure 3: The list with RSS image bullets.

Here, we positioned the background image using pixels for a precise placement. Depending on the design you are creating, you might also use %, ems, or keywords. Just be careful when your design features content that might cause a list item to wrap over several lines — if you set the background to vertical center or 50% it can look quite strange:

![Screenshot showing the way the vertically-centred bullet will sit in the middle of the text, instead of being centred to the first line of text.
](https://static.webplatform.org/w/public/4/45/image-bv.gif)

Figure 4: A demonstration of vertically-centred bullet images on a multi-line list item.

But by setting the image to align at the top of the list item, you maintain the default bullet behaviour, where the bullet sits on the first line of text:

![Screenshot of top-positioned bullet images.](https://static.webplatform.org/w/public/9/96/image-bw.gif)

Figure 5: A demonstration of top-aligned bullet images on a multi-line list item.

###List margins and padding

Clever use of margins and padding can make lists look much more polished and professional, but these techniques differ among different types of lists. In this section we'll look at how to apply sensible margins and padding to the two most common list types.

###Unordered lists

The default style for lists left-indents them, relative to surrounding paragraphs:

![Screenshot of default list styles with a larger left indent than paragraphs.](https://static.webplatform.org/w/public/a/ad/list-ind.gif)

Figure 6: Default styled lists are indented on the left.

If you want unordered list items to sit at the same left-align point as the rest of your content, you must set some styles to control the indentation. Different browsers require different settings; some need the margin removed while others need the padding removed. The safe way to reset for all browsers is to set both to 0:

```
ul {
  margin: 0;
  padding: 0;
}
```

However, this may not have the expected effect; while it does cause the text to sit flush left, the bullets will still sit outside the text:

![Screenshot of bullets sitting outside the text.](https://static.webplatform.org/w/public/5/51/list-ine.gif)

Figure 7: Bullets are positioned to the left of the text.

So, to align the bullets to the left you can now set a margin on the list items:

```
ul {
  margin-left: 0;
  padding-left: 0;
}

ul li {
  margin-left: 1em;
}
```

At this point you may still find a pixel-level difference between browsers, but the effect is basically as consistent as possible:

![Screenshot of bullets left-aligned closely with paragraphs.](https://static.webplatform.org/w/public/3/38/list-inf.gif)

Figure 8: Bullets positioned together with the surrounding paragraphs.

###Ordered lists

Now let's consider the same issue for ordered lists. They are trickier because the numeric markers are aligned according to the list item with the largest number. For example, if you have 10 list items, all the numbers will be positioned to allow for the two-digit "10" item:

![Screenshot of ten-item list, with the markers indented to allow for the 10.](https://static.webplatform.org/w/public/2/2c/ol-inden.gif)

Figure 9: The numeric markers for items 1-9 have preceding padding so they right-align with item 10.

There really isn't a convenient way to make an ordered list consistently left-aligned to the same position as the surrounding text, unless you set the list to list-style-type: decimal-leading-zero; which, while functional, isn't very attractive:

![Screenshot of leading zeros allowing numbers to left-align consistently.](https://static.webplatform.org/w/public/b/bf/ol-indeo.gif)

Figure 10: The leading zeros fill in the space for items 1-9.

It is more common to simply live with the difference in spacing. It does, however, mean that the markers of your ordered and unordered lists can't easily and consistently be left-aligned. You can only line up the text of your lists:

```
ul, ol {
  margin-left: 0;
  padding-left: 0;
}

li {
    margin-left: 2em;
}
```

You need at least 2em of left margin to accomodate both ordered and unordered lists. Note the way the text of the items lines up in these two lists:

![Screenshot of lists set to have text consistently left-aligned.](https://static.webplatform.org/w/public/c/ce/list-ing.gif)

Figure 11: The text lines up in both ordered and unordered lists.

**So, what to do?**

You basically have three choices:

1. Live with the default positioning of lists and their markers
2. Explicitly line up the text of your lists
3. Set a different style for ul and ol

There is no "right" or "wrong" approach, and it is quite common to simply leave things to the default settings for lists in general content.

###Using list-style-position

If you want the text of multi-line list items to wrap below the list marker (not recommended), you must set the list-style-position property to inside, which produces this result:

![Screenshot of unordered list with text wrapping below bullets.](https://static.webplatform.org/w/public/c/c8/inside-l.gif)

Figure 12: List position "inside" causes the text to wrap below the marker instead of in line with the indented text.

For obvious reasons, this is not an especially popular style. By default, list-style-position is set to outside, which produces the results discussed earlier.

### What about definition lists?

In general, definition lists don't require a huge amount of attention, except to set a **dt** style (commonly bold text) and to control the indentation of the definitions:

```
dt {
  font-weight: bold;
}

dd {
  margin-left: 2em;
}
```

This sets up a clear and easy style for definition lists:

![Screenshot of a definition list with bold terms and indented definitions.](https://static.webplatform.org/w/public/4/4d/definiti.gif)

Figure 13: A simply-styled definition list.

Although definition lists can be rearranged with floats and positioning, they are quirky; generally, it's better to keep things simple.

###Nested lists

In the HTML Lists article you learned about nested lists. When you create CSS for lists you should take care to maintain clear design cues that show the relationship between a nested list and its parent (the list item that contains it). By far the most common way to do this is by indenting the nested list items; it is, in fact, the default setting across browsers.

If you set up your own list indentation, your base setting will simply be multiplied. For example, consider this CSS:

```
ul, ol {
  margin-left: 0;
  padding-left: 0;
}

li {
  margin-left: 2em;
}
```

Each subsequent child list item in the chain inherits the margin value from its parent list item, in addition to having another 2em of its own added on top. So a top level list item (one that doesn't have a list item as a parent) will have a left margin of 2em, then a child list item of the first list item will inherit 2em from its parent, and then have another 2em added on to it, for a total of 4em, and so on.

###Horizontal lists

One of the most common changes required when working with lists is to produce a horizontal list — that is, to make the items appear next to each other instead of one after the other. This is a common trick for site navigation. Let's begin with a standard vertical list:

![Screenshot of a simple list with bullets](https://static.webplatform.org/w/public/5/5d/simple-n.gif)

Figure 14: A simple list.

Now let's convert this to a horizontal list:

![Screenshot of a list with the items appearing next to each other](https://static.webplatform.org/w/public/b/b4/simple-o.gif)

Figure 15: A simple horizontal list.

To achieve this, we must do three things to our list:

1. Remove the margin and padding from the <ul>
2. Set the list items to display: inline;
3. Give the list items some spacing to the right, to avoid having them run together

In the example, the list has the ID "mainmenu", so we'll use that as a contextual selector to make sure we only change the list we intend to change. The CSS is:
```
#mainmenu {
  margin: 0;
  padding: 0;
}

#mainmenu li {
  display: inline;
  padding: 0 1em 0 0;
}
```

In this simple example, setting the list items to display: inline; is enough; however, float: left; can also achieve a similar look.

###Faux columns

Earlier, we created a list of RSS feeds with graphical bullets. Now let's imagine that list has been placed in a sidebar on your site. You want the list to appear in two columns, with a border around the whole group:

![Screenshot of a list in two columns.](https://static.webplatform.org/w/public/1/16/columns-.gif)


Figure 16: A list of feeds in two columns, with an RSS icon for each bullet.

Let's assume the basic list is inside a <div>, which sets the width and border. The basic list would look something like this:

![Screenshot of basic list](https://static.webplatform.org/w/public/b/be/columns0.gif)

Figure 17: The unstyled list inside the border.


To achieve the faux columns effect, add the RSS icon as demonstrated earlier; then, add a 5px margin to the top, right, and left:

```
.rss {
  margin: 5px 5px 0 5px;
  padding: 0;
}

.rss li {
  list-style-type: none;
  background: #fff url("icon-rssfeed.gif") 0 3px no-repeat;
  padding: 0 0 5px 15px;
  display:-moz-inline-box;
}
```

Note that display:-moz-inline-box; is added to get the example to display correctly in Firefox 2.

We don't need to add a bottom margin, as the last list item's padding will cover that:

![Screenshot of list with the correct spacing and icon.](https://static.webplatform.org/w/public/6/68/columns1.gif)

Figure 18: Halfway there; we now have correct spacing and icon bullets.


Now we set the list items to display: inline-block;, and set their width to 40% and right margin to 2% (we could also use pixel widths). We also must explicitly set the **ul** to 100% width to ensure that the list wraps and sizes correctly:

```
.rss {
  margin: 5px 5px 0 5px;
  padding: 0;
  width: 100%;
}

.rss li {
  display: inline-block;
  width: 40%;
  margin: 0 2% 0 0;
  list-style-type: none;
  background: #fff url("icon-rssfeed.gif") 0 3px no-repeat;
  padding: 0 0 5px 15px;
  display:-moz-inline-box;
}
```

The inline-block display setting positions an element inline, but allows it to have a width and height. In most browsers this will be enough to create the column effect, but for Internet Explorer you must also float the list items to the left. To accomplish this, let's use a conditional style for all versions up to IE7:

```
<!--[if lte IE 7]>
  <style type="text/css">
    .rss li {
      float: left;
    }
  </style>
<![endif]-->
```

We now have the desired two column effect:

![Screenshot of a list in two columns.](https://static.webplatform.org/w/public/1/16/columns-.gif)


Figure 19: The completed list.

### Legacy browsers

If you are required to produce this design for older browsers that don't support inline-block, then you must float the list items to the left and use a clearing fix like the one described in the article Clearing a float container without source markup. Thankfully most modern browsers have now made inline-block a valid display property, so unless you have a very large browser share for older browsers you should be able to use the inline-block method.

### Lists conclusion

We've now covered a core set of styling choices and methods for lists. You can build on these examples and combine them to create a large number of designs. Because lists are very commonly combined with links, let's look at them next.
