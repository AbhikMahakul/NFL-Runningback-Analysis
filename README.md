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

Once I did this, I needed to ensure that each unique run play would pull through. I created a unique identifier for each play by concatenating the game ID and play Id. 


  
  
