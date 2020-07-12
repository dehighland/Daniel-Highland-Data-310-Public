# Social Distancing - Project I (7-11-20)

 1. Just drawing boxes with a centroids and looking for collisions works decently when applied to 30 degree angled, clear video (as seen throughout the beach output video). However, in less ideal cases (such as the Hamilton and Tulsa rally videos), the programs faults shine through. For instance, the code will often correctly identify two people standing next to each other, but not identify a violation (ex: at the start of the hamilton clip, people in the crowd behind Trump, and a few times in the beach video). The code contains a config file to edit the distances, which would likely improve the method on unideal angles, but the code analyzes each frame incredibly slowly. While the code could be optimized to better work on a particular angle, it would be laborious to do so. The code also regularly identifies shadows as people, resulting in people violating social distancing with their own shadow (seen throughout the hamilton clip). In other words, this code would be ineffective during the night. 
 2. On its own, it likely would not be useful for estimating infection. Our ability to estimate infection depends on the amount of footage we have and from how many vantage points. Ideally, the vantage points would be areas meant to represent the larger population (we could surveile everywhere, but that would be unethical) during daylight. However, without a face mask recognizer, it would be hard to tell if two people being close would actually impact infection. If we are looking at a major intersection, many people could be passing by with masks, leading to a much lower infection risk.
 3. To implement this design better, we would need a face mask detector and to keep track of the violations. If violations are staying onscreen for a long time or if people leave the screen together (implying unseen violations offscreen). Ethically speaking, it would be preferable if as few people as possible had access to this footage, as it would be a violation of privacy if people who didn't need to see the footage had access. We should also avoid any face recognition efforts, as registering faces creates the possiblility of our deisgn falsely accusing people of violating social distancing, opening them up to unfair punishment. Facial recognition code could also be used (even outside of our original program) to track peoples movements in an area, thereby violating privacy. 


#### Beach Video
[![](http://img.youtube.com/vi/SOSH0QptOx8/0.jpg)](http://www.youtube.com/watch?v=SOSH0QptOx8 "")

#### Hamilton Video
[![](http://img.youtube.com/vi/Eq8hT0Cs29s/0.jpg)](http://www.youtube.com/watch?v=Eq8hT0Cs29s "")

#### Tulsa Video
[![](http://img.youtube.com/vi/9qfOGnfU0NQ/0.jpg)](http://www.youtube.com/watch?v=9qfOGnfU0NQ "")
