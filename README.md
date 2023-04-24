# Linear- and Logistic Regression
## This repo is dedicated to two widely known algorithms used under supervised learning, linear regression and logisitc regression which is often called classification.
### There are 4 functions used in Linear regression:

### **Compute Cost**
  - #### Description: Compute Cost is a function which finds the accumulative loss function of every training example and returns this accumulutation multiplied by $\frac{1}{2m}$.            The formula looks as follows:
    $$J(wb) = \frac{1}{2m} \sum_{i=1}^{m}(f_{w,b}(x^{(i)}) - y^{(i)})^2$$
    
### **Normalize Data**
  - #### Description: Normalize data is a function which scales the feature to allow for a higher model accuracy, and lower cost value. In this linear regression example we predict the prices of a house given 3 features, sqft, bedroom quantity, and at last the floors. Bedroom quantity and floor amount are numbers which resemble each other, floating around values ranging from 1-4, whereas sqft can have a value which is far over that scale, which is very inefficient for the model especially during gradient descent, which can be shown by following image:![4 plots, where the two on the left show plots that are scaled and unscaled, and on the right two cost function countour plots, where one is scaled and the other isnt](https://raw.githubusercontent.com/TernFolbaek/linear-and-logistic-regression/main/normalization.img)
  
### **Compute Gradient**
 - #### Description: Compute gradient returns the gradient for every w parameter and b parameter for each training example, first looping through "m" amount of times, and thereafter a nestood loop of "j" iterations to retrieve the gradient of every feature coefficient. Which looks as following:
     $$\frac{dJ(w,b)^{(i)}}{db} = (f_{w,b}(x^{(i)}) - y^{(i)})$$
     $$\frac{dJ(w,b)^{(i)}}{dw} = (f_{w,b}(x^{(i)}) - y^{(i)})x_j^{(i)}$$
   And at last return the total gradient from all training examples:
   $$\frac{\partial J(w,b)}{\partial b}  = \frac{1}{m} \sum\limits_{i = 0}^{m-1} \frac{\partial J(w,b)}{\partial b}^{(i)}$$
    
    $$\frac{\partial J(w,b)}{\partial w}  = \frac{1}{m} \sum\limits_{i = 0}^{m-1} \frac{\partial J(w,b)}{\partial w}^{(i)}$$

 
### **Gradient descent**
  - #### Description:
