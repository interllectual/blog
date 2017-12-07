---
title: "Flexible Equal-Height Boxes: CSS and Javascript Methods"
categories: work
tags:
  -Recommended
  -CSS
  -Web Design
summary: 
---
<p>The new design of this site relies heavily on boxes of equal height.  I did a lot of thinking about how to accomplish this, and a lot of playing around with different methods during my design process, so I thought I&#8217;d share with you the ones I chose to use and why.</p>

<h2><span class="caps">CSS</span> Method</h2>

<p>The most obvious use of equal-height boxes is on the front page, where I show excerpts from the most recent articles in each of the three main sections of the site, followed by links to some older articles and the section archives.  It was important for the design that the &#8220;coffee&#8221;, &#8220;cocoa&#8221;, and &#8220;margarita&#8221; columns all be the same height, and that the title of each of the subsections align with each other across the three columns.  I was able to accomplish this and more using my trusty friend, the em.</p>

<p>I like to specify font size and line height using ems.  This allows users to increase their browser font size and still maintain the line height relationships that I have set up.  I found that doing this also allowed me specify heights of boxes in terms of ems, and be confident that my text would be cut off neatly in between two lines. An example would probably help here:</p>

<p>The first question I had to tackle was &#8220;How do I get all three excerpts to be the same height, when I can&#8217;t predict the length of the title?&#8221;.  The title may be anywhere between 1 and 4 lines long, depending on my mood at the time of writing.  I knew from my <span class="caps">CSS</span> font specifications that the <code>&#60;h2&#62;</code> elements containing the titles were 1.2em in size, and had a line height of 1.2em, with a .5em bottom margin.  I also knew that the <code>&#60;p&#62;</code> elements containing the body of the excerpt had a size of 1em and a line height of 1.5em. So I knew there was a way to specify the height of the excerpt such that the bottom of the box would always fall between two lines of excerpt text.  I could then hide the rest of the excerpt with <code>overflow:hidden</code> and have equal height excerpts.</p>

<p>Well, I fired up the calculator widget and started doing, as <a href="http://walscapades.com/?page_id=3">Steve</a> likes to put it, &#8220;The Math&#8221;.  After about an hour of calculations, resulting in a spinning head and much frustration, I decided to determine this height by trial and error. Which worked like a charm, giving me a height of 12.3 em for the excerpts, which allows sufficient text to show no matter how long title, and always cuts off between two rows of text.  So hey, presto, I had three equal height excerpt boxes.</p>

<p>Follow this same method, I was able to set equal heights on the boxes containing the &#8220;More drinks&#8221; titles, and have all three of the archives links align.  And I also used this method on the &#8220;Best of&#8221; and &#8220;Elsewhere&#8221; sections, keeping them equal heights as well.  I then realized that since I had all heights specified in ems, I could also get the tab on the right containing the navigation to be equal in height to the three other main columns on the page, an added bonus that I wasn&#8217;t anticipating.</p>

<p>The best thing, though, about this technique, is that the columns are flexible.  If a user increases their font size, the columns still hold up, up to a certain point.  There is some text overlap at large font sizes, which I still working on, but at most font sizes the layout should hold.</p>

<h2>Javascript Method</h2>

<p>Another place I rely on equal-height boxes is on the article pages.  I want the left-hand navigation column to be equal to the height of the column containing the article text, so that the dotted border always extends to the bottom of the article.  This time I can&#8217;t use ems, because there is really no way of predicting how long I&#8217;m going to ramble on in my articles.</p>

<p>The border was problematic no matter which column I placed it on, because the article may or may not be longer than the navigation.  So there would be some instances where the border wouldn&#8217;t extend to the bottom of the page if I just chose to put the border on one of the two columns and do nothing else.</p>

<p>So I looked for another method.  What I needed was to force the height of both columns to be the same height as the longer of the two columns.  Luckily, there are some folks out there who have published Javascript methods to do just that.  There are several scripts out there, as a quick Google search can show you.  The one I ended up using is from <a href="http://www.paulbellows.com/getsmart/balance_columns/">paulbellows.com</a>.</p>

<p>The reasons I chose this script were twofold.  First, it uses modern <span class="caps">DOM</span> scripting methods, and second, it recalculates the column sizes when the browser window is resized.  Since this site is liquid, the second was important to me, as resizing the window can have a huge impact on the length of the columns, and if the script didn&#8217;t account for that, there could be some messy looking results.</p>

<p>The one flaw of this method is that the column sizes aren&#8217;t recalculated when the text size is changed.  So if a user increases the text size of an article, they are left with text overlapping the boundaries of the box until they resize or reload the page.  I haven&#8217;t been able to find any way to overcome this, although I am continuing to look.  If you have any pointers, let me know.</p>

<h2>Conclusion</h2>

<p>While not the most elegant solutions, there are ways to create equal height boxes in today&#8217;s browsers without using tables.  I look forward to the days when we can rely on using &#8220;<span class="caps">CSS</span> table display properties&#8221; and/or <a href="http://www.w3.org/TR/2001/WD-css3-multicol-20010118/">CSS3 multi-column layouts</a> to achieve this (aside: <a href="http://weblogs.mozillazine.org/roc/">check this blog out</a> in Firefox 1.5 alpha&#8212; <span class="caps">CSS</span> columns, cool!) , but until then, we&#8217;ll still have to keep coming up with creative solutions.</p>
