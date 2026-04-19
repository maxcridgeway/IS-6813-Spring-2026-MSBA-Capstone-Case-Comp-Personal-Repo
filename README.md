# IS-6813-Spring-2026-MSBA-Capstone-Case-Comp-Personal-Repo

## README: Summary of business problem and project objective.
MasterControl provides quality and manufacturing management software to life sciences companies — pharma, biotech, and medical device manufacturers where they sell two core product lines. Qx (Quality Solutions), which is the established product with 20+ years in the market, and Mx (Manufacturing Solutions), which is the newer product with roughly 4 years in the market so far. Leads enter the sales pipeline as Qualified Activity Leads (QALs) and are worked by Sales Development Representatives (SDRs) who attempt to progress them through stages: Recycled, Excluded, SQL, SQO, or Won. The core problem is that in the current state of the pipeline, Mx converts QALs to SQL at 12.7% in comparison to Qx, which has a conversion rate of 19.7%. This represents significant unrealized pipeline value for a product that MasterControl is actively investing in growing. The sponsor believes the gap may stem from targeting, i.e., Mx may be getting pitched to the wrong types of companies or the wrong people within those companies, rather than reflecting a product quality issue. SDRs have limited daily call and email capacity and currently lack a systematic, data-driven method for deciding which leads to contact next. With that in mind, the goal of the project is a ranking system of which types of leads to contact, not just a list. 

## README: Your group's solution to the business problem.
Our solution to the business problem stated above involved the following steps. First, we performed exploratory data analysis in order to discern the most useful variables that would be used in building our predictive models. This involved visualizations to identify which variables were most strongly correlated with each other, as well as with the target variable ‘is_success’. Next, we worked on building the models' predictive models, including the following.

* Logistic Regression (our baseline)
* Random Forest
* MLP-based neural network
* CatBoost
* XGBoost
* LightGBM
* GradientBoosting
* ElasticNet
* BalancedBagging
* StackingEnsemble
* VotingEnsemble

Once the models were built, we went through the process of tuning the hyperparameters associated with them to maximize our AUC, Sensitivity, and Specificity scores, which were our main KPIs for measuring the model performance. We then chose the model that we found to be the best mix of all three KPIs as our final predictive model, which, in our case, happened to be the Voting Ensemble model. This model is used to predict the likelihood of success for a Qualified Activity Lead to convert to SQL, SQO, or Won stage.

## README: Your contribution to the project
For this project, my contribution started with the business problem statement, where I helped to edit the general structure and specified the details and timeline for our group. I also created the confusion matrix we would be basing the logic for our true positive rate, true negative rate, and any other KPIs on. I also helped to edit the exploratory data analysis notebook. Thomas had taken the reins on it, and I was very satisfied with the work he had done. For our final modeling notebook, I created and tuned all of the following models found within the project.

* MLP
* ElasticNet
* BalancedBagging

I also worked to create many of the feature-engineered variables used within our models to help gain more predictive power. Here are those variables, as well as a quick classification of what they are attempting to model.

* ‘account_penetration_count',      # Buying Committee Density
* 'has_cross_functional_interest',  # Buying Committee Cross-Interest
* 'weekend_warrior',                # Digital Body Language (Recency)
* 'form_depth_score',               # Digital Body Language (Intent)
* 'exec_momentum_score',            # Title/Intent Interaction
* 'channel_momentum',               # Channel/Recency Interaction
* 'high_compliance_risk',           # Regulatory Pressure
* 'is_growth_tier_decision_maker',  # Growth Tier Power
* 'regulatory_urgency_score',       # Risk/Seniority Interaction
* 'is_technical_gatekeeper',        # Semantic Gatekeeper Flag
* 'title_length_ratio',             # Semantic Complexity
* 'is_niche_specialist'             # Semantic Specialist Flag

I also worked as an editor to ensure the overall structure of the code throughout each notebook was consistent and cohesive with the style of that document (variable names, comments, etc.). Once presenting our findings, I edited and presented the sections from our slide deck relating to the modeling approach, model evaluation, and model explainability using SHAP analysis. Finally, I worked as a facilitator when our group would meet to discuss our project and the next steps that would need to be taken throughout the project.

## README: The business value of the solution.
Using our best performing model, the Voting Ensemble model, we achieved an AUC-ROC curve of 0.915, a TPR of 79.7%, and a TNR of 87.0%. These scores are immensely useful if adopted, as it shows that the model is very accurate at predicting which QALs will progress to the next step in the sales pipeline and which will churn. In fact, using an optimal profit configuration  in our final notebook, we calculated that at the optimal threshold of 0.076, we would expect 297 of the 951 leads to be contacted and captured as SQLs. Assuming an SQL represents a generation of $6000 in revenue and an outreach cost of $50, we calculated that the adoption of our model could produce a net profit of $1,734,450 ((6000 * 297) - (50 * 951) = 1734450). Thus, the accuracy and interpretability of our model can work to boost the company's bottom line by informing their sales team what type of companies to go after and who within those companies to target.

## README: Difficulties that your group encountered along the way.
There were many difficulties that our group faced throughout the project. The first was the difficulty of sifting through all of the data provided to discern the variables/information that would be helpful in our predictions versus those that would just add noise and confusion to our models. Our next difficulty was deciding how to deal with missing data from our observations, as we needed that data to be present to build our models, but we also wanted to make sure it was representative of true values. Finally, one of the greatest difficulties was the scheduling that needed to take place to balance the work being done on the project, our other classes within the MSBA program, and outside obligations (family, work, etc.). All this being said, I believe we handled each hurdle gracefully, and I could not ask for a better group to have completed the project with. (For more information about how the data difficulties were addressed, see our RMD files, where comments are provided when needed.)

## README: Final Notes
As a note about the project, our group did not realize that the GitHub assignment was supposed to be individual until recently. For that reason, I have uploaded the files associated with the project that I deemed I had a personal hand in finalizing. These files are a mix of personal notebooks and versions of group notebooks that had been submitted. Regardless, I believe the notebooks and this README provide enough context to discern what everybody’s individual contributions were to the project. It is for that same reason that you will only see a couple of commits to my personal repo this README is attached to, as we worked to continually email the versions of each notebook back and forth as needed throughout the project (aka made life harder for ourselves). Also, during the process of this final commit, I could not get JupyterLab to load on my personal machine. That is the IDE I had been using to generate our final modeling submission from the file ‘mastercontrol_model_v13-Max_Copyv2.ipynb’ and while I could load it on JupyterNotebook, it could not run all the cells as of today, 04/19/26. If need be, you can recreate on JupyterLab using the file and should get the same results as our file ‘Modeling Assignment Final Submission.html’.
