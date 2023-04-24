# Linear- and Logistic Regression
## This repo is dedicated to two widely known algorithms used under supervised learning, linear regression and logisitc regression which is often called classification.
### There are 4 functions used in Linear regression:
### **Compute Cost**
  - #### Description: Compute Cost is a function which finds the accumulative loss function of every training example and returns this accumulutation multiplied by $\frac{1}{2m}$.            The formula looks as follows:
    $$J(wb) = \frac{1}{2m} \sum_{i=1}^{m}(f_{w,b}(x^{(i)}) - y^{(i)})^2$$
### **Normalize Data**
  - #### Description: Normalize data is a function which scales the feature to allow for a higher model accuracy, and lower cost value. In this linear regression example we predict the prices of a house given 3 features, sqft, bedroom quantity, and at last the floors. Bedroom quantity and floor amount are numbers which resemble each other, floating around values ranging from 1-4, whereas sqft can have a value which is far over that scale, which is very inefficient for the model especially during gradient descent, which can be shown by following images:
- 
