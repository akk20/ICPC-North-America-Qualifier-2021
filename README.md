# ICPC North America Qualifier 2021
Collection of questions used during the ICPC North America Qualifier 2021

Contest website with original problems/example input:  
https://naq21.kattis.com/problems


## Problem A - Alien Integers
Exploratory robots are essential to expanding our understanding of the moon, Mars, and other celestial bodies. When there are two or more robots in the same vicinity, they need to be marked by humanly readable integers for purposes of visual tracking. To reduce the possibility of error in visual recognition of the robots in dark and dusty environments, numbers are chosen so that they have no digits in common. More formally, two non-negative integers are alien to each other if there is no digit which occurs in both of their decimal representations. For example, `11229` and `67840` are alien to each other, while `2022` and `427` are not. No integer is alien to `1234567890`.

The numbers on robots in the same area should also be close to each other numerically (for instance, to simplify processing of the marks by the software, to make them easy to remember, to distinguish them from other groups of robots marked in similar manner, …).

### Input
The input consists of an integer `N (1≤N≤10^15)` given on a single line.

### Output
When there is one non-negative alien integer `Y` closest to the input number `N`, output the value of `Y`. When there are two such integers that are equally close to the input number `N`, output both of them in ascending order, on a single line. When there is no integer alien to the input number `N`, output `Impossible`.

### Sample Input/Output
Link to sample data A

Sample Input 1  | Sample Output 1
------------- | -------------
`24`  | `19`

Sample Input 2  | Sample Output 2
------------- | -------------
`605`  | `499 711`

Sample Input 3  | Sample Output 3
------------- | -------------
`98765432011`  | `Impossible`


## Problem B - Avoiding Asteroids
You escaped the planet, but enemy starfighters are right behind you! To make things worse, in between you and the safety of your base is an asteroid field. The starfighters would never follow you into the asteroids, but unfortunately you used all your fuel in the escape, other than one small drop that will be enough for just one final burst of the engines. You’ve got two choices. You can surrender and face a long prison term. Or, you can aim your starship toward your base, and fire that one burst. There’s no way to know how fast that burst will make you move, but you know it’ll eventually get you to the safety of your base. That is, unless you collide with one of the asteroids.

You have a scan of the asteroid field, and need to determine whether you are sure to have a safe route through the field, or if surrender is the better option. Some important notes:

- Your ship and the base are insignificant compared to the size of the asteroids, and can be treated as points.
- Your scan of the asteroids will give the center of mass, the direction of motion (of the center of mass), and the points on the convex hull of the asteroid (all measured at the time of the scan).
- The center of mass of each asteroid translates over time in the given direction, but at an unknown speed. (You do know that the speed is non-negative: asteroids will not move backwards.)
- The asteroids can rotate about their center of mass, in any direction, at any angular velocity. You don’t have any information about the tumbling of the asteroid, and must allow for any possibility.
- Asteroids do not bounce off of each other (treat asteroids as though they pass through each other if they happen to collide).
- If you decide not to surrender, your ship will move through the asteroid field at an unknown speed: perhaps extremely slow, or perhaps extremely fast. You have no control over your ship’s speed and no ability to steer around asteroids.
- You may assume that no asteroid can “graze” the ship. Formally, for each asteroid either:
  - for any combination of your ship’s speed, the asteroid’s speed, and the asteroid’s angular velocity, the distance between your ship and the asteroid will be at least `10^−6` units, or
  - there exists some combination of your ship’s speed, the asteroid’s speed, and the asteroid’s angular velocity such that your ship intersects the asteroid and the distance between your ship and the nearest point on the surface of the asteroid is at least `10^−6` units.
- No asteroid can collide with (or graze) your base: for any combination of an asteroid’s speed and angular velocity, the distance between your base and the asteroid will be at least `10^−6` units at all times.
- Your ship starts at least distance `10^−6` units away from your base.

### Input
The first line of input consists of six real numbers `sx,sy,sz,bx,by,bz` and a single integer n, separated by spaces. These give the 3D coordinates of your ship `(sx,sy,sz)`, the 3D coordinates of the base `(bx,by,bz)`, and the number of asteroids, `n (0≤n≤30)`.

The next `2n` lines describe each of the asteroids, with one asteroid per pair of lines. The first line of each pair contains six real numbers `px,py,pz,dx,dy,dz` and a single integer m, separated by spaces, giving the position `(px,py,pz)` and direction `(dx,dy,dz)` of the asteroid’s center of mass, as well as the number of points `m` on the asteroid’s convex hull `(4≤m≤8)`. The second line of each pair contains `3m` real numbers, giving m triples of points `ci,x,ci,y,ci,z` , all separated by spaces. These are the 3D coordinates of the points on the convex hull of the asteroid, taken at the time of the scan. The asteroid center of mass is located somewhere within the convex hull (but not necessarily at the geometric center).

All real values in the input are in the range `[−2⋅10^6,2⋅10^6]`
and have at most 6 digits after the decimal point. Each asteroid’s direction is a unit vector, up to numerical tolerance, and will satisfy 
