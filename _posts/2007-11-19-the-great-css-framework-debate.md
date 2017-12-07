---
title: "The great CSS framework debate"
categories: work
tags:
  -CSS
  -Web Design
summary: 
---
<p>I&#8217;m a little late to this conversation, since I am on vacation for Thanksgiving, but I thought I&#8217;d weigh in on the <a href="http://www2.jeffcroft.com/blog/2007/nov/17/whats-not-love-about-css-frameworks/"><span class="caps">CSS</span> framework discussion</a> started by Jeff Croft.</p>

<p>I&#8217;m pretty sure the only reason why this is getting so much attention right now is because of the final few paragraphs of Jeff&#8217;s original article, which suggest that the only reason folks are against frameworks is that they are afraid frameworks will make their jobs obsolete:</p>

<blockquote>
<p>My gut feeling is that many folks who make their living off writing semantic (X)HTML and <span class="caps">CSS</span> are getting scared. They’re realizing that <span class="caps">CSS</span> and <span class="caps">HTML</span> are actually pretty darn easy, especially with the aide of tools like frameworks. They’re realizing that the only hard thing about writing <span class="caps">CSS</span> is troubleshooting lousy browsers — and they’re realizing that lousy browsers are fewer and farther between than ever, and getting fewer every year. They’re realizing, quite frankly, that their skill set may be less valuable in the future than it has been for the past couple of years. I’d love to be proven wrong, but until someone speaks up with some good reason why <span class="caps">CSS</span> frameworks shouldn’t be used, instead of simply asserting that they shouldn’t, I’m convinced these folks are just trying to drum up some false job security.</p>
</blockquote>

<p>This is a bit of hyperbole and flame-bait, and it&#8217;s not surprising to me that it has been met with some anger. But I have made posts like this myself, and am not going to hold it against Jeff, who I&#8217;m pretty sure didn&#8217;t mean to offend lots of his friends and colleagues in one fell swoop.</p>

<p>My experience with <span class="caps">CSS</span> frameworks is limited to Blueprint. I have briefly looked at <span class="caps">YUI</span>, and felt that the logic behind that system was at odds with the way I think. Just a different approach from what I am used to &#8212; nice looking shoes that just don&#8217;t fit me. Blueprint fit a bit better, and I had decided to use it for the redesign of this site that has recently launched, so that I could evaluate it in a real-world situation.</p>

<p>The most potentially useful part of Blueprint for me was the grid piece. I already have preferred ways to do a global reset and typography that work well for me and are well-honed. According to Jeff, <a href="http://www2.jeffcroft.com/blog/2007/nov/18/follow-up-css-frameworks/">this is in fact a personal framework</a>. Well, maybe, if you want to start playing with semantics. To me, a framework is a standard that folks from all over the world agree on and utilize, like Rails or Django or jquery. But whatever. What I found missing from the grid piece, and also from the <a href="http://kematzy.com/blueprint-generator/">grid generator</a> and <a href="http://www.ajaxbestiary.com/Labs/LayoutTool/index.htm">layout generator</a>, was a way to create a liquid grid. This was an important requirement for this site, which has always been liquid, and has been a place where I could show that liquid sites can be designed well and that the issues commonly cited as reasons not to go liquid can easily be overcome with a little thought. I belong to the <a href="http://adactio.com">Jeremy Keith</a> school of liuid design. :)</p>

<p>So, I ended up writing my own grid and not using Blueprint. For professional front-end developers, I suspect that this is a common occurrence &#8212; there are well-established specifications for a project that make the use of a framework impossible. I have found that the exceptions are more common than the rule in the work that I do, and <span class="caps">CSS</span> frameworks may work best for the rule. I may try to work with a framework again in the future, if I have a project that is suitable for them. </p>

<p>For the record, I don&#8217;t feel threatened by them. Even for front-end folks, there&#8217;s much more that goes into what we do than the simple chunking out of code, and most folks that I know are constantly on the lookout for tools that make the code writing process more quick and efficient. If frameworks turn out to be one of those tools, they will happily be adopted by me and my colleagues.</p>
