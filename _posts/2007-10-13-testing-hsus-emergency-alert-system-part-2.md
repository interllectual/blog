---
title: "Testing HSU&#8217;s Emergency Alert System, Part 2"
categories: work
tags:
  -University Web Development
summary: 
---
<p>As promised, here is a follow-up to <a href="http://interllectual.com/coffee/testing-hsus-emergency-alert-system">my previous post about our test of the emergency alert system</a> last week.</p>

<p>We advertised the test on the <span class="caps">HSU</span> home page during business hours with a red box in the &#8220;promo&#8221; area:</p>

<p><img src="http://interllectual.com/images/13.jpg" title="HSU's home page, with red box announcing that a test of the emergency alert system would occur that day." alt="HSU's home page, with red box announcing that a test of the emergency alert system would occur that day." /></p>

<p>Then, at the appointed time, I switched the <span class="caps">HSU</span> home page into emergency mode for 15 minutes. A notice was displayed that explained the test, and what <span class="caps">HSU</span> constituents should do during an actual emergency:</p>

<p><img src="http://interllectual.com/images/14.jpg" title="HSU home page with large, red emergency notice posted." alt="HSU home page with large, red emergency notice posted." /></p>

<p>(These screenshots were taken by Karine Joly of <a href="http://collegewebeditor.com/blog/index.php/archives/2007/09/28/5-tips-to-be-better-prepared-for-a-campus-emergency-or-crisis/">collegewebeditor.com</a>, who has many great articles about higher ed emergency communications. I forgot to take screenshots during the drill :/ )</p>

<h2>What we learned</h2>

<ol>
<li><strong>Our chief of police rocks.</strong> Yes, we knew this already, but our Chief of Police, Tom Dewey, really needs to be commended. He has worked extremely hard on this system, which includes not only the web notices, but also notices on the campus <span class="caps">NPR</span> radio station, a telephone information line, text messages sent out to any constituent that chooses to sign up for them, and bells ringing, a recorded announcement, and signs placed around campus to warn folks of the emergency. He has been able to bring together staff from all parts of campus as key parts of the system, and his coordination has been amazing. Every part of the system worked on the first test, which is incredible. There is fine-tuning to be done, but Tom has done a great job pulling this all together.</li>
<li><strong>Our bells need to be louder.</strong> This is part of the fine-tuning&#8212; the bells couldn&#8217;t be heard on some parts of campus, so we are looking into amplification systems and ways to broadcast the bells from various parts of campus.</li>
<li><strong>Black text on red doesn&#8217;t work on the web.</strong> Tom has out together a color-coded system of signs for campus, and the intention is for the web notices to also use that system. There are 4 colors: red for campus or area closures and tests of the system, orange for tsunami warnings, yellow for national or regional incidents that don&#8217;t directly affect campus, and green for all-clear notices after an emergency. When I put together the styles for the web notices, I decided to scale back the background color from the really bright colors of the signs to aid readability. This unfortunately made the red notices kind of pink, which wasn&#8217;t really what we were looking for. So I made a quick change at the 11th hour to the colors you see above. That combination doesn&#8217;t meet accessibility standards for contrast, however. So, although the goal was for black text on red, we will have white text on red, which will be much more readable and allow a color of red that says &#8220;emergency&#8221; and not &#8220;be my Valentine&#8221;.</li>
</ol>

<p>So, all in all, the test was a success. The plan is to have one of these tests per semester so that everyone is always up on what our roles will be if we ever have to implement the system for real.</p>

<h2>Other refinements</h2>

<p>We have added 20 boilerplate notices to the campus <span class="caps">CMS</span> for all kinds of potential incidents, from a forest fire in the campus forest to a shooter incident on campus. The notices include information such as whether folks should leave campus, whether classes are canceled, whether staff and faculty should remain and assist or leave, and whether the residence halls should evacuate. Public Affairs staff can choose the appropriate boilerplate notice to start from and adjust it for the particular situation at hand, saving time.</p>

<p>The <span class="caps">CSU</span> has also put together a roll-over system for all 23 universities to deal with situations where our web server is taken out of commission. If there is a major earthquake on campus taking out our server, for example, humboldt.edu will resolve to a server in Long Beach so that we can still use the web as a communication vehicle. I and several other folks on campus can log into that server and manage the site from there. If we are also  out of commission, either from being physically incapicatated, or from our whole county being offline due to a major infrastructure failure (this happened last week&#8230;), we have a buddy campus that can also log in and make updates for us. </p>

<p>So, I feel that we are about as prepared as we can be for an emergency situation. Let&#8217;s hope we never have to actually put all this to use. </p>
