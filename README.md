# Website Phishing Prediction/Classification

Developed a model that predicts/classifies whether a website is a Phishing website based on various features.

## Dataset
The dataset contains 31 columns, with 30 features and 1 target. The dataset has 2456 observations. As part of the dataset we have below columns, which are used to classify the URL as phishing or not:

Rule: { -1 → Phishing, 0 → Legitimate, Otherwise → Legitimate   Otherwise→ Legitimate }



* having_IP_Address { -1,1 }  
      * Rule: {If the Domain Part has an IP Address → Phishing   Otherwise→ Legitimate }

* URL_Length { 1,0,-1 }   
      * Rule: {If URL length <54 → Legitimate  else if URL length 54 and 75 → Suspicious   Otherwise → Phishing }

* Shortining_Service { 1,-1 }   
      * Rule: {TinyURL → Phishing   Otherwise → Legitimate }

* having_At_Symbol { 1,-1 }   
      - Rule: {If Url Having @ Symbol → Phishing   Otherwise → Legitimate }

* double_slash_redirecting { -1,1 }   
      * Rule:  {If the Position of the Last Occurrence of "//" in the URL > 7→ Phishing      Otherwise→ Legitimate }

* Prefix_Suffix { -1,1 }
      * Rule:  {If Domain Name Part Includes (-) Symbol → Phishing    Otherwise → Legitimate }

* having_Sub_Domain { -1,0,1 }    
      * Rule: {If Domain Name Part Includes (-) Symbol → Phishing     Otherwise → Legitimate }

* SSLfinal_State { -1,1,0 }   
      * Rule: {If Use https and Issuer Is Trusted and Age of Certificate 1 Years → Legitimate    Else If Using https and Issuer Is Not Trusted  → Suspicious       Otherwise → Phishing }

* Domain_registeration_length { -1,1 }
      * Rule: {If Domains Expires on 1 years → Phishing    Otherwise → Legitimate }

* Favicon { 1,-1 }    
      * Rule: {If Favicon Loaded From External Domain → Phishing     Otherwise → Legitimate }


* port { 1,-1 } 
      * Rule: {If Port # is of the Preffered Status → Phishing     Otherwise → Legitimate }

* HTTPS_token { -1,1 }    
      * Rule: {If Using HTTP Token in Domain Part of The URL → Phishing     Otherwise → Legitimate }

* Request_URL { 1,-1 } 
      * Rule: {If % of Request URL <22% → Legitimate     Else if % of Request URL≥22% and 61% → Suspicious     Otherwise → Phishing  }


* URL_of_Anchor { -1,0,1 }    
      * Rule:  {If % of URL Of Anchor <31%  → Legitimate      Else if% of URL Of Anchor ≥31% And≤67% → Suspicious       Otherwise → Phishing }

* Links_in_tags { 1,-1,0 } 
      * Rule: {If % of Links in "<Meta>", "<Script>" and "<Link>"<17%  → Legitimate     Else if % of Links in <Meta>", "<Script>" and "<Link>" ≥17% And≤81% → Suspicious      Otherwise → Phishing }

* SFH { -1,1,0 }    
      * Rule: {If SFH is "about: blank" Or Is Empty → Phishing      Else if SFH Refers To A Different Domain → Suspicious      Otherwise  → Legitimate }

* Submitting_to_email { -1,1 }    
      * Rule: {If Using "mail()" or "mailto:" Function to Submit User Information → Phishing     Otherwise  → Legitimate }

* Abnormal_URL { -1,1 }   
      * Rule: {If The Host Name Is Not Included In URL → Phishing     Otherwise → Legitimate }

* Redirect { 0,1 }   
      * Rule: {If #ofRedirect Page≤1 → Legitimate     Else if #of Redirect Page≥2 And<4 → Suspicious     Otherwise → Phishing }

* on_mouseover { 1,-1 }  
      * Rule: {If onMouseOver Changes Status Bar → Phishing      Else if It Does't Change Status Bar → Legitimate }

* RightClick { 1,-1 }  
      * Rule: {If Right Click Disabled → Phishing     Otherwise → Legitimate }


* popUpWidnow { 1,-1 }   
      * Rule: {If Popoup Window Contains Text Fields→ Phishing      Otherwise → Legitimate }

* Iframe { 1,-1 }   
      * Rule: {If Using iframe → Phishing     Otherwise → Legitimate }

* age_of_domain { -1,1 }   
      * Rule: {If Age Of Domain≥6 months → Legitimate     Otherwise → Phishing }

* DNSRecord { -1,1 }   
      * Rule: {If no DNS Record For The Domain → Phishing     Otherwise → Legitimate }

* web_traffic { -1,0,1 }   
      * Rule: {If Website Rank<100,000 → Legitimate     Else if Website Rank>100,000 → Suspicious     Otherwise → Phishing }

* Page_Rank { -1,1 }   
      * Rule: {If PageRank<0.2 → Phishing     Otherwise → Legitimate  }

* Google_Index { 1,-1 }  
      * Rule: {If Webpage Indexed by Google → Legitimate      Otherwise → Phishing }

* Links_pointing_to_page { 1,0,-1 }  
      * Rule: {If #Of Link Pointing to The Webpage=0 → Phishing     Else if #Of Link Pointing to The Webpage>0 and≤2 → Suspicious     Otherwise → Legitimate }

* Statistical_report { -1,1 }  
      * Rule: {If Host Belongs to Top Phishing IPs or Top Phishing Domains → Phishing     Otherwise → Legitimate }

* Result { -1,0 }  
      * Rule: {If  0 → Phishing    Else If 1 → Legitimate }
