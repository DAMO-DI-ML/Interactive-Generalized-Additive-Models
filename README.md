### Interactive GAM: An interactive and interpretable generalized additive model tool for electric load forecasting

Interactive generalized additive model (GAM) is an interpretable method which can incorporate specific domain knowledge in electric power industry for improved performance. Our method leverages piecewise linear functions and is optimized based on boosting framework. By utilizing the special structure of hinge functions and the boosting framework, our algorithm learns the interactive GAM model efficiently. Our interactive GAM outperforms current state-of-the-art GAMs and demonstrates good generalization ability in the cases of extreme weather events. To help the end users to use the model more easily, a user-friendly web-based tool is developed based on the interactive GAM. 

#### Usage:

Requirements: see the document requirements.txt

Install: (will update later)

#### How to train a GAM:

Replace the "data.csv" in ./data folder with your data file. The data file requires both features and column to be predicted. In our setting, we require the target column as "load". As a result, please manually rename the label column in your data file as "load". Next switch the interactive page to "sample weight editing page" and press the "Apply" button. Then the interactive GAM model is automatically trained. Once the model is trained, the interface will display the prediction of the model on training data and the "shape function editing page" will be enabled.

#### How to apply domain knowledge:

##### 1, Change the weight of training samples

Switch the interactive page to "sample weight editing page", and select the area you want to edit. Press "Increasing weight" or "Decreasing weight" button on the right of page. Our tool will record the times you pressed the button and adjust the weight in an exponential way. The sample weights are initialized as $1$. If the "Increasing weight" has been pressed for $K$ times, then the weight of the samples in this area is set to $2^K$. The user can modify the sample weights according to the fitting error, or some reference factor, which can be selected in the "Ref factor" drop-down menu. After editing the weight, you can press "Apply" button, then the model is retrained according to the new sample weights.
  
![page_1](./figs/page_1.png)

##### 2, Add constraints to the shape functions

Switch the interactive page to the "shape function editing page", and select the area you want to edit. Press "Increase", "Decrese", "Convex" or "Concave" buttons on the right of page to select different constraints. One can select multiple areas and apply different constraints. Once editing is complete, you can press "Apply" button, then the model is update to fitting these constraints meanwhile to increase the fitting error as small as possible. We plot the sample density to help the user to estimate how many samples will be affected due to the constraints applied.
 
![page_2](./figs/page_2.png)

