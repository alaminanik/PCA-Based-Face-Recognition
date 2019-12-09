# PCA-Based-face-Recognition

<p>It's hard to find a real-life implementation of this old algorithm nowadays, but other research was based on this. Furthermore, this algorithm's simplistic and effective nature makes it very beautiful.</p>

To train the model:<br><br>
1.-Flat the black and white images of the training set (from matrices to vectors)<br>
2.-Calculate the mean.<br>
3.-Normalize the training set: for each image, subtract the mean.<br>
4.-Calculate the covariance: multiply all images by themselves.<br>
5.-Extract eigenvectors from the covariance.<br>
6.-Calculate eigenfaces: eigenvectors x normalized pictures.<br>
7.-Choose the most significant eigenfaces.<br>
8.-Calculate weights: chosen eigenfaces x normalized pictures.<br>

<p>Imagine a picture of a face as a [m x n] image matrix. We convert each matrix into [(m x n) x 1] image vector. Thus, each face can be represented as a vector and the whole set of faces will represent a vector space of dimension m x n x N, where N is the images of all faces. This space is large. And it needs to be described with a training set of faces with Train Images. The training sample needs to be projected into this space, where each dimension will give a certain contribution to the overall presentation. The principal component method (PCA) allows us to find the basis space in such a way that the data in it are located, in a sense, optimally. Thus we can construct a new basis of smaller dimensions so that its components will carry maximum information. Leaving the dimensions with only useful information, we obtain a feature space in which each image of the original sample is presented in a generalized form. Next, we take an image from the Test set, we can map it to a pre-created space and determine which image of the training sample our example is closest to.
If it is at a relatively large distance from all the data, then this image is more likely to not belong to our database at all. After applying the following algorithm, We see that the first 24 components carry almost 100% of the information. Select them.
Next we will display each training image in the space of the main components and find the weights. After the vector w is known, it is necessary to determine which of the existing objects it is closest to. Is the minimum distance and index of the object to which this image is located closest.</p>

<p>If we input an image that is not in the source database, the vector w will still be calculated and the minimum distance will be found. Therefore the criterion t0 is introduced, if the minimum distance < t0
this means that the image belongs to the recognizable class if the minimum distance is > t0, then there is no such image in the database. The value of this criterion is chosen empirically.</p>




