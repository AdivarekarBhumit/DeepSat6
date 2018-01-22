# DeepSat SAT-6
![sat_img](https://user-images.githubusercontent.com/26761067/35227875-4e13a46a-ffb5-11e7-8cc1-3f6c6439bd8e.png)

Originally, images were extracted from the National Agriculture Imagery Program (NAIP) dataset. The NAIP dataset consists of a total of 330,000 scenes spanning the whole of the Continental United States (CONUS). The authors used the uncompressed digital Ortho quarter quad tiles (DOQQs) which are GeoTIFF images and the area corresponds to the United States Geological Survey (USGS) topographic quadrangles. The average image tiles are ~6000 pixels in width and ~7000 pixels in height, measuring around 200 megabytes each. The entire NAIP dataset for CONUS is ~65 terabytes. The imagery is acquired at a 1-m ground sample distance (GSD) with a horizontal accuracy that lies within six meters of photo-identifiable ground control points.

The images consist of 4 bands - red, green, blue and Near Infrared (NIR). In order to maintain the high variance inherent in the entire NAIP dataset, we sample image patches from a multitude of scenes (a total of 1500 image tiles) covering different landscapes like rural areas, urban areas, densely forested, mountainous terrain, small to large water bodies, agricultural areas, etc. covering the whole state of California. An image labeling tool developed as part of this study was used to manually label uniform image patches belonging to a particular landcover class.

Once labeled, 28x28 non-overlapping sliding window blocks were extracted from the uniform image patch and saved to the dataset with the corresponding label. We chose 28x28 as the window size to maintain a significantly bigger context, and at the same time not to make it as big as to drop the relative statistical properties of the target class conditional distributions within the contextual window. Care was taken to avoid interclass overlaps within a selected and labeled image patch.

# Content
Each sample image is 28x28 pixels and consists of 4 bands - red, green, blue and near infrared.

The training and test labels are one-hot encoded 1x6 vectors

The six classes represent the six broad land covers which include barren land, trees, grassland, roads, buildings and water bodies.

Training and test datasets belong to disjoint set of image tiles.

Each image patch is size normalized to 28x28 pixels.

Once generated, both the training and testing datasets were randomized using a pseudo-random number generator.

# Dataset
Dataset can be downloaded from kaggle
https://www.kaggle.com/crawford/deepsat-sat6/
