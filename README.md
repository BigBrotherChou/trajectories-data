# trajectories_data
Dataset demo of trajectories of taxis
## Structure of the dataset
The raw data demo of taxi is saved in the file named `data.csv` in the directory `raw_trajectory_data` . the structure of the dataset is arranged as follows:
|| Seial ID | taxi ID  | date     | lng | lat | angle| load|sped|
|-| -------- | -------- | -------- |-------- |-------- |----|-------- |---|
|| ...| ...| ... |...|...|... |...|...|
|$(l_1,time,dow)\rightarrow$| ... | 1480 | 2020-08-05 12:18:14 |116.327033339434 |39.9094521622044|...|0|...|
|| ...| ...| ... |...|...|... |...|...|
|$(l_m,time,dow)\rightarrow$| ...| 1480| 2020-08-05 12:19:10 |116.267395032144 |39.9102254615886 |...|0|...|
|$l_{m+1}\rightarrow$| ...| 1480| 2020-08-05 12:19:59 |116.325545212463 |39.996186373953|...|1|...|
|| ...| ...| ... |...|...|... |...|...|

The raw data of taxi trajectories consists of a collection of GPS positioning information from multiple taxis at different times. 

 ``taxi ID`` is used to indicate the unique identifier of each taxi,
 
 ``date`` represents the time information when the trajectory data is generated
 
 ``lng`` and ``lat`` respectively represent the longitude and latitude of the taxi at the current time
 
 ``angle`` and ``speed`` indicate the direction and speed of the taxi's movement at the current time
 
 ``load`` represents the passenger load status of the taxi at the current time. The value `1` represents that the taxi is occupied (has passengers) at that time, while the value `0` indicates that the taxi is vacant.

## Data filtering
In our work, we filter the raw data to generate the data required for training the model. 

Firstly, we will filter all the data of the taxis that need to be extracted based on their taxi ID. After sorting the filtered data by `date`, we will select the trajectory points with `load` values of `0` and `1` respectively to form the final dataset used for training which is  represented as $((l_1, time, dow), ..., (l_m, time, dow))$ and $(l_m, ..., l_{m+n})$ in our work.

For more detail raw data, please visit [Google Drive](https://drive.google.com/drive/folders/1wVI7P9yKHDfivRbxHpI5kBt_7iV0cNug?usp=sharing)
