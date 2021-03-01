FLICKERSCAPE was created using a combination of HTML, CSS, and JavaScript.  It more specifically makes heavy use of the HTML <audio>
tag, CSS animations and transitions, and the Web Audio API.  It is designed to be a cross between a piece of art and a game
that will run in many browsers and can be played forever.

The first page that you will see (the Homepage or Title Page) is a simple HTML page that features a large heading containing the
title of the piece.  You will notice that it "flickers" red every few seconds.  This was created using a series of CSS classes that are
each animated but are sequentially delayed by a few milliseconds. The about tab in the upper left corner will expand when you hover over it.
This was also achieved using a CSS animation when the div is hovered over.

The warning page (which appears after you click the title) is a simple HTML page as well that uses the same Style.css file as the homepage.
It is timed to refresh after 6 seconds using the following:

  <!--<meta http-equiv="refresh" content="6;base.html" />-->

Once it is refreshed it will take you to the start of the piece.  The foundation of the piece is a file called base.html.  This page is basically
empty except for several <audio> tags which run the underlying soundscape/drone for the piece, some JavaScript synthesizing some more
sounds, and an iframe that takes up the entire page.
Inside this iframe is a page called test_css.3.html.  This file is the first "scene" of the piece.  It is made up of many different <div> elements
all with different CSS associated with them.  They all have different behaviors when you hover over them/click them which are achieved using
CSS animations.  Some of the rectangles will turn red when you hover over them.  You can click these ones and when you do
they open up even more iframes within the iframe which have JavaScript in them which will synthesize more sounds.
The page inside the top layer iframe also has another <audio> tag which adds sounds specifically written for scene one.

Every ten seconds the scene will change inside the top layer iframe making the grid of divs look different and changing some of the audio.
However, because all of the changes are happening within this top layer div, none of the base elements, e.g. the underlaying soundscape, will
change but the scene specific ones will.  I chose to put all of the css for each of the scenes inside the actual pages because it all
changes with each scene and there was not enough similarity between each to justify making a second seperate CSS file (like the homepage
and warnig page had) to link to.  I thought it would be redundant to fully comment each and every scene so I simply commented scene 1 (test_css.2.html)
which can be used as a reference for the other scenes because the basic layout is very similar.  Same goes for each audio.html file.  Only audio1.html
is fully commented.

There are 8 scenes and they each link to the next every 10 seconds.  Kind of like a linked list of webpages.  However, the 8th and final scene
then links back to the 1st one creating an endless loop that could be played/performed forever.  When you are done with the piece simply close
the tab.