# About:

From scratch implementations of **Principal Component Analysis (PCA)** (dimensionality reduction) and **K-Means** (classification) unsupervised learning algorithms in python, using human face images from https://www.kaggle.com/competitions/11785-spring2021-hw2p2s1-face-classification/data

You can also find an implementation of **Singular Value Decomposition (SVD)** that can be employed in cooperation with PCA or used instead of PCA to obtain dimensionality reduction.

# Preparation:
images.zip found in "data" directory contains 10 directories, each containing 50 human face images. Thus, we have 500 observations to classify.
Every image, after being loaded, is grayscaled using PIL's Image module and converted into a numpy array (function: **grayscale_and_convert_to_nparray**).

Note that you can transform image into bi-level representation instead of grayscaling it, which yields even better classification results.
To achieve that, simply pass **'1'** as actual parameter in img.convert() function (function: **grayscale_and_convert_to_nparray**) instead of **'L'**.

• Before grayscale:

![0257_01](https://user-images.githubusercontent.com/48795138/177875797-334eec48-1332-4ba3-80c8-8455011dbd71.jpg)

• After grayscale:

![test_gray](https://user-images.githubusercontent.com/48795138/177875850-606213f1-55c7-4eb8-b8bd-a38e788fbf89.jpg)

• After bi-leveling:

![ggg](https://user-images.githubusercontent.com/48795138/177879103-af7f4c5f-7e47-4e86-9ad7-719c34644a87.jpg)


# Using PCA and K-Means implementation:
• PCA class constructor takes 1 argument (**n_components**), which corresponds to the number of principal components the user wishes to employ in order to transform the data into a lower dimension.

• kmeans class constructor takes 2 arguments. The first argument (**k**) is the number of clusters the user wishes to partition the 500 observations into. The second argument (**init**), specifies the initialization technique used to obtain the first centroids before entering the actual classification process. The 2 options are kmeans++ (maxmin) and random initialization. In order to use the first option, simply pass "kmeans++" as second actual parameter (init="kmeans++"). Any other string passed as second parameter will initialize centroids randomly.

# Visualizing the dimensionality reduction (using SVD):

• Initial image (d = 4096):

![d4096](https://user-images.githubusercontent.com/48795138/178166196-34f709f2-a328-4cb9-9f38-4aa49cf60841.jpg)

• Reduced to d = 250 dimensions:

![d250](https://user-images.githubusercontent.com/48795138/178166212-41a0d626-8624-4391-b4ed-5f55a388993d.jpg)

• Reduced to d = 50 dimensions:

![d50](https://user-images.githubusercontent.com/48795138/178166222-12259d2a-9659-49a5-84e6-34af6c27708a.jpg)

• Reduced to d = 1 dimension:

![d1](https://user-images.githubusercontent.com/48795138/178166235-e67806f4-58a5-46cf-b93f-ae14728a4b09.jpg)


# Visualizing the clusters:
After reducing the dataset's dimension to 2 for the sake of visualization using PCA, we have the following results:
![b_plot_3](https://user-images.githubusercontent.com/48795138/177870030-aacdc6be-a508-469c-89e1-36f55dfd46f6.jpg)

![b_plot_5](https://user-images.githubusercontent.com/48795138/177870349-4405020b-a821-4a96-8e5d-b95a609b9637.jpg)

![b_plot_7](https://user-images.githubusercontent.com/48795138/177870853-b975c93e-36e1-43c1-8b46-3371ddbf9b32.jpg)

![b_plot_10](https://user-images.githubusercontent.com/48795138/177871123-3d483ca6-ff7e-439a-a58e-29680e9920af.jpg)


