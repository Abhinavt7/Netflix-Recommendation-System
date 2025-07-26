# Netflix-Recommendation-System

The primary objective of this project is to explore the domain of Collaborative Filtering, a class of recommendation algorithms that leverages the "wisdom of the crowd" to make predictions. Instead of analyzing movie content, it analyzes user behavior, operating on the principle that users who agreed in the past will likely agree in the future.

This project systematically implements and compares three distinct collaborative filtering models, each representing a different level of sophistication:

1. The Foundational Baseline Model
Before diving into complex algorithms, it is essential to establish a performance benchmark. The project begins by implementing a Baseline Model which predicts ratings based on a simple but effective heuristic: the combination of global, user, and item biases. It calculates a baseline rating by considering the average rating of all movies, how much a specific user deviates from that average (are they a tough critic or easily pleased?), and how much a specific movie deviates from the average (is it a universally acclaimed film or a niche title?). This model serves as the "common sense" yardstick against which more advanced techniques are measured.

2. Matrix Factorization with Singular Value Decomposition (SVD)
The core of modern collaborative filtering lies in Matrix Factorization, and this project implements the renowned Singular Value Decomposition (SVD) algorithm. This technique addresses the immense sparsity of the user-item interaction matrix (where most users have not rated most movies) by decomposing it into two smaller, dense matrices of "latent factors." These factors represent unspoken, underlying properties of users and movies. For a movie, a latent factor might represent its genre affinity, its level of action, or its comedic tone. For a user, it might represent their preference for those same properties. A user's predicted rating for a movie is then calculated by taking the dot product of their respective latent factor vectors, providing a nuanced prediction far beyond simple averages.

3. The Advanced SVD++ Model
To push the boundaries of accuracy, the project culminates in the implementation of SVD++, an powerful extension of the SVD algorithm. SVD++ enhances its predecessor by incorporating implicit feedback. While standard SVD only considers explicit feedback (e.g., a user's 4-star rating), SVD++ also models the information implied by the mere act of a user rating a movie, regardless of the score. It operates on the insight that the set of all movies a user has interacted with provides a rich, holistic signal about their profile. By integrating this implicit information, SVD++ gains a more complete view of user preferences, leading to demonstrably superior prediction accuracy.

--Evaluation and Final Outcome

Each model is rigorously evaluated using 5-fold cross-validation to ensure robust and generalizable results. The primary performance metric is the Root Mean Squared Error (RMSE), which measures the average magnitude of prediction errors and is particularly sensitive to large, inaccurate predictions.
As hypothesized, the results confirm a clear hierarchy of performance, with SVD++ emerging as the most accurate model. The final, trained SVD++ model is then serialized and saved to a file. This portable artifact is used to power a practical recommendation function that can take any user ID and generate a personalized, ranked list of top-N movie recommendations, completing the journey from raw data to a functional, intelligent system.

--Technology Stack:

Core Language: --Python 3

Data Manipulation: Pandas, NumPy

Recommendation Engine: scikit-surprise

Data Visualization: Matplotlib, Seaborn

Development Environment: Google Colaboratory (Jupyter Notebook)
