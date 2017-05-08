ABSTRACT

Scientific publications and other genres of research output are increasingly cited in policy documents. Citations in documents of this  nature could be considered a critical indicator of the significance and societal impact of the research output. In this work, we have  built classification models that predict whether a particular research work is likely to be cited in a public policy document based on the  attention it received online, primarily on social media platforms. We evaluated the classifiers based on their accuracy, precision and  recall values. We found that Random Forest and Multinominal Naive Bayes classifiers performed best.

DATASET

The dataset in this study is a database dump that we obtained from altmetric.com, which consists of 5.2 million articles. Our initial analysis showed that 89,350 articles have atleast one policy citation and 5,097,207 articles have no citation in any policy document. To create a balanced dataset for further analysis, along with the 89,350 articles that have been cited in policy documents, we randomly chose  another 89,350 articles that did not receive any citation in policy documents. The result was a balanced dataset with approximately  180,000 records, half of them being cited in policy documents.

FEATURE SELECTION 

The dataset has a very rich set of features for each article but for our analysis, we have considered only the features related to online  attention. The dataset consists of mention counts on various online sources including reference managers, main stream newsoutlets, blogs,  peer-review platforms (e.g., PubPeer and Publons), social media, public policy documents, and Wikipedia. We used mention counts in Twitter, Facebook, Reddit, Mendeley, Google+, Wikipedia, Weibo, main stream newsoutlets, blogs, videos, and peer-review paltforms as features to build the classifiers. A few sources were not considered. "Connotea" that has been discontinued since 2013 and two other sources, "Pinterest" and "Stackoverflow" contributed to less than 1% of the articles in the sample. We replaced the policy citation count with a binary class label denoting whether or not the article had been cited in policy documents. 

METHODS

To predict the likelihood of a research article being cited in a policy document, we implemented three classifiers which include Multinomial Naive Bayes, Random Forest with number of trees set at 100, and a C-Support Vector Machine with the Radial Basis Function(RBF) kernel. We then divided the entire dataset in to training and test sets comprising of 80% and 20% of the entire dataset respectively. The models were trained using 10 fold cross validation technique and evaluated based on the accuracy, precision, recall, and F1-measure metrics.

With the classification models built, we calculated weights for each feature to determine their significance in making the final prediction. Since feature weights in the case of Support Vector Machines can only be determined for linear kernels, we ranked features based on their relevance only to the Random Forest and Multinomial Naive Bayes classifiers.We ranked the features in decreasing order of their importance to the Random Forest classifier.
 
FILES

Convert_policy_data_to_csv.ipynb - Code to extract the required features from the articles that are mentioned in atleast one policy document.

NonPolicyRandomData.ipynb - Code to randomly choose 89,350 non-policy articles and extract the required features from each of them.

MultinomialNaiveBayes.ipynb - 10-fold cross validated training and testing using Multinominal Naive bayes classifier 

RandomForest.ipynb - 10-fold cross validated training and testing using Random forest classifier.

SVM.ipynb - 10-fold cross validated training and testing using C-Support Vector Machine with the RBF kernel.
