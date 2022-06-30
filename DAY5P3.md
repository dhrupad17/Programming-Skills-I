# Check If It Is a Straight Line
---
- ## Question:
> You are given an array coordinates, coordinates[i] = [x, y], where [x, y] represents the coordinate of a point. Check if these points make a straight line in the XY plane.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2019/10/15/untitled-diagram-2.jpg)
> Input: coordinates = [[1,2],[2,3],[3,4],[4,5],[5,6],[6,7]]
> 
> Output: true
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean checkStraightLine(int[][] coordinates) {
        int x1 = coordinates[0][0],
		x2 = coordinates[1][0],
		y1 = coordinates[0][1],
		y2 = coordinates[1][1];
        int a = (y2 - y1);
	    int b = (x1 - x2);
	    int c = a * x1 + b * y1;
        for(int i = 2; i < coordinates.length; i++) {
		int cval = a * coordinates[i][0] + b * coordinates[i][1];
		if(cval != c)
			return false;
	    }

	return true;
    }
}
