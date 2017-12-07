---
title: "Creating an A-Z index with Textpattern"
categories: work
tags:
  -Recommended
  -Textpattern
  -University Web Development
summary: 
---
<p>I got an email from <a href="http://campfiresites.com">Eric</a> yesterday asking if I would share how I created the A-Z index on the <a href="http://www.humboldt.edu">Humboldt State University</a> site with Textpattern. His email was timely, because with the new <a href="http://textpattern.com/weblog/11/textpattern-4-stable-released"><span class="caps">TXP</span> 4.0 release</a>, I was planning on re-examining how I did the A-Z index (which was done in one of the gamma releases) to see if it could be cleaned up a bit.  I thought I&#8217;d publish this here as well, in case anyone else is interested. </p>

<p>The index I inherited from the previous webmaster was just 26 static html files that needed to be maintained and alphabetized by hand.  The textpattern solution is probably not the cleanest database solution that I could have set up, but it was one I could wrap my head around, and gave me several other benefits of Textpattern.  These include the ability to set up an easy-to use interface for student assistants, and keep track of which author had published something to the index.</p>

<p>There are 3 components to the index: 
<ol>
<li>the links to the index sections which fall along the bottom of the main page, which are managed through the textpattern link functions,</li>
<li>the data, which are stored in custom fields of textpattern articles, and</li>
<li>the display of the data, which is done through a page template and forms.</li>
</ol></p>

<p>If these terms don&#8217;t make sense to you, you may want to check out the Textbook entry on <a href="http://textpattern.net/wiki/index.php?title=Textpattern_Semantic_Model">the semantic model of textpattern</a>.</p>

<h2>Links</h2>

<p>For the links, I set up a category of <span class="caps">TXP</span> links called <code>azindex</code>, and set up 26 links in this category (one for each letter of the alphabet). The name of the link is A, B, C, etc, and the url is <code>/siteindex?c=A</code>, <code>/siteindex?c=B</code>, etc.  The <code>?c=</code> in the url tells textpattern to only display articles assigned to the category indicated. </p>

<p>On <a href="http://www.humboldt.edu">the main page</a> I output the links for the index with <code>&#60;txp:linklist form=&#34;azindexlinks&#34; category=&#34;azindex&#34; limit=&#34;30&#34; sort=&#34;linksort&#34; /&#62;</code>.  I output these as an unordered list, and use <span class="caps">CSS</span> to style them as a horizontal bar across the bottom of the page.  This step could probably be skipped and the links just added directly to the code of the page.  I did it this way to make my page templates cleaner&#8212; 26 links adds a lot of code!</p>

<h2>Data</h2>

<p>For the data, I set up 26 article categories, one for each letter of the alphabet, and a section called <code>siteindex</code> where I would display the results when one of the index links is clicked.</p>

<p>I use the article custom fields to hold the index information.  I have 5 fields set up, which correspond to the information in the index: Department Name, Department <span class="caps">URL</span>, Location, Phone, and Fax.  When I enter a new item, I fill out these fields and the title only, leaving the body blank.  I also categorize each entry under the correct letter of the alphabet, so <span class="caps">TXP</span> know which A-Z index page it corresponds to, and make sure I post it to the section <code>siteindex</code>.</p>

<h2>Display</h2>

<p>To display the index results, on the <code>siteindex</code> page, I set up a table and headers for the output (which is tabular data), and then call the relevant results with <code>&#60;txp:chh_article_custom limit=&#34;1000&#34; listform=&#34;azlist1&#34; sortby=&#34;Title&#34; sortdir=&#34;asc&#34; allowoverride=&#34;all&#34; /&#62;</code>.  This uses the <code>chh_article_custom</code> plugin, which allows me to sort the the results by title, rather than in the order they were posted. (So index items can be added in any order, and I can be sure they end up alphabetized).  This option wasn&#8217;t available for <code>&#60;txp:article_custom/&#62;</code> in the gamma releases, but it is there in v4.0, so you don&#8217;t need the plugin anymore.</p>

<p>Finally, in the form <code>azlist1</code>, I use the <code>rei_show_custom</code> plugin to output the info in the custom fields.  Here is what the form contains:     </p>

<pre>
&#60;tr&#62;
&#60;td&#62;&#60;a href=&#34;&#60;txp:rei_show_custom customid=&#34;2&#34; /&#62;&#34;&#62;
&#60;txp:rei_show_custom /&#62;&#60;/a&#62;&#60;/td&#62;
&#60;td&#62;&#60;txp:rei_show_custom customid=&#34;3&#34; /&#62;&#60;/td&#62;
&#60;td&#62;&#60;txp:rei_show_custom customid=&#34;4&#34; /&#62;&#60;/td&#62;
&#60;td&#62;&#60;txp:rei_show_custom customid=&#34;5&#34; /&#62;&#60;/td&#62;
&#60;/tr&#62;</pre>

<p>In 4.0, this can now be done using the <code>&#60;txp:custom_field /&#62;</code> tag, and there is no need for the plugin.</p>

<p>If I need to use an alternate format for the display of a particular entry, I use an override form to do this.  My main override form has </p>

<pre>
&#60;tr&#62;
&#60;td colspan=&#34;4&#34;&#62;&#60;a href=&#34;&#60;txp:rei_show_custom customid=&#34;2&#34; /&#62;&#34;&#62;
&#60;txp:rei_show_custom /&#62;&#60;/a&#62;&#60;/td&#62;
&#60;/tr&#62;
</pre>

<p>which I use when I need to say something like: Information Technology Services: see also Academic Computing, Telecommunications &#38; Network Services, Instructional Media Services, or University Computing Services. (<a href="http://www.humboldt.edu/~humboldt/siteindex?c=I">See this example live here</a>.)</p>

<h2>You&#8217;re Done</h2>

<p>Once all this is set up,  all you have to do is input all the articles.  Student assistants are good for this (thanks Kent!).  </p>

<p>Inputting the articles was a big initial investment for <del>me</del> <ins>Kent</ins>, but maintenance of the A-Z index is a breeze now that it is set up.  And it is heavily used&#8212; most of the on-campus folks at the University use the A-Z Index to find their sites they need, rather than traversing the navigation hierarchy.  It has proved a good solution for us, in the absence of a university-wide <span class="caps">LDAP</span> database or other system we could have tapped into.</p>
