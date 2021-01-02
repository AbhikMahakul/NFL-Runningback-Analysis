<h1> Inspiration </h1>
<p> As a passionante NFL fan, I find myself asking the same qustion every year. Which NFL running back is the best rusher? When determining ths, we are given fairly limited information (Yards, YPC, and Carries). Other factors people use to assess a running backs abillity would be their style of play. To answer this question, I am utilizing my knowldge of Python and Pandas to answer this question. Disclaimer - this anaysis does not factor the quality of blocking, or strength of schedule.</p>

<h1> Obtaining the Data </h1>

<h2> Simplifying the Data </h2>

I was able to obtain a play-by-play data set for the 2020 NFL season from following GitHub Repository.<br>
https://github.com/ryurko/nflscrapR-data
<br>
<br>
Upon reading the 2020 play-by-play CSV, I filtered the appropriate columns. Those columns are rusher_player_name', 'week','home_team', 'posteam', 'play_type', 'yards_gained', 'run_location', 'run_gap','play_id','old_game_id'. 
<br>
<br>
To ensure that only running plays were filtered, I filtered by play_type == run. 

<h2> Formatting the Data </h2> 

With over 100 players to analyze, I needed to simplify my dataframe. I started by creating a table of runningbacks with the top 20 carries. 
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images/Images/Top%2020%20Carries.png" /></p>
<p>
With the current format of the dataframe, I would not be able to create visualizations and calculate statistics on a per player basis. To enable this, I pivoted the data so that each player would the column header, and the following values would be the yardage gained for each play. To ensure that each unique run play would pull through. I created a unique identifier for each play by concatenating the game ID and play Id. This value was set as the index. 

Despite having simplified my dataframe, I wanted to eliminate more players so that I could simplify my analysis. I calculated the mean yards gained for all running plays. This value is 4.544. I calculated the mean yards per carry for each of the 20 running backs. To further shorten my list, I eliminated any running back with a mean yards gained below 4.544. I chose to use mean yards gained because this is one of the best indicators of efficency. </p>
<br>
<br>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images/Images/Top20YPC.png"/></p>

<p> This simplified my list of running backs to Derrick Henry, Dalvin Cook, Aaron Jones, Melving Gordon, Alvin Kamara, Ronald Jones, Nick Chubb, and Miles Sanders.</p>

<h2> Adding My Own Blueprint </h2>
<p> Although I have calculated the mean yards gained per each run, this statistic does not tell the full story. This value can be easily skewed by running several running plays which have a large gain. Furthermore, it does not paint a full picture on the distribution of yardage gained for each play. To add clarity, I added a column to the original data set that grouped the yardage gained of each running play into the following categores. Please note these groupings were created based off of my own knowledge/interpretation of Football. 
 <br>
 <br>
 Yardage Gained < -2, Significant Loss<br>
 -2 < Yardage Gained < 2, stuffed<br>
 2 < Yards Gaineds < 4, slight gain <br>
 4 < Yards Gaineds < 6, ideal gain <br>
 7 < Yards Gaineds < 10, burst gain <br>
 10 < Yards Gaineds < 19, big gain <br>
 20 > Yards Gaineds, 20 or Greater <br>
 <br>
To format the data in a way that it could be visualized on a per player basis, I created another pivot. The column header would be the players names, the values would be the groupings, and I indexed each play by creating a unique ID as I did previously. 
  
                         
                           
  
