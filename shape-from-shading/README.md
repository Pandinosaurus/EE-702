## EE 702 Project Codes

### Shape from Shading

#### Group members:
	- Yash Bhalgat (13D070014)
	- Meet Shah (13D070003)
	
#### Code files:
	- shapeFromShading.py (using pq) and shapeFromShading_fg.py (using fg) for sphere
	- shape_from_shading_image.py (using pq) and shape_from_shading_image_fg.py (using fg) for special images
	- 3dSurfaceplotPlotly.py plots the saved .npy files for 3d images
	
#### Result files:
	- 2d folder - the depth maps can be found here.
	- 3d folder - includes the .npy files for 3d visulisations of all the depth-maps
	- depth_images - Depth-maps of the special images

#### Observations:

##### Effect of lambda (regularization parameter):
	In case of using 'pq', you can see that the improvement depth-map of the sphere is 
	considerable when lambda is changed from 10 to 100.
	But the parameters 'fg' are already regularised, so changing lambda from 10 to 1000
	doesn't show much effect on the sphere's depth-map.

##### Effect of noise in radiance:
	The range of radiance is from (0,11) in our case. So, we added gaussian noise of 10%, 30% and 50% resp.
	And the result deteriorated as the noise increased. But the deterioration was higher in the case of 'pq'
	than in 'fg'.
	
##### Effect of noise in source:
	We have taken the default source to be s0. Then we added gaussian noise of 20%, 50% and 80% resp while
	extracting the radiance from the sphere. Then we used the default source for reconstructing the depth.
	As can be seen in the result images, the depth-map gets shifted towards the additive noise direction.
	It can also be seen that the shift for the same noise is noticeably more in case of 'pq' than 'fg' as
	p and q parameters amplify the noise.
	(This can visibly observed in the 80% case.)
