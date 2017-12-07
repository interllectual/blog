---
title: "Textpattern to Movable Type Export Script"
categories: work
tags:
  -ExpressionEngine
  -Textpattern
  -Tools
summary: 
---
<p>I am reposting this file here so it doesn&#8217;t get lost in the intertubes.  </p>

<p><a href="http://interllectual.com/files/export-movabletype.zip">Textpattern to Movable Type exporter</a></p>

<p>This script, which I found tucked away in a corner of the <a href="http://expressionengine.com/wiki/Migrate_To_EE">ExpressionEngine Wiki</a> with no directions, was written by Ryan Abrams and is <a href="http://www.flipsidejones.net/files/export-movabletype.php.txt">still available on his site</a> as of this writing.  His site is abandoned, however.</p>

<p>The script converts your <span class="caps">TXP</span> site to Movable Type format, which is a standard format that can be imported into many other <span class="caps">CMS</span>s, including Expression Engine and Wordpress.  I have successfully used   it to convert my site to Expression Engine (more on that coming soon), and have not lost any data.  Comments were all successfully transferred, which is not the case with the other scripts I was able to find.</p>

<p>Instructions for use:</p>

<ol>
<li> <a href="http://interllectual.com/files/export-movabletype.zip">download the script</a></li>
<li>Edit the configuration variables at the top to match your <span class="caps">TXP</span> install</li>
<li><span class="caps">FTP</span> the script to your site as a php file.  It doesn&#8217;t matter where you put it, but you need to be able to browse to it.</li>
<li>Browse to the script in your browser of choice.  You will see a bunch of crazy looking stuff displayed, which is your content in MT format.</li>
<li>When the page is done rendering, view source and save the source code to your machine as text.</li>
<li>Delete the script from you server for security.</li>
</ol>

<p>Use the import utility of the new <span class="caps">CMS</span> to import your content from this file.  For Expression Engine:</p>

<ol>
<li>Upload the newly created text file to the site with your new EE installation,</li>
<li>use the &#8220;Import from Movable Type&#8221; utility in  Admin &#62; Utilities &#62; Import Utilities.</li>
<li>There are a few of options in the EE import utility&#8212; I specified Textile as my default entry format.  You may need to load the <a href="http://expressionengine.com/downloads/details/textile/">Textile plugin</a> before importing the entries to have this as an option.  All the other options are straightforward.  The &#8220;Auto-create categories&#8221; option worked for me as well&#8212; no need to re-create all those categories by hand!</li>
</ol>

<p>I hope you find this useful.</p>
