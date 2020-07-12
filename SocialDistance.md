# Social Distancing - Project I (7-11-20)

 1. Just drawing boxes with a centroids and looking for collisions works decently when applied to 30 degree angled, clear video (as seen throughout the beach output video). However, in less ideal cases (such as the Hamilton and Tulsa rally videos), the programs faults shine through. For instance, the code will often correctly identify two people standing next to each other, but not identify a violation (ex: at the start of the hamilton clip, people in the crowd behind Trump, and a few times in the beach video). The code contains a config file to edit the distances, which would likely improve the method on unideal angles, but the code analyzes each frame incredibly slowly. While the code could be optimized to better work on a particular angle, it would be laborious to do so. The code also regularly identifies shadows as people, resulting in people violating social distancing with their own shadow (seen throughout the hamilton clip). In other words, this code would be ineffective during the night. 





#### Beach Video
[![](http://img.youtube.com/vi/SOSH0QptOx8/0.jpg)](http://www.youtube.com/watch?v=SOSH0QptOx8 "")

#### Hamilton Video
[![](http://img.youtube.com/vi/Eq8hT0Cs29s/0.jpg)](http://www.youtube.com/watch?v=Eq8hT0Cs29s "")


#### Tulsa Video
[![](http://img.youtube.com/vi/9qfOGnfU0NQ/0.jpg)](http://www.youtube.com/watch?v=9qfOGnfU0NQ "")
