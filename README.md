[Report](https://hackmd.io/s/S15oeq_a7)

# Advanced Statistics. Assignment #2 report.
>Author:  Artur Khayaliev, BS4-DS
---

* First of all, you can find github repo [here](https://github.com/zytfo/adv_stat_assignment_2)
* Clone it to your local machine to open jupyter notebook and see all the plots. They will be opened in new tabs when you run all cells
* You can find plots pictures in [*plots_pictures*](https://github.com/zytfo/adv_stat_assignment_2/tree/master/plots_pictures) folder
* Red circle means start city

## Initial Google map with cities

This path was built in order of adding cities from dataframe (without any logic). The red circle is the first city - Moscow.

![](https://i.imgur.com/20RjD0r.png)

As we can see, we have a terrible tour which consists all cities, but it is very inefficient in terms of distance.

## Experiments


I tried four different cooling rates:
* 0.1
* 0.01
* 0.001
* 0.0001

## Cooling rate = 0.1
The tour distance is **36676.39** km.

![](https://i.imgur.com/TOz7xbz.png)
>gmap_0.1.png

Much better than path from dataset. But it is still inefficient.

![](https://i.imgur.com/0ywlzLu.png)
>temperature_0.1.png

Here we can see a temperature decreasing through iterations. As we can see, already in 60th iteration we have a temperature close to 0.

![](https://i.imgur.com/GBH3RF0.png)
>distance_0.1.png

As we can see, it looks like almost step function and distance goes to 36000 km in 60th iteration.

## Cooling rate = 0.01
The tour distance is **20772.67** km.

![](https://i.imgur.com/jYzdiEv.png)
>gmap_0.01.png

Here we just reduced our tour distance in ~16000 km which is a huge number. We also can see, that we improved our path. It is a very good improvement, but let's try some more.

![](https://i.imgur.com/JnHPIyD.png)
>temperature_0.01.png

Temperature decreases much slower comparing to 0.1, i.e. we have 0 degrees in 600th iteration (10 times bigger than 0.1).

![](https://i.imgur.com/xpkZsfA.png)
>distance_0.01.png

Distance also decreases in a much different way. In fact, we almost converge into our minimum in ~700th iteration.

## Cooling rate = 0.001
The tour distance is **19118.26** km.

![](https://i.imgur.com/qO7pznq.png)
>gmap_0.001.png

We improved distance of the tour a bit once again, but not too much as in previous case.

![](https://i.imgur.com/XF9Rz8E.png)
>temperature_0.001.png

Temperature decreases much slower (10 times bigger iterations than in the previous case), and we converge to the minimum in the 6000th iteration.

![](https://i.imgur.com/rRGBWsO.png)
>distance_0.001.png

Our distance function is very different from the first one. It significantly changes in the first 2000 iterations and converges to the minimum in the 6000th iteration.

## Cooling rate = 0.0001
The tour distance is **19024.19** km.

![](https://i.imgur.com/9lRgdP2.png)
>gmap_0.0001.png

This is our best case. We just reduced our distance from 36k to 19k kms. 

![](https://i.imgur.com/DOP01p4.png)
>temperature_0.0001.png

Here we converge to 0 degrees in the 60000th iteration. 

![](https://i.imgur.com/m82plR6.png)
>distance_0.0001.png

Our distance changes a lot in first 25k. After 40k iterations, it almost converges to the minimum.

| Cooling Rate  | Distance of the tour (km)|
| ------------- |:-------------:|
| 0.1           | 36676.39      |
| 0.01          | 20772.67      |
| 0.001         | 19118.26      |
| 0.0001        | 19024.19      |

# Conclusion

In this assignmet I had to apply Simulated Annealing method on russian cities dataset. It was an interesting task and I liked it a lot.
