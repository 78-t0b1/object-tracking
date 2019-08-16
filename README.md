# object-tracking
Study different techniques to track object.

<h1>How to use it ??</h1>

<p>	tracker_types contains object diffrent object tracking techniques. Set tracker_types index respective to method you want to exicute. </p>
<p>	run program. Now one still frame will appear. </p>
<p>	Use your mouse pointer to map object. Then press enter. </p>
<p>	press Esc to exit.  </p>



<h1>Explaination of trackers</h1>

<h2>BOOSTING Tracker</h2>

<p>It is based on online version of AdaBoost. This classifier need to be trained at runtime with positive and negative examples of object. Given a new frame the classifier is run on every pixel in the neighbourhood of previous location and the score of the classifier is recorded. The new location of object is one where score is maximum. </p>

<h2>MIL Tracker</h2>

<p>It looks in a small neighbourhood around the current location to generate several potential positive examples.In MIL(multiple instance learning)you dont specify positive or negative examples. Instead, only one image in positive bag to be positive. a positive bag contains the patch centered on the current location of the object and also patches in a small neighborhood around it. Even if the current location of the tracked object is not accurate, when samples from the neighborhood of the current location are put in the positive bag, there is a good chance that this bag contains at least one image in which the object is nicely centered. MIL project page has more information for people who like to dig deeper into the inner workings of the MIL tracker.</p>

<h2>KCF Tracker</h2>

<p>KFC stands for Kernelized Correlation Filters. This tracker builds on the ideas presented in the previous two trackers. This tracker utilizes that fact that the multiple positive samples used in the MIL tracker have large overlapping regions. This overlapping data leads to some nice mathematical properties that is exploited by this tracker to make tracking faster and more accurate at the same time.</p>

<h2>TLD Tracker</h2>

<p>TLD stands for Tracking, learning and detection. As the name suggests, this tracker decomposes the long term tracking task into three components — (short term) tracking, learning, and detection.this track appears to track an object over a larger scale, motion, and occlusion. If you have a video sequence where the object is hidden behind another object, this tracker may be a good choice.</p>

<h2>MEDIANFLOW Tracker</h2>

<p>Internally, this tracker tracks the object in both forward and backward directions in time and measures the discrepancies between these two trajectories. Minimizing this ForwardBackward error enables them to reliably detect tracking failures and select reliable trajectories in video sequences.</p>

<h2>GOTURN tracker</h2>

<p>Out of all the tracking algorithms in the tracker class, this is the only one based on Convolutional Neural Network (CNN). From OpenCV documentation, we know it is “robust to viewpoint changes, lighting changes, and deformations”. But it does not handle occlusion very well.</p>

<h2>MOSSE tracker</h2>

<p>Minimum Output Sum of Squared Error (MOSSE) uses adaptive correlation for object tracking which produces stable correlation filters when initialized using a single frame. MOSSE tracker is robust to variations in lighting, scale, pose, and non-rigid deformations.
it is also very easy to implement, is as accurate as other complex trackers and much faster. </p>

<h2>CSRT tracker</h2>

<p>In the Discriminative Correlation Filter with Channel and Spatial Reliability (DCF-CSR), we use the spatial reliability map for adjusting the filter support to the part of the selected region from the frame for tracking. This ensures enlarging and localization of the selected region and improved tracking of the non-rectangular regions or objects. It uses only 2 standard features (HoGs and Colornames). It also operates at a comparatively lower fps (25 fps) but gives higher accuracy for object tracking.</p>
