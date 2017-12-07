---
title: "Creating an A-Z index with ExpressionEngine"
categories: work
tags:
  -Recommended
  -University Web Development
summary: 
---
<p>For the first article in my series about building the new <a href="http://www.humboldt.edu"><span class="caps">HSU</span> site</a> with <a href="http://pmachine.com">ExpressionEngine</a>, I thought I&#8217;d write the compliment to my earlier article where I explained <a href="http://interllectual.com/coffee/creating-an-a-z-index-with-textpattern">how I built <span class="caps">HSU</span>&#8217;s A-Z index with Textpattern</a>.</p>

<h2>Setting up the framework</h2>

<p>The first thing I did was set up the framework: a weblog (EE&#8217;s name for a container for related posts) called &#8220;siteindex&#8221; with 26 categories named A-Z where I would publish the entries, and a template group also called &#8220;siteindex&#8221; with 26 templates named A through Z.  Naming the template group and template pages in this way creates clean urls&#8212; the url of the page with the A entries will be <code>humboldt.edu/siteindex/A</code>.</p>

<p>Then I entered all the data for the index into the weblog, categorizing each entry under the alphabetical letter of the page that I wanted the entry to be displayed on.</p>

<h2>Coding the templates</h2>

<p>One of the great things about ExpressionEngine is that it allows for user-defined variables that can be used within EE tags.  These become a really convenient way to manage a group of templates that are essentially the same, differing only in the category, weblog, etc that is called by the EE tags.</p>

<p>So, I start out each if the 26 template pages with:</p>

<pre>{assign_variable:letter=&#34;A&#34;}
{assign_variable:catid=&#34;54&#34;}</pre>

<p>The first line sets the letter of the index page, which I use in the <code>&#60;title&#62;</code> tag of the page and in the <code>&#60;h1&#62;</code> tag: </p>

<pre>&#60;title&#62;{letter}: HSU A-Z Index&#60;/title&#62;</pre>

<p>and</p>

<p><pre>&#60;h1&#62;A-Z Index: {letter}&#60;/h1&#62;</pre>.</p>

<p>The second line sets the category id for the weblog category &#8220;A&#8221;, which happens to be 54 in this case.  I use this within the EE tag that produces the table cells with the entries filed under A, with <code>siteurl</code>, <code>dept-name</code>, <code>loc</code>, <code>phone</code> and <code>fax</code> being fields of data entered in the <code>siteindex</code> weblog:</p>

<pre>&#38;#123;exp:weblog:entries weblog=&#34;siteindex&#34; category=&#34;{catid&#38;#125;&#34; orderby=&#34;title&#34; 
sort=&#34;asc&#34; status=&#34;open&#34; disable=&#34;member_data|pagination|trackbacks&#34;}
&#60;tr class=&#34;{switch=&#34;odd|even&#34;}&#34;&#62;
&#60;td&#62;{dept-name}&#60;/td&#62;
&#60;td&#62;{loc}&#60;/td&#62;
&#60;td&#62;{phone}&#60;/td&#62;
&#60;td&#62;{fax}&#60;/td&#62;
&#60;/tr&#62;
&#38;#123;/exp:weblog:entries&#38;#125;</pre>

<p>The template also includes all the the other code to layout and format the page, and is repeated 26 times.  Luckily, EE provides include templates that allow me to write all this code only once and call it on each of the 26 template pages:</p>

<pre>&#38;#123;embed=&#34;includes/siteindex&#34;&#38;#125;</pre>

<p>So, each of the 26 pages actually only contains the following:</p>

<pre>{assign_variable:letter=&#34;A&#34;}
{assign_variable:catid=&#34;54&#34;}
&#38;#123;embed=&#34;includes/siteindex&#34;&#38;#125;</pre>

<p>with the <code>letter</code> and <code>catid</code> varying for each letter of the alphabet.</p>

<h2>The real advantage of EE</h2>

<p>The best part of the A-Z index in EE is that it is now the official repository for department names and urls on the main site.  EE has an amazing feature called relationship fields, which allows you to refer to information posted in one weblog from within a second weblog.  So whenever I need to list a linked department name, I can refer to this <code>siteindex</code> weblog rather than duplicating the information.  This has already proved to be a huge time saver for me, as several departments have changed their name since we went live with the new site.  I changed all the references to these departments in a few seconds by changing the name in the <code>siteindex</code> weblog.</p>

<p>I will be writing more about how I used relationship fields in the near future, so stay tuned.<br />
&#8212;&#8212;-</p>
