# Linear- and Logistic Regression
## This repo is dedicated to two widely known algorithms used under supervised learning, linear regression and logisitc regression which is often called classification.
### Linear regression:
### **Compute Cost**
  - #### Description: Compute Cost is a function which finds the accumulative loss function of every training example and returns this accumulutation multiplied by $\frac{1}{2m}$.            The formula looks as follows:
    $$J(wb) = \frac{1}{2m} \sum_{i=1}^{m}(f_{w,b}(x^{(i)}) - y^{(i)})^2$$
    
### **Normalize Data**
  - #### Description: Normalize data is a function which scales the feature to allow for a higher model accuracy, and lower cost value. In this linear regression example we predict the prices of a house given 3 features, sqft, bedroom quantity, and at last the floors. Bedroom quantity and floor amount are numbers which resemble each other, floating around values ranging from 1-4, whereas sqft can have a value which is far over that scale, which is very inefficient for the model especially during gradient descent, which can be shown by following image:![4 plots, where the two on the left show plots that are scaled and unscaled, and on the right two cost function countour plots, where one is scaled and the other isnt](https://raw.githubusercontent.com/TernFolbaek/linear-and-logistic-regression/main/normalization.img)
  
### **Compute Gradient**
 - #### Description: Compute gradient returns the gradient for every w parameter and b parameter for each training example, first looping through "m" amount of times, and thereafter a nestood loop of "j" iterations to retrieve the gradient of every feature coefficient. Which looks as following:
     $$\frac{dJ(w,b)^{(i)}}{db} = (f_{w,b}(x^{(i)}) - y^{(i)})$$
     $$\frac{dJ(w,b)^{(i)}}{dw} = (f_{w,b}(x^{(i)}) - y^{(i)})x_j^{(i)}$$
   #### And at last return the total gradient from all training examples:
   $$\frac{\partial J(w,b)}{\partial b}  = \frac{1}{m} \sum\limits_{i = 0}^{m-1} \frac{\partial J(w,b)}{\partial b}^{(i)}$$
    
    $$\frac{\partial J(w,b)}{\partial w}  = \frac{1}{m} \sum\limits_{i = 0}^{m-1} \frac{\partial J(w,b)}{\partial w}^{(i)}$$

 
### **Gradient descent**
  - #### Description: Gradient descent is then iteratively used to find the optimal w,b parameter values. It does this by iterating x amount of times, starting with updating the gradient of each parameter, thanks to the "compute gradient" function. Thereafter w, and b parameters are updated as following:
      $$w = w-\alpha *  \frac{\partial J(w,b)}{\partial w}$$
      $$b = w-\alpha *  \frac{\partial J(w,b)}{\partial b}$$
    #### in this case the "=" is not used as the equality sign, but as the assignment operator. w is an array in this case, where its dimension "n" is corresponds to quantity of features.

### Logistic Regression
#### Logistic Regression utilizes the same functions as Linear regression, however in this specific case we regularize our training model. 
### **Compute Sigmoid**
 - #### Description: The model for logistic regression varies from that of linear regression since we compute the sigmoid which looks as follows:   $$f_{\mathbf{w},b}(x) = g(\mathbf{w}\cdot \mathbf{x} + b)$$
 

   #### Where the formula for sigmoid (g) is displayed as:
   
   $$g(z) = \frac{1}{1+e^{-z}}$$
 
### **Compute Cost**
 - #### Description: The compute cost function for logistic regression looks different to that of linear regression since we deal with the output values of 0-1. The equation is as shown:
 $$loss(f_{\mathbf{w},b}(\mathbf{x}^{(i)}), y^{(i)}) = (-y^{(i)} \log\left(f_{\mathbf{w},b}\left( \mathbf{x}^{(i)} \right) \right) - \left( 1 - y^{(i)}\right) \log \left( 1 - f_{\mathbf{w},b}\left( \mathbf{x}^{(i)} \right) \right) \tag{2}$$    
 #### in the above equation if the target value of y = 1, then the right hand side of the equation will be removed, and vice versa where y = 0 then the left hand side of the equation will be removed. This equation allows us to aggregate the loss funciton of both desired outcomes which allows for optimized code. Now that this logistic regression algorithm utilizes regularization throughout the entirety of the process we will evolve the cost function to look as following: $$J(\mathbf{w},b) = \frac{1}{m}  \sum_{i=0}^{m-1} \left[ -y^{(i)} \log\left(f_{\mathbf{w},b}\left( \mathbf{x}^{(i)} \right) \right) - \left( 1 - y^{(i)}\right) \log \left( 1 - f_{\mathbf{w},b}\left( \mathbf{x}^{(i)} \right) \right) \right] + \frac{\lambda}{2m}  \sum_{j=0}^{n-1} w_j^2$$ 
 #### The prefix: $\frac{1}{m}  \sum_{i=0}^{m-1}$ is nothing different, simply gets the accumulation of above loss functions and multiplies it to retrieve the average. What is different is the suffix: $\frac{\lambda}{2m}  \sum_{j=0}^{n-1} w_j^2$ , which is what brings in the regularization. What regularization does is that it accumulates the value of every parameter w squared, and therafter gets the average value which is at last added onto the cost value. Which punishes the parameter values since the algorithms purpose is to minmize the cost function, hence minimizing w parameters, diminishing potential overfitting in the model.
  

### **Compute Gradient**
 - #### Description: Compute gradient in a regularized algorithm is nearly the same except for the update rule for $w_j$

### **Compute Gradient Descent**
 - #### Description:


