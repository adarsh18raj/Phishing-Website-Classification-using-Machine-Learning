# Phishing Website Classification using Machine Learning
Phishing is an online crime that tries to trick unsuspected users to expose their sensitive (and valuable) personal information, for example, usernames, passwords, financial account details, personal addresses, SSN, and social relationships, to the miscreant, often for malicious reasons. Phishing is normally perpetrated by disguising as a trustworthy entity in Internet communication which is achieved by combining both social engineering and technical tricks.

## Objective
Develop a model that predicts/classifies whether a website is a Phishing website.

## Dataset
The dataset contains 31 columns, with 30 features and 1 target. The dataset has 2456 observations. As part of the dataset we have following columns, which are used to classify a website as phishing or Legitimate:

###### Rule: { -1 → Phishing, 0 → Suspicious, Otherwise → Legitimate }



1. having_IP_Address { -1,1 }  
      * Rule: {If the Domain Part has an IP Address → Phishing,   Otherwise→ Legitimate}

2. URL_Length { 1,0,-1 }   
      * Rule: {If URL length <54 → Legitimate,  else if URL length 54 and 75 → Suspicious,   Otherwise → Phishing}

3. Shortining_Service { 1,-1 }   
      * Rule: {TinyURL → Phishing,   Otherwise → Legitimate}

4. having_At_Symbol { 1,-1 }   
      * Rule: {If Url Having @ Symbol → Phishing,   Otherwise → Legitimate}

5. double_slash_redirecting { -1,1 }   
      * Rule:  {If the Position of the Last Occurrence of "//" in the URL > 7→ Phishing,      Otherwise→ Legitimate}

6. Prefix_Suffix { -1,1 } 
      * Rule:  {If Domain Name Part Includes (-) Symbol → Phishing.    Otherwise → Legitimate}

7. having_Sub_Domain { -1,0,1 }    
      * Rule: {If Domain Name Part Includes (-) Symbol → Phishing,     Otherwise → Legitimate}

8. SSLfinal_State { -1,1,0 }   
      * Rule: {If Use https and Issuer Is Trusted and Age of Certificate 1 Years → Legitimate,    Else If Using https and Issuer is not Trusted  → Suspicious,       Otherwise → Phishing}

9. Domain_registeration_length { -1,1 } 
      * Rule: {If Domains Expires on 1 years → Phishing,    Otherwise → Legitimate}

10. Favicon { 1,-1 }    
      * Rule: {If Favicon Loaded From External Domain → Phishing,     Otherwise → Legitimate}

11. port { 1,-1 } 
      * Rule: {If Port # is of the Preffered Status → Phishing,     Otherwise → Legitimate}

12. HTTPS_token { -1,1 }    
      * Rule: {If Using HTTP Token in Domain Part of The URL → Phishing,     Otherwise → Legitimate}

13. Request_URL { 1,-1 } 
      * Rule: {If % of Request URL <22% → Legitimate,     Else if % of Request URL≥22% and 61% → Suspicious,     Otherwise → Phishing}

14. URL_of_Anchor { -1,0,1 }    
      * Rule:  {If % of URL Of Anchor <31%  → Legitimate,      Else if% of URL Of Anchor ≥31% And≤67% → Suspicious       Otherwise → Phishing}

15. Links_in_tags { 1,-1,0 } 
      * Rule: {If % of Links in "<Meta>", "<Script>" and "<Link>"<17%  → Legitimate,     Else if % of Links in <Meta>", "<Script>" and "<Link>" ≥17% And≤81% → Suspicious,      Otherwise → Phishing}

16. SFH { -1,1,0 }    
      * Rule: {If SFH is "about: blank" Or Is Empty → Phishing,      Else if SFH Refers To A Different Domain → Suspicious,      Otherwise  → Legitimate}

17. Submitting_to_email { -1,1 }    
      * Rule: {If Using "mail()" or "mailto:" Function to Submit User Information → Phishing,     Otherwise  → Legitimate}

18. Abnormal_URL { -1,1 }   
      * Rule: {If The Host Name Is Not Included In URL → Phishing,     Otherwise → Legitimate}

19. Redirect { 0,1 }   
      * Rule: {If #ofRedirect Page≤1 → Legitimate,     Else if #of Redirect Page≥2 And<4 → Suspicious,     Otherwise → Phishing}

20. on_mouseover { 1,-1 }  
      * Rule: {If onMouseOver Changes Status Bar → Phishing,      Else if It Does't Change Status Bar → Legitimate}

21. RightClick { 1,-1 }  
      * Rule: {If Right Click Disabled → Phishing,     Otherwise → Legitimate}

22. popUpWidnow { 1,-1 }   
      * Rule: {If Popoup Window Contains Text Fields→ Phishing,     Otherwise → Legitimate}

23. Iframe { 1,-1 }   
      * Rule: {If Using iframe → Phishing,     Otherwise → Legitimate}

24. age_of_domain { -1,1 }   
      * Rule: {If Age Of Domain≥6 months → Legitimate,     Otherwise → Phishing}

25. DNSRecord { -1,1 }   
      * Rule: {If no DNS Record For The Domain → Phishing,     Otherwise → Legitimate}

26. web_traffic { -1,0,1 }   
      * Rule: {If Website Rank<100,000 → Legitimate,     Else if Website Rank>100,000 → Suspicious,     Otherwise → Phishing}

27. Page_Rank { -1,1 }   
      * Rule: {If PageRank<0.2 → Phishing,     Otherwise → Legitimate}

28. Google_Index { 1,-1 }  
      * Rule: {If Webpage Indexed by Google → Legitimate,      Otherwise → Phishing}

29. Links_pointing_to_page { 1,0,-1 }  
      * Rule: {If # of Link Pointing to The Webpage=0 → Phishing,     Else if #Of Link Pointing to The Webpage>0 and≤2 → Suspicious,     Otherwise → Legitimate}

30. Statistical_report { -1,1 }  
      * Rule: {If Host Belongs to Top Phishing IPs or Top Phishing Domains → Phishing,     Otherwise → Legitimate}

31. Result { 0,1 }  
      * Rule: {If  0 → Phishing,    Else If 1 → Legitimate}
      
      

## Data Exploration and PreProcessing

1. Created a dataframe 'data' to extract the data into it.
2. data.info() and data.isna().sum shows the information about the data including the null values. This dataset doesn't have null values and it's clean.
3. In order to understand the distibution of data, I've plotted the count values of some features and I've carried out descriptive statistics as well.
4. Data should be split into training and test. After analysing for overfitting and underfitting conditions, I have split them as 80% for Training and 20% for Testing for better accuracy.


## Training the Model
Since it is a classification problem, I've applied different classification algorithms and used the following models:
1. Logistic regression
2. Decision tree 
3. XG Boost
4. Random Forest



## Evaluating and Testing the model: 
I've calculated accuracy, precision, recall and F-score to choose the best model for prediction. I've also used Area under the curve and confusion matrix in order to find which model is a good fit and how accurately the model is predicting values.



| Model Used  | Accuracy  |
|---|---|
|Logistic Regression   | 0.93 |
|Decision Tree   | 0.91 |
|XG Boost   | 0.95 |
|Random Forest   | 0.98 |


## Conclusion
Among all the classification algorithms applied in this project to classify whether a website is a Phishing website, Random Forest turns out to be the best one as it gives the accuracy of 98%. 



If you have any query, feel free to contact me at adarsh18raj@gmail.com
