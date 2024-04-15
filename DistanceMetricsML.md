# DISTANCE METRICS IN MACHINE LEARNING  

## INDEX: IMPORTANCE > TYPES-REPRESENTATIONS > WHEN-TO-USE > PYTHON-LIB

### IMPORTANCE:
    1. To make decisions by understanding the pattern of input data.
    2. Algorithms makes decisions based on proximity
    3. Helps in improving performance of Classifications, Clustring, Informations Retrival tasks.
    4. Measure similiarity and dissimilarity between data-points.
    
### TYPES-REPRESENTATIONS: Most commonly used metrics =>
1. Euclidean Distance: 
    - Straight line distance between two data-points in Euclidean space.
    - Calculated as the square root of the sum of the squared differences between corresponding coordinates.
    - Formula: 
                
                 ![Euclidean Distance](https://latex.codecogs.com/svg.latex?d(\mathbf{p}, \mathbf{q}) = \sqrt{\sum_{i=1}^{n} (q_i - p_i)^2})
                

2. Manhattan Distance: 
    - It is the sum of the absolute differences between the coordinates of two points.
    - Manhattan distance is also known as [Taxicab Geometry](https://en.wikipedia.org/wiki/Taxicab_geometry).
    - Formula:
                
                   d(p,q)= `$d(\mathbf{p}, \mathbf{q}) = \sum_{i=1}^{n} |q_i - p_i|$`
                
3. Minkowski Distance:
    - A generalization of the Euclidean and Manhattan distances.
    - Distance metric exponent `p` is a parameter. When `p=1`, it's the Manhattan distance, and when `p=2`   
            it's the Euclidean distance.
    - Formula:
                
                  d(p,q)= `$d(\mathbf{p}, \mathbf{q}) = \left( \sum_{i=1}^{n} |q_i - p_i|^p \right)^{1/p}$`
                
4. Cosine Similarity: 
    - Measures the cosine of the angle between two vectors.
    - Mostly used in text mining and document similarity tasks.
    - Often used when the vectors orientation is more important than magnitude of vectors.
    - Formula:
                
                  d(p,q)= `$\text{cosine similarity}(\mathbf{p}, \mathbf{q}) = \frac{\mathbf{p} \cdot \mathbf{q}}{\|\mathbf{p}\| \|\mathbf{q}\|}$`
                
5. Hamming Distance: 
    - Specifically designed for categorical data. 
    - Often used and apt for comparing sequences, such as DNA sequences or binary strings.
    - Formula:
                
                  d(p,q)= `$d(\mathbf{p}, \mathbf{q}) = \sum_{i=1}^{n} (p_i \neq q_i)$`
                

### WHEN-TO-USE
    * Choice of the metric depends on the data characteristics and the specific requirements of the ML task.
    * The most suitable way to choose a good metrics for your task is `Experimentation and Validation`

### PYTHON-LIB
    
    1. Scipy (scipy.spatial.distance):
            ```
             from scipy.spatial import distance
             euclidean_distance= distance.euclidean([1, 2], [4, 5])
             manhattan_distance= distance.cityblock([1, 2], [4, 5])
             minkowski_distance= distance.minkowski([1, 2], [4, 5], p=3)
             cosine_similarity = distance.cosine([1, 2], [4, 5])
             hamming_distance  = distance.hamming([1, 0, 1], [1, 1, 1])

            ```
    2. Scikit-learn (sklearn.metrics.pairwise):
            ```
                from sklearn.metrics.pairwise import euclidean_distances, manhattan_distances, cosine_similarity
                
                euclidean_distance= euclidean_distances([[1, 1]], [[7, 7]])
                manhattan_distance= manhattan_distances([[1, 1]], [[7, 7]])
                cosine_similarity = cosine_similarity([[1, 1]], [[7, 7]])

            ```
    3. NumPy: 
        3.1 Itself does not have built-in distance functions like SciPy or Scikit-learn.
        3.2 Often used for manual implementation due to powerful array operations
