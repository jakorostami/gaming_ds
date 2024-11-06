<div align="center">
  
  # <div align="center"> Gaming Data Science and Machine Learning</div>

This repo is a demo of a classical Data Science and Machine Learning approach but for gaming data, which I've never worked with before.
The gaming data is from the games of [Counter-Strike Global Offensive](https://en.wikipedia.org/wiki/Counter-Strike:_Global_Offensive) (CSGO) and [League of Legends](https://en.wikipedia.org/wiki/League_of_Legends) (LoL).

For CSGO, the approach is analytical at first producing statistical and probabilistic analysis of the games played. Later on, the coordinate data (longitude, latitude) is used
to do movement prediction with an LSTM, training on the GPU.

But for LoL, the approach is a bit different because of the composition of the dataset, first an analysis is done which then leads to a binary classification challenge where
the predictions are which teams wins. 


## <div align="center"> CS-GO </div>
What we'll look at first is the equipment value after buy time for each match and split them by which side won.

<div align="center">
  - Counter-Terrorists tend to buy more expensive gear <br>
  - Terrorists might be saving depending on the round<br>
</div>
<br>
  <p>
    <a target="_blank">
    <img width="60%" src="https://github.com/jakorostami/gaming_ds/blob/main/notebook-images/3.png" alt="Mapper"></a>
    
  </p>
  <br>
  <br>
  
Of all the matches analyzed, we find that Counter-Terrorists have a higher propensity to be the first attacker.
<br>

  <p>
    <a target="_blank">
    <img width="60%" src="https://github.com/jakorostami/gaming_ds/blob/main/notebook-images/11.png" alt="Mapper"></a>
    
  </p>
  <br>

  
Terrorists have a tendency to spread around bomb site while Counter-Terrorists focus more on bomb site B and the center.
  <p>
    <a target="_blank">
    <img width="70%" src="https://github.com/jakorostami/gaming_ds/blob/main/notebook-images/2.png" alt="Mapper"></a>
    
  </p>


When we test the difference of time between attacks between CT and T using a non-parametric statistical test 500 times to see if
this happens by chance 1% of the time - the majority of our tests generate values that are compatible with our data. Meaning we don’t really find a statistical difference.
  <p>
    <a target="_blank">
    <img width="70%" src="https://github.com/jakorostami/gaming_ds/blob/main/notebook-images/12.png" alt="Mapper"></a>
    
  </p>

## <div align="center"> League of Legends </div>
For LoL, at a first glance we find the following:
<div align="center">
  - Higher team champion level comes with high team minions killed <br>
  - More wards placed by the team also comes with a higher team champion level
</div> 
<br>
  <p>
    <a target="_blank">
    <img width="70%" src="https://github.com/jakorostami/gaming_ds/blob/main/notebook-images/lol1.png" alt="Mapper"></a>
    
  </p>

<br>
If a team has an extremely high kill rate they tend be very different in their first 10 minutes of the game.
<div align="center">
  - lower deaths than the non-anomaly teams <br>
  - higher kill assists <br>
  - higher kills <br>
  - more gold per minute <br>
  - higher total experience <br>
  - higher champion level <br>
</div>
<br>
  <p>
    <a target="_blank">
    <img width="70%" src="https://github.com/jakorostami/gaming_ds/blob/main/notebook-images/lol3.png" alt="Mapper"></a>
    
  </p>
<br>

We've got all the features for modeling
  <p>
    <a target="_blank">
    <img width="70%" src="https://github.com/jakorostami/gaming_ds/blob/main/notebook-images/lol4.png" alt="Mapper"></a>
    
  </p>

  <br>

  The best model is a logistic regression using our augmented dataset with the PCA embeddings. 
  The second best model is the Random Forest which is a tree-based model.
  <p>
    <a target="_blank">
    <img width="70%" src="https://github.com/jakorostami/gaming_ds/blob/main/notebook-images/lol6.png" alt="Mapper"></a>
    
  </p>


</div>
