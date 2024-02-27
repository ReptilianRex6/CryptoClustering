# CryptoClustering 

GitHub Copilot assisted me in this Challenge by helping me understand concepts of Kmeans. 

I also used code from the week 11 activity files for finding the best value for K since it was basically the same thing save a few variable name changes. 

GitHub Copilot recomended implimenting code to assist with local memory issues

```
import os
os.environ["OMP_NUM_THREADS"] = "1"
```

For determining the weights of the features in PCA, I was running into errors saying 
>ValueError: Shape of passed values is (3, 7), indices imply (7, 3)

GitHub Copilot explained the issue: 
> pca.components_ is a 2D array with a shape of (3, 7), but you're trying to create a DataFrame with an index of length 7 (scaled_data.columns) and columns of length 3 (["PCA1", "PCA2", "PCA3"]).
> To fix this issue, you should transpose pca.components_ before creating the DataFrame. This can be done using the numpy.transpose function or the T attribute of the numpy array. Here's how you can do it:
```
pca_weights_df = pd.DataFrame(np.transpose(pca.components_), columns=["PCA1", "PCA2", "PCA3"], index=scaled_data.columns)
```
