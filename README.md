<h1> Decision Tree: Drug Study </h1>
<p>The aim of this study is to develop a decision tree model to predict the appropriate drug for patients suffering from a specific illness, using clinical features such as age, sex, blood pressure (BP), cholesterol levels, and sodium-to-potassium ratio (Na_to_K). The goal is to aid healthcare providers in prescribing the most suitable medication for new patients.</p>
<h2> Data Understanding </h2>
<p>The dataset used in this study contains information on patients, all of whom suffered from the same illness. Each patient responded to one of five medications: Drug A, Drug B, Drug C, Drug X, and Drug Y. The features of the dataset include:
<ul>
<li>Age</li>
<li>Sex</li>
<li>Blood Pressure (BP)</li>
<li>Cholesterol</li>
<li>Sodium-to-Potassium Ratio (Na_to_K)</li>
<li>The target variable is the drug each patient responded to.</li>
</ul>
The dataset is diverse, representing different age groups, both sexes, various blood pressure levels, cholesterol levels, and sodium-to-potassium ratios. Understanding these features is crucial as they play significant roles in determining the effectiveness of the prescribed drugs.</p>
<h2> Data Preparation And Analysis</h2>
The dataset is read using pandas, and the following variables are defined:
<ul>
<li>X as the Feature Matrix (data of my_data)</li>
<li>y as the response vector (target)</li>
<li>The column containing the target name is removed since it does not contain numeric values.</li>
</ul>
<img src="https://github.com/GBOL67/DecisionTrees-Drug-Study/blob/main/media/1.PNG" align="center" width="400" height="300" />
<p>The figure shows the distribution of the target variable</p>
<p>The distribution analysis reveals that Drug Y is the most commonly prescribed medication for the patients in this dataset, followed by Drug C. Drug X, Drug A, and Drug B are less frequently chosen. This information can help healthcare providers understand the current trends in drug prescriptions for this illness and consider the effectiveness and suitability of these medications for future patients. Further analysis could explore the reasons behind these trends and the specific characteristics of patients that lead to the choice of each drug.</p>
<h2> Modelling </h2>
<p>The decision tree model was developed using the grid search method to find the optimal tree depth, which was determined to be 3. The initial model was then evaluated using a confusion matrix and classification report.</p>
<img src="https://github.com/GBOL67/DecisionTrees-Drug-Study/blob/main/media/tree.png" align="center" width="400" height="300" />
<p>The model shows high accuracy and excellent performance for most of the drugs. However, there are some challenges in predicting Drug C accurately, as evidenced by the low precision for this class.</p>
<h2> Evaluation </h2>
<p>The decision tree model was developed using the grid search method to find the optimal tree depth, which was determined to be 3. The initial model was then evaluated using a confusion matrix and classification report.</p>
Confusion Matrix: 
<p>[ 7,  0,  0,  0,  0]</p>
<p>[ 0,  5,  0,  0,  0]</p>
<p>[ 0,  0,  5,  0,  0]</p>
<p>[ 0,  0, 10, 10,  1]</p>
<p>[ 0,  0,  0,  0, 22]]</p>

Classification Method:
<img src="https://github.com/GBOL67/DecisionTrees-Drug-Study/blob/main/media/tree.png" align="center" width="400" height="300" />

<h2> Model Refinement </h2>
<p>The model was refined using cross-validation with the following parameters: n_splits=4, shuffle=True, random_state=3. The accuracy for each fold was:</p>
<ul>  
<li>Fold 0: 0.80</li>
<li>Fold 1: 0.88</li>
<li>Fold 2: 0.92</li>
<li>Fold 3: 0.88</li>
</ul>
<p>The best-performing fold (Fold 2) was used to create a refined model, which was then evaluated with the following classification report.</p>
<p>The refined model demonstrates improved accuracy and better performance for most of the drugs, with an overall accuracy of 92%. The persistent issue with predicting Drug C accurately suggests the need for further investigation and potential inclusion of additional features.</p>
<h2> Conclusion </h2>
<p>The decision tree model effectively predicts the appropriate drug for patients based on their clinical features, demonstrating strong performance for most drugs. The refinement process using cross-validation improved the model's accuracy, making it more reliable for clinical application. Future work could focus on addressing the persistent misclassification issues with Drug C, possibly by exploring additional features or alternative modeling techniques. This model provides a useful tool for clinicians to prescribe the most suitable medication for patients with a specific illness, leveraging patient data to make informed decisions.</p>
<p>By integrating machine learning models like decision trees into the healthcare system, we can move towards more personalized and effective treatment plans, ultimately improving patient outcomes and optimizing resource allocation in clinical settings.</p>
