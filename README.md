# Easy-Roads-3D-Traffic

NOTE: January 2019.   ER3D version 3.2, currently in development as of Jan 18) will have Lanes for each road.   That will make this code obsolete.  Once I get a working beta I will be working with that code and making a new repo, if necessary.  I have seen the alpha code provided with version 3.2 and it already so much better than mine.

-----------------------------

Simple automated traffic using Easy Roads 3D as the path information

I have been looking at multiple traffic ai assets and since my needs were simple, as well as having issues having other assets match the Easy Roads road path.

Easy Roads 3D has a series of Vector3 points, these points are in the center of the road (these are the ones I use) as well as along the right and left hand side of the road.

There are two scripts: 
* TrafficMgmt.cs - This adds traffic to the game/experience.  This script is attached, in my case to the camera, and is run only at Startup.
* AutoMgmt.cs    - This script is attached to each automobile and it sets the current path.   At each intersection a new road is selected.  This script needs to be disabled until a ERRoad object is attached, see TrafficMgmt Start() function.

Since I am using the Center Points of the road, each auto needs to be moved to the right.  The AutoMgmt script has a minRight and maxRight values, these are used to set the auto at random points to the right when the TrafficMgmt script creates an instance of the auto.

Because of this my prefab has a transform that has the AutoMgmt script and it has a child object which is the visible auto.  Make sure to set the "Hover Auto" value in the AutoMgmt script to this child object.  Take a peek at the image attached to this repository to see where the AutoMgmt script it to be placed. (on the parent object, not on the actual auto)
