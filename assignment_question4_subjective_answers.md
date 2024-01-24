## Goal

The target is to plot time taken to fit and predict the Decision tree model against varying N - number of samples and M - number of features.
We have plotted the time taken to fit and predict the model against M and N. We have also plotted the standard deviation in time taken to fit and predict the model against M and N.

## Results
For each type of Decision Tree i.e.,

1. Discrete Input and Discrete output
2. Discrete Input and Real output
3. Real Input and Discrete output
4. Real Input and Real output
   
We have 4 plots, one for each of the following

1. Average Time to fit the model
2. Average Time to predict the model
3. Standard Deviation in Time to fit the model
4. Standard Deviation in Time to predict the model
So, in total we have 16 plots.

## Discrete input and Discrete Output
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/f49b154e-9dcb-4b9a-bbca-8fde71394974)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/3f11f036-d319-428c-b661-22b989aa8963)

As we can see from the above plot, the time taken to fit the model increases with the number of samples and number of features. The time taken to predict the model is dependent on the input. The prediction ends soon in some cases and takes a lot of time in some cases. But the average time taken to predict the model is almost increases with respect to the number of samples and number of features.

![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/935d0a73-d264-41d8-b204-ee2bcb4234eb)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/60fbc339-5693-4563-acac-f17b351647a5)

##  Discrete Input Real Output
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/0ab6f7e4-6e20-4c89-b51c-4b3cbf033945)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/b7abccf0-540c-4250-9a96-a5ba2b116042)

![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/5bede41a-bcee-4889-a795-8022c936fdb2)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/99270d80-301a-419a-9ccd-ce140ef58b14)

## Real Input and Disceret Output
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/df982ebe-b82e-4ec5-98d0-a30ddeda189d)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/bdf298f9-98ea-4cf7-a3b6-99c47bdd2d6b)

As we can see from the above plot, the time taken to fit and predict the model increases with both number of samples and number of features. The average time to predict has random flashes which shows dependence on input.

![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/a0ec6f6f-ae50-472f-b777-d053e01ec361)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/276250ed-b642-4adc-99dc-6efd56c4d0a8)

## Real Input Real Output
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/923d74f0-8c4b-4808-8f55-3e58c41ab2aa)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/28edbd43-afe1-460f-89a4-e4160d65af25)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/5b8a0403-6fee-4bf8-8522-6557dfcf6425)
![image](https://github.com/Kareena-Beniwal/ML-assignment---1/assets/76513375/4d8c9416-7baa-4326-94e3-f95c9fc7764f)

# Conclusions

due to limitation of time and computing power of our system we could only test for small values of N and M.

For large values of N and M, we can check the mathematical time complexity of the model in following ways:

The theoretical time complexity varies depending upon the types of input provided.

### Discrete Input:
M - no of features/attributes
N - samples
Depth of the tree in case of discrete inputs = M
For each level in the decision tree, we require O((M-level)N) runtime to get the nodes. we require O(N) to find the information of (M-level) attributes 

So as we increase the levels from zero to M, the total runtime will be of the order O(NM + (M-1)N + (M-2)N +......+  N ) = O(M(M+1)N) = $O(M^2*N)$

## Real Input:

In worst-case scenario, when tree becomes unbalanced and each node has only one child, the depth would be equal to the number of samples N. Since, at each level, the algorithm selects a feature and a split point that maximizes information gain, potentially leading to a binary split. If, at each step, one side of the split contains only one sample, the tree depth grows with the number of samples.

In the best-case scenario, where the tree is perfectly balanced, the depth would be of order of $O(log N)$. This would occur when, at each level, the algorithm makes balanced binary splits, dividing the data into two equal parts.

Therefore, Depth of the tree = $O(N)$ [worst case scenario]
                             = $O(log N)$ [balanced tree- optimal depth]

For each level in the decision tree, to select the attribute and find the split value we need O(M)*O(N logN + N^2) = O(MN^2)
Here:               $NlogN$ => sorting the instances to find the split
                    $N^2$   =>   find the split and information gain


Thus , the total runtime = $O(MN^3)$ [worst case scenario]
                         = $O(MN^2(log N))$ [balanced tree- optimal depth]

