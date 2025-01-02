# Possible notes for A2

## Loss function 

### Multiclass SVM Loss

The score of the corrent class should be higher than all the other scores

once the socre of the correct class is higher than all other class ( in some level ). We would call it no loss function 

Given an example \((x_i, y_i)\) where \(x_i\) is an image and \(y_i\) is the label:

Let \( s = f(x_i, W) \) be scores.

Then the SVM loss has the form:

\[ L_i = \sum_{j \neq y_i} \max(0, s_j - s_{y_i} + 1) \]



