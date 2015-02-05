# code
HTML, CSS, JavaScript, Java, etc. - code done in web dev projects


<!DOCTYPE html>
<html>
 <head>
   <meta charset="utf-8">
   <meta name="description" content="CNIT132 Final Project">
   <title>Pacific Trails Resort - Activities</title>
   <meta name="keywords" content="The Pacific Resort,Activities,Yurts,Reservations, Hiking,Kayaking, Bird watching">
   <meta name="author" content="Meli Naseri">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" href="favicon.ico" type="image/ico">
   <link rel="stylesheet" href="pacific.css">
 </head>
<body>
 <div id="wrapper">
  <div id="backimage"><h1>Pacific Trails Resort</h1></div>
  <div id="nav">
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="yurts.html">Yurts</a></li>
        <li><a href="activities.html">Activities</a></li>
        <li><a href="reservations.html">Reservations</a></li>  
    </ul>
  </div>
<div id="content">
 <h2>Activities at Pacific Trails</h2>
 <img class="trail" src="trail.jpg" alt="in the forest trail">
 <h3>Hiking</h3>
 <p>Pacific Trails Resort has 5 miles of hiking trails and is close to a state park.</p>
 <h3>Kayaking</h3>
 <p>Ocean kayaks are available for guest use.</p>
 <h3>Bird Watching</h3>
 <p>We offer guided bird watching trips at sunrise several times a week.</p>
 <div id="bird"><img src="little-bird.gif" alt="a bird flying"></div>
 <div id="footer">
       <p>Copyright &copy; 2011 Pacific Trails Resort<br>
       webmaster name</p>
 </div> <!-- footer div end -->
</div> <!-- content div end -->
</div> <!-- wrapper div end -->
</body>
</html>



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>CNIT 133 - Homework7 - Object Model and Event Model</title>
    <link rel="stylesheet" href="http://code.jquery.com/ui/1.10.3/themes/smoothness/jquery-ui.css">
    <style type="text/css">
        
        table
        {
            margin:0px auto;
            border:1px black solid;
        }
        td
        {
            border:1px black solid;
            font-size:24pt;
            background-color:white;
            width:60px;
            padding:5px;
        }
        .openCell
        {
            background-color:yellow;
        } 
    </style>
    <script src="http://code.jquery.com/jquery-1.10.2.js"></script>
    <script src="http://code.jquery.com/ui/1.11.1/jquery-ui.js"></script>
    <script type="text/javascript">
        $(document).ready(function()
        {
            //jQuery for tooltip
            $( document ).tooltip();

            //populate table
            var num = [];
            var temp;
            while(num.length < 15)
            {
                temp = Math.ceil(Math.random()*15);
                if (num.indexOf(temp) == -1)
                    num.push(temp);
            }

            for (var i = 0; i < 4; i++)
            {
                for (var j = 0; j < 4; j++)
                {
                    $("#cell" + i + j).html(num.pop());
                }
            }
            //swapCells helper function
            function swapCells(first, second)
            {
                var temp = $("#cell" + first).html();
                $("#cell" + first).addClass("openCell");
                $("#cell" + first).html($("#cell" + second).html());
                $("#cell" + second).removeClass("openCell");
                $("#cell" + second).html(temp);
            }
            for (var i = 0; i < 4; i++)
            {
                for (var j = 0; j < 4; j++)
                {
                    $("#cell" + i + j).click(processClick(i, j));
                }
            }
            //set click listeners for each table data
            function processClick(i, j)
            {
                var current = "" + i + j;
                var left = "" + (i-1) + j;
                var right = "" + (i+1) + j;
                var top = "" + i + (j-1);
                var bottom = "" + i + (j+1);
                return function()
                {
                    if ($("#cell" + left).hasClass("openCell"))
                        swapCells(current,left);
                    if ($("#cell" + right).hasClass("openCell"))
                        swapCells(current,right);
                    if ($("#cell" + top).hasClass("openCell"))
                        swapCells(current,top);
                    if ($("#cell" + bottom).hasClass("openCell"))
                        swapCells(current,bottom);

                    if ($("#cell00").html() == 1 &&
                        $("#cell01").html() == 2 &&
                        $("#cell02").html() == 3 &&
                        $("#cell03").html() == 4 &&
                        $("#cell10").html() == 5 &&
                        $("#cell11").html() == 6 &&
                        $("#cell12").html() == 7 &&
                        $("#cell13").html() == 8 &&
                        $("#cell20").html() == 9 &&
                        $("#cell21").html() == 10 &&
                        $("#cell22").html() == 11 &&
                        $("#cell23").html() == 12 &&
                        $("#cell30").html() == 13 &&
                        $("#cell31").html() == 14 &&
                        $("#cell32").html() == 15 &&
                        $("#cell33").html() == "")
                        alert("You Win");
                }
            }
        });
    </script>
</head>
<body>
	<h1>CNIT 133 Homework 7 - Object Model and Event Model </h1>
    <a href="hwk7.html">Homework 7</a> | <a href="7part1.html">Part1</a> | <a href="7part2.html">Part2</a> | <a href="7part3.html">Part3</a> | <a href="7part4.html">Part4</a> | Extra Credit<br><br>
	<div class="wrapper">
    <section id="content">
        <table>
            <tr>
                <td id="cell00"></td>
                <td id="cell01"></td>
                <td id="cell02"></td>
                <td id="cell03"></td>
            </tr>
            <tr>
                <td id="cell10"></td>
                <td id="cell11"></td>
                <td id="cell12"></td>
                <td id="cell13"></td>
            </tr>
            <tr>
                <td id="cell20"></td>
                <td id="cell21"></td>
                <td id="cell22"></td>
                <td id="cell23"></td>
            </tr>
            <tr>
                <td id="cell30"></td>
                <td id="cell31"></td>
                <td id="cell32"></td>
                <td id="cell33" class="openCell"></td>
            </tr>
        </table>
    </section>
    <footer>
            <a href="http://validator.w3.org/check" target="_blank">
            <img id="html5validator" src="html5_logo.png" alt="html5 validator" height="60" width="60" /></a>
            <a href="http://http://http://jigsaw.w3.org/css-validator/validator" target="_blank">
            <img id="cssalidator" src="css-validator.gif" alt="css validator" height="30" width="60" /></a>
     </footer>
     <p>Last update on <script type="text/javascript">
               document.write(document.lastModified);
     </script>
     </p>
</body>
</html>



<!doctype html>
<!--
Edited: pablo ponce
Name       : Orange And Black
Description: A two-column, fixed-width design for 1024x768 screen resolutions.
Version    : 1.0
Released   : 20090203
Thank you to FTC
-->
<head>
<meta charset="utf-8">
<title>night life</title>
	<meta name="keywords" content="">
	<meta name="description" content="">
	<link href="style.css" rel="stylesheet" type="text/css" media="screen">
    </head>
<body>
<div id="header-wrapper">
	<div id="header">
	  <div id="menu">
			<ul>
				<li class="current_page_item"><a href="index.html">Home</a></li>
		<li><a href="neighborhood.html">Neighborhood</a></li>
        <li><a href="nightlife.html">Nightlife</a></li>
		<li><a href="todo3.html">To DO</a></li>
		<li><a href="transportation.html">Transportation</a></li>
		<li><a href="event.html">Event</a></li>					
        <li><a href="arts.html">Arts&amp;Culture</a></li>
			</ul>
	  </div>
		<!-- end #menu --><!-- end #search -->
	</div>
	<!-- end #header -->
</div>
<!-- end #header-wrapper -->
<div id="page">
	<div id="logo">
		<h1><a href="index.html">San Fran<span class="text1">Tours</span></a></h1>
		<p><em><a href="http://www.freecsstemplates.org"></a></em></p>
	</div>
	<hr>
	<p>
	  <!-- end #logo -->
  Nightlife</p>
<div id="content">
<div class="post">
			<h2 class="title">Nightlife at the Academy of Science</h2>
		  <div class="entry">          
	 
<table width="100%" border="0" cellspacing="0" cellpadding="120">
  <tr>
    <td style="background-image:url(images/academy_science.jpg)"><br>
    </br></td>
  </tr>
</table>
	
<p>Every Thursday night, music, creatures and cocktails come together for NightLife at the California Academy of Sciences. Each week features a live band or DJ, and a unique theme  from salsa dancing to sustainable seafood and beyond. Delivering the wonders of land, space, and water in an exquisitely wrapped package, the California Academy of Sciences brings the above, below, and beyond of the entire world to life. Serving as one of the largest, innovative, and most eco-friendly natural history museums in the world, this Golden Gate Park jewel glistens with the promise of prehistoric sensations, astronomical exploits, dazzling gems and minerals, and living examples of extraordinary plants and animals. Come see the Academy in a whole new light!<br>
    55 Music Concourse Drive (located right between Martin Luther King Jr. Blvd. and JFK Drive)<br>
    <STRONG>Phone :</STRONG> (415) 379-8000 or visit the <a href="http://www.calacademy.org/events/nightlife/">website</a><br>
    Monday – Saturday (9:30am – 5pm); Sunday (11
    
    am – 5pm)<br>
    <STRONG>Admission Price: </STRONG>Adult $29.95<BR>
      Senior (ages 65 and over) $24.95<BR>
      Student $24.95
      <BR>
      Youth (ages 12-17) $24.95<BR>
      Child (ages 4-11) $19.95<BR>
    Ages 3 and under FREE<br>
    The California Academy of Sciences offers free entry December 9, 2012</span></p></p>
		  </div>
	</div>
    <div class="post">
			<h2 class="title">Pandora Karaoke &amp; Bar</h2>
		  <div class="entry">          
	 
<table width="100%" border="0" cellspacing="0" cellpadding="120">
  <tr>
    <td style="background-image:url(images/7.jpg)"><br>
    </br></td>
  </tr>
</table>
	
<p>
Is the largest and most unique late-night karaoke &amp; full-bar venue in the city and with vast array of song selections come in a variety of languages and with thousands of songs at one's disposal, everyone is sure to find the perfect tune. And it offers a great selection of food and alcoholic beverages and is the perfect   environment for birthdays, corporate events, get-togethers, and group fun. Visit us and see for yourself just how much fun you'll have at Pandora Karaoke &amp; Bar! Address: 177 Eddy Street San Francisco, CA 94102 Phone: (415) 359-1888<br>
      Tuesday thru Sunday: 6pm - 2am<BR>
      <em>Enjoy 50% off room rates and plenty of drink specials!</em><br>
      <em>Every Wednesday and Thursday buy one bottle and receive 1 hour private karaoke room rental for free!</em></span></p>
		  </div>
	</div>
    
    <div class="post">
			<h2 class="title">The Parlor			</h2>
	  <div class="entry">          
	 
<table width="100%" border="0" cellspacing="0" cellpadding="120">
  <tr>
    <td style="background-image:url(images/parlor-sf.jpg)"><br>
    </br></td>
  </tr>
</table>
	
<p>Is a waterfront bar that brings back the city&amp;rsquo;s early 1900s persona in style while offering all of the best nightclub accoutrements—including happy hour specials, world-class DJs, special events and live bands—for the modern nightlife enthusiast. The menus offer everything from light bites at happy hour to specialty cocktails to a lengthy list of libations for bottle service.<br>
Address: 2801 Leavenworth St,                                                                                                    San Francisco<br>
Phone: 415-775-5110<br>
Mon-Fri (5pm-2am)<br>
Sat-Sun (1pm-2am) </p>
      </div>
	</div>
    <div class="post">
			<h2 class="title">1015 FOLSOM</h2>
	  <div class="entry">          
	 
<table width="100%" border="0" cellspacing="0" cellpadding="95">
  <tr>
    <td style="background-image:url(images/1015.jpg)"><br>
    </br></td>
  </tr>
</table>
	
<p>This is SF’s oldest, biggest, and most worldly known nightclub. With 4 to 5 different rooms, all with different genres of electronic music, from the breaks and Drum&amp;Bass in the basement, to the 80’s flavor in the front room, to the tribal upstairs and you can’t miss the main room that’s where the DJ is who you came to hear.  This is the place that brings in the big name DJ’s, so if you want to hear the like of Oakey, PVD, Digweed, Maas, Tiesto, this is where they usually play. It is big, it gets crowded, and it gets hot and Free b4 10:15pm.<br>
 Address: 1015 Folsom  or visit the <a href="http://www.1015.com">website</a> for more update events.</p>
	    </div>
	</div>
                 <div class="post">
			<h2 class="title">Ruby Skye	</h2>
		  <div class="entry">          
	 
<table width="100%" border="0" cellspacing="0" cellpadding="120">
  <tr>
    <td style="background-image:url(images/ruby_skye.jpg)"><br>
    </br></td>
  </tr>
</table>
	
<p>
The popular nightclub in San Francisco, California. The nightclub is housed in the Native Sons of the Golden West building at 420 Mason Street. Downtown's most glamorous and colossal nightspot led a previous life as an 1890s   Victorian playhouse, and many of the beautiful Art Nouveau trimmings are still   in place. Mission District clubbers won't go near the place -- way too disco and   full of the &quot;bridge and tunnel&quot; crowd -- but for tourists it's a safe bet for a   dance-filled night in the city. The light and sound system here is amazing, and   on weekend nights the huge ballroom floor is packed with sweaty bodies dancing   to thumping DJ beats or live music. When it's time to cool off you can chill on   the mezzanine or fire up in the smoking room. For more information call: 415/693-0777 or visit the <a href="http://www.rubyskye.com">website</a> </p>
		  </div>
	</div>
    
     <div class="post">
			<h2 class="title">Tonga Room &amp; Hurricane Bar</h2>
		  <div class="entry">          
	 
<table width="100%" border="0" cellspacing="0" cellpadding="120">
  <tr>
    <td style="background-image:url(images/tonga_2.jpg)"><br>
    </br></td>
  </tr>
</table>

<p>Offers a tropical and festive atmosphere with live entertainment, dancing and a rain storm. Tonga Room serves exceptional Pacific Rim Asian Cuisine in a tropical setting and it is the perfect escape after a busy day of meetings or in town visiting for the first time and be sure to drop by and try the Mai Tai, regularly recognized as the City's best!<br>

  <strong>Address:</strong> 950 Mason St. San Francisco, CA  94108 <br>
  <strong>Phone:</strong> (415) 772-5278<br>

  <strong>Email: </strong>tongaroom@fairmont.com </p>
	   </div>
</div>
                
<!-- end #sidebar -->
<div style="clear: both;"> <a href="http://www.freecsstemplates.org/">Big thanks to FTC</a></p></div>
    
    <div id="footer">
	<p>Student Project by: &bull;David Mackey&bull; Pablo Ponce&bull; Meli Naseri&bull; Santos Martinez&bull; Kim Williams&bull; Brandon Nelson&bull; Shaobo Zhang&bull; Christopher Tarlton&bull;<a href="http://www.freecsstemplates.org"> 2012 </a></p>
</div>
<!-- end #footer -->
</body>
</html>
