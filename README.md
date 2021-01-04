<h1> Inspiration </h1>
<p> As a passionate NFL fan, I find myself asking the same qustion every year. Which NFL running back is the best rusher? When determining this, we are given fairly limited information (Yards, YPC, and Carries). Other factors people use to assess a running backs abillity would be their style of play. To answer this question, I am utilizing my knowldge of Python and Pandas. Disclaimer - this analysis does not factor the quality of blocking, or strength of schedule.</p>

<h1> Obtaining the Data </h1>

<h2> Simplifying the Data </h2>

I was able to obtain a play-by-play data set for the 2020 NFL season from the following GitHub Repository.<br>
https://github.com/ryurko/nflscrapR-data
<br>
<br>
<p>Upon reading the 2020 play-by-play CSV, I filtered the appropriate columns. Those columns are rusher_player_name', 'week', 'home_team', 'posteam', 'play_type', 'yards_gained', 'run_location', 'run_gap', 'play_id', 'old_game_id'.
 <br>
 <br>
 To ensure that only running plays were filtered, I filtered by play_type == run.</p>

<h2> Formatting the Data </h2> 

With over 100 players to analyze, I needed to simplify my dataframe. I created a table which comprised of running backs who were top 20 in carries. 
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images/Images/Top%2020%20Carries.png" /></p>
<p>
With the current format of the dataframe, I would not be able to create visualizations and calculate statistics on a per-player basis. To enable this, I pivoted the data so that each player would be a column header, and the following values would be the yardage gained for each play. To ensure that each unique run play would pull through, I created a unique identifier for each play by concatenating the game ID and play Id. This value was set as the index. 

Despite having simplified my dataframe, I wanted to eliminate more players so that I could simplify my analysis. I calculated the mean yards gained for all running plays. This value is 4.544. I calculated the mean yards per carry for each of the 20 running backs. To further shorten my list, I eliminated any running back with a mean yards gained below 4.544. I chose to use mean yards gained because this is one of the best indicators of efficency. </p>
<br>
<br>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images/Images/Top20YPC.png"/></p>

<p> This simplified my list of running backs to Derrick Henry, Dalvin Cook, Aaron Jones, Melvin Gordon, Alvin Kamara, Ronald Jones, Nick Chubb, and Miles Sanders.</p>

<h2> Adding My Own Blueprint </h2>
<p> Although I have calculated the mean yards gained per run, this statistic does not tell the full story. This value can be easily skewed by calling several running plays which have a large gain. Furthermore, it does not paint a full picture on the distribution of yardage gained for each play. To add clarity, I added a column to the original data set that grouped the yardage gained of each running play into the following categores. Please note these groupings were created based off of my own knowledge and interpretation of football. 
 <br>
 <br>
 Yardage Gained < -2, Major Loss<br>
 -2 < Yardage Gained < 2, Stuffed<br>
 2 < Yards Gaineds < 4, Slight Gain <br>
 4 < Yards Gaineds < 6, Ideal Gain <br>
 7 < Yards Gaineds < 10, Burst Gain <br>
 10 < Yards Gaineds < 19, Big Gain <br>
 20 > Yards Gaineds, 20+ Gain <br>
 <br>
To format the data in a way that it could be visualized on a per player basis, I created another pivot. The column header would be the players names, the values would be the groupings, and I indexed each play by creating a unique ID as I did previously. 
 
<h1> Visualizations </h1>


<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images2/Images2/AJones.png"/></p>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images2/Images2/AKamara.png"/></p>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images2/Images2/DCook.png"/></p>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images2/Images2/DHenry.png"/></p>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images2/Images2/MGordon.png"/></p>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images2/Images2/MSanders.png"/></p>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images2/Images2/NChubb.png"/></p>
<p><img alt="Image" title="icon" src="https://github.com/AbhikMahakul/NFL-Runningback-Analysis/blob/main/Images2/Images2/RJones.png"/></p>

<h1> Conclusion/Analysis</h1> 

<p1> I start my analysis by eliminating Miles Sanders because he has, by a considerable margin, the highest percentage of plays (4.17%) of his plays resulting in a significant loss. To be succesful, it is imperative that your running back does not get stuffed or lose yardage because this will increase the pressure on the passing game. Following the theme of not placing additional pressure on the passing game, I will also eliminate Nick Chubb and Melvin Gordon because they have the highest percentage of their runs stuffed at respectily 17.05% and 19.58%. 
 
<br> 
Ronald Jones will be the next running back eliminated. Of the running backs left, he has the highest percentage of runs grouped as slight gain (27.22%). Although slight gain runs are better than being stuffed or loosing yardage, runs of these gains are usually wins for the defense. 

<br> Based off of my progression, it makes sense that Derrick Henry will be eliminated. This, however is not the case. Even though, of the remaining running backs, he has the lowest percentage of runs grouped in the ideal category, this is expected because his Mean Yards Per Carry is outside the range of ideal. 

<br> As I look at the other groupings (burst, big, and 20+), I notice that Derrick Henry is first in 2 of the 3 categories ( burst and 20+). Of the remaining running backs, Derrick Henry is the only running back who leads multiple groups. With that being said, my analysis concludes that Derrick Henry is the best rusher amongst running backs. He does not have a signigicant number of plays which result in being stuffed, a significant loss, or slight gain. Furthermore, he is most consistent and explosive as exibited by his high yards per carry (5.14), and high percentage of runs classified as a burst or 20+ gain. 
                         
                           
  
