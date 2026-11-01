# Evidence map link check, November 1, 2026

Scope: every link on the map (2,874 records). 2,845 records carry a DOI; the map links each to https://doi.org/<DOI>, or to an override link where noted below.

## How each link was checked

1. Registration: each DOI was looked up at the doi.org handle service, which says whether the DOI exists and which page it points to.
2. Right paper: the title registered for each DOI (Crossref, DataCite, or the agency that issued it) was compared with the title the map shows.
3. Alive: each DOI's landing page was requested by script. Pages that publisher bot walls blocked, and every page that errored, were opened in a real web browser (Claude in Chrome), at least one from every publisher.

## Results

- DOIs registered and resolving: 2,840 of 2,844 checked by script, plus the new Iregbu et al. (2026) record, opened in Chrome.
- Landing pages that opened for the script: 1475. Behind publisher bot walls for the script (403, 202, 429): 1338, across 82 publisher sites; one or two from every site were opened in Chrome and all loaded the right article, except where a site shows a human-verification page (BMJ journals, PNAS, Health Affairs, ASHA, Nutrición Hospitalaria; SSRN passed on its own after a few seconds). A person passes those checks; I did not click them.
- Registered title differs from the map title: 14. Three are records shown in English translation of a Swedish, German or Portuguese title (fine). One differs only by formatting tags in the registry. One DOI points to a whole poster-abstract supplement rather than the single poster (10.4103/0019-5545.341957; flagged, left as is). Nine map titles were shortened or paraphrased versions of the real title, and a tenth was already flagged in the ledger; all ten now show the registered title:
  - 10.1111/add.16571: "Open banking transaction data and gambling harm" now reads "The relationship between gambling behaviour and gambling‐related harm: A data fusion approach using open banking data"
  - 10.1080/09638237.2019.1581350: "A psychological model of compulsive spending in bipolar disorder" now reads "Financial difficulties in bipolar disorder part 2: psychological correlates and a proposed psychological model"
  - 10.1080/09638237.2018.1521920: "Depression, anxiety and stress as predictors of later compulsive buying in bipolar disorder" now reads "Financial difficulties in bipolar disorder part 1: longitudinal relationships with mental health"
  - 10.3389/fpsyt.2022.810057: "FinTech and bipolar disorder: using financial data to support self-management (single-case)" now reads "Financial technologies (FinTech) for mental health: The potential of objective financial data to better understand the relationships between financial behavior and mental health"
  - 10.1007/s10899-021-10080-9: "Operationalizing DSM-5 gambling disorder criteria in online account tracking data" now reads "Applying the DSM-5 Criteria for Gambling Disorder to Online Gambling Account-Based Tracking Data: An Empirical Study Utilizing Cluster Analysis"
  - 10.48550/arxiv.2506.12605: "The Rise of AI Companions: How Human-Chatbot Relationships Influence Well-Being" now reads "The Rise of AI Companions: Interaction with AI Companions and Psychological Well-being"
  - 10.1098/rsos.220111: "Robust longitudinal links between loot box spending and problem gambling but not wellbeing" now reads "Loot box spending is associated with problem gambling but not mental wellbeing"
  - 10.3390/ijerph191811334: "That You Just Know You're Not Alone: Eating Disorder Recovery Accounts on Instagram as a Chance for Self-Help? A Qualitative Interview Study" now reads "“That You Just Know You’re Not Alone and Other People Have Gone through It Too.” Eating Disorder Recovery Accounts on Instagram as a Chance for Self-Help? A Qualitative Interview Study among People Affected and Self-Help Experts"
  - 10.21673/anadoluklin.1187327: "Online Gaming Features and Adolescents with ADHD" now reads "Online gaming features in adolescents with attention-deficit/hyperactivity disorder"
  - 10.2196/30900: "Real-time Affective States During Social Media Use Among a Clinical Sample of Depressed Adolescents: Exploring Use Patterns and Racial/Ethnic Differences" now reads "Exploring Use Patterns and Racial and Ethnic Differences in Real Time Affective States During Social Media Use Among a Clinical Sample of Adolescents With Depression: Prospective Cohort Study"

## Broken links and what replaced them

DOIs that do not exist at doi.org:
- 10.54039/ijcnis.v12i2.4529 (Alnfiai, audio CAPTCHA): wrong prefix; the correct DOI is 10.17762/ijcnis.v12i2.4529, opened in Chrome.
- 10.1192/j.eurpsy.2023.532 (Azeem, BDD in Pakistan) and 10.1192/j.eurpsy.2023.509 (Micanti, eating disorders since COVID-19): Cambridge prints these DOIs on the article pages but never registered them. The map now links to the Cambridge Core pages.
- 10.35248/2155-9600.21.s6.814 (Rossi, pro-ana in an Italian sample): the publisher never registered it. The map now links to the article on longdom.org, opened in Chrome.

Correct DOIs whose publisher page is broken, now linked to a free copy:
- 10.2174/1745017902016010024 and 10.2174/1745017901410010028 (Clinical Practice and Epidemiology in Mental Health): the publisher page loads blank. Now linked to PMC7254823 and PMC3962983.
- 10.9745/ghsp-d-20-00346 (Global Health: Science and Practice): the publisher returns a 404 page. Now linked to PMC8514037.
- 10.24869/psyd.2025.88 (Psychiatria Danubina): 502 Bad Gateway. Now linked to PubMed 40516084.

Correct DOIs whose publisher site did not load on November 1, with no free copy found (left as the DOI link; they may come back):
- 10.54393/pbmj.v5i1.205: pakistanbmj.com, timed out
- 10.21608/ijma.2023.175781.1557: ijma.journals.ekb.eg, timed out
- 10.37513/curj.v1i1.662: journals.library.cornell.edu, no longer resolves
- 10.31436/ijcs.v8i3.464: journals.iium.edu.my, no longer resolves
- 10.17219/pzp/84982: www.pzp.umed.wroc.pl, no longer resolves
- 10.6092/2612-4033/0110-2919: riviste.unime.it, unreachable
- 10.47836/pjssh.30.2.05: pertanika.upm.edu.my, unreachable
- 10.25911/5fbcd371429cb: ANU Open Research, 503
- 10.52180/1999-9836_2024_20_4_12_645_656: elibrary.ru, 403 in a browser too

## Records with no DOI

29 records had no DOI and no link. Links were found and opened in Chrome for 14 (CDC, WHO, NatCen, gov.uk, Eurostat, MMWR, PubMed, and one with a DOI). 15 still have no link:
- "You're Not Crazy": A Case of New-onset AI-associated Psychosis. (Joseph M. Pierre et al., 2026)
- Bipolar disorder and willingness to share financial data with fintech tools (survey) (Brozena J. et al., 2023)
- "I'm Literally Just Hoping This Will Work:" Obstacles Blocking the Online Security and Privacy of Users with Visual Disabilities (Napoli D et al., 2021)
- Facebook Use and Well-Being Among Army Veterans With PTSD (Daphna Yeshua-Katz, 2021)
- The Relationship between Orthorexia Nervosa, Anorexia Nervosa, and the Use of Instagram (Bülter, 2021)
- Achieving Anorexia: An Improbable but Possible Aspiration among College-Age Students (K. Goldberg, 2020)
- Blind and Human: Exploring More Usable Audio CAPTCHA Designs (Fanelle V et al., 2020)
- An Experimental Study on the Effects of Pro-Anorexia Content on Eating Disorder Development (Green, 2019)
- Bet You Can't Eat Just One: Binge Eating Disorder Promotion In American Food Advertising (Danowski, 2019)
- The use of social networking sites in adolescents and young adults: exploring the possible implications in youth mental health (Alice Barber, 2019)
- Exposure to fad diet advertising among youth and young adults in Canada (Brittany Cormier, 2018)
- Battling the Stigma: Combat Veterans' Use of Social Support in an Online PTSD Forum (Alexandru Stana et al., 2017)
- Qualitative study of overspending in bipolar disorder (Richardson T. et al., 2016)
- Social media and thinspiration (J. Dennison, 2016)
- Relationship between risk behaviors for orthorexia nervosa, social media and diets in nutrition students (De Oliveira et al., None)
