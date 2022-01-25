# ICPC North America Qualifier 2021
Collection of questions used during the ICPC North America Qualifier 2021

Contest website with original problems/example input:  
https://naq21.kattis.com/


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
