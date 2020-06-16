# Lesson plan for participants
## Summer Institute in Computational Social Science 2020
## Activity, Day 4: Non-probability-based Surveys in Practice
## Matthew Salganik & Robin Lee [1]

Please read the entire lesson plan before beginning.

## Summary

How accurate are estimates from non-probability-based online surveys? In this activity, you will conduct a survey of MTurk workers, produce unweighted and weighted estimates, and then compare your estimates to those that come from high-quality probability-based sample. This activity was inspired by a paper written by Sharad Goel, Adam Obeng, and David Rothschild: [Online, Opt-in Surveys: Fast and Cheap, but are they Accurate?](https://5harad.com/papers/dirtysurveys.pdf) The survey that you will partially replicate was done by the [Pew Research Center](https://www.pewresearch.org/) on [public attitudes toward computer algorithms](https://www.pewresearch.org/internet/2018/11/16/public-attitudes-toward-computer-algorithms/).

### Learning objectives

Participants will gain experience with the following activities:
- reading survey results and methodology reports
- creating questionnaires on Google Forms [Note: This assignment uses Google Forms because it is free. See the end of this lesson plan for comments about using [Qualtrics](https://www.qualtrics.com/), a more sophisticated platform that requires payment or institutional support.]
- deploying surveys on MTurk
- data wrangling and weighing non-probability samples
- using the total survey error framework to reason about and discussion sources of errors in estimates

### Before group activity

- Read [Chapter 3 in *Bit by Bit*](https://www.bitbybitbook.com/en/1st-ed/asking-questions/)
- Read the [Mathematical notes in Chapter 3 in *Bit by Bit*](https://www.bitbybitbook.com/en/1st-ed/asking-questions/sampling-mathematical/)
- Read the paper that motivated this activity: [Online, Opt-in Surveys: Fast and Cheap, but are they Accurate?](https://5harad.com/papers/dirtysurveys.pdf) by Goel et al. In this paper, the researchers conduct an opt-in, non-probability survey of people on MTurk. They compared the raw sample estimates and those made after various weighting adjustments to estimates that come from surveys using probability-based sampling methods.
- Read [Intro to Poststratification](https://github.com/compsocialscience/summer-institute/blob/master/2020/materials/day4-surveys/activity/introduction_to_poststratificiation.md)

### Activity schedule
- 2 hour and 45 minutes
    - 1 hour in the morning: prepare and deploy surveys
    - break for lunch while data is being collected on MTurk
    - 1 hour and 45 minutes in the afternoon
      - 15 minutes: validate survey responses and pay MTurk participants
      - 60 minutes: analyze a larger dataset that we collected for you
      - 30 minutes: discuss activity

## During group activity
### Morning session:
1. Create a questionnaire on Google Forms. When you are done, your questionnaire will look a bit like [this one](https://docs.google.com/forms/d/e/1FAIpQLSeBrHa4c5r_DcewQJWE9vrAeqpfN7mxx9QWZO852ItAOL22tA/viewform) (30 minutes).
  - Start with our template questionnaire that already contains a consent statement, attention check questions, and questions about demographics. You will obtain the link for editing access to this template on our Slack workspace. Make a copy of the template.
  - Fill in section 2 with survey questions from the Pew Research Center [topline report](https://www.pewresearch.org/internet/wp-content/uploads/sites/9/2018/11/PI_2018.11.16_algorithms_TOPLINE.pdf) from their study on [public attitudes toward computer algorithms](https://www.pewresearch.org/internet/2018/11/16/public-attitudes-toward-computer-algorithms/). You should add to your questionnaire all the questions binary response options. We focused on the binary response options because those make the analysis in the afternoon easier.  There are 6 binary questions: ALG1, SM3, V1Q1, V2Q3, V3Q3, V4Q3.
  - Pilot test the questionnaire and confirm that can be completed within 6 minute.

2. Deploy your survey to Amazon Mechanical Turk (30 minutes).
  - You will request a task as "Survey Link".
  - [Here](https://blog.mturk.com/tutorial-getting-great-survey-results-from-mturk-and-google-forms-da4993d878df) is a blog post tutorial on how to a deploy Google Forms questionnaire on MTurk.
  - We estimate that the survey will take about 6 minutes, and we would like to pay an hourly wage of $15 per hour so you should pay $1.50 per completed survey.
  - For participants of SICSS-Duke: We have created MTurk accounts for you to use. Please create your tasks from these accounts with the pre-loaded funds. If you use your own account for data collection, we won't be able to reimburse you.
  - If you do not have funds allocated for MTurk, you may ask other participants and your friends and family to fill in the survey to construct a non-probability-based sample.
  - An alternative to Amazon Mechanical Turk is [Prolific](https://www.prolific.co/)

### Afternoon session:
1. After the data has been collected, validate survey and pay MTurk workers (15 minutes).
  - Download the CSV of responses from Google Forms.
  - Check to make sure that all of your MTurk workers actually took the survey by comparing the list of Worker IDs provided in the survey data against the Worker IDs recorded by the MTurk platform. [2]
  - Delete responses that did not meet the attention check criteria.
  - Pay MTurk workers that completed valid surveys.
  - Remove redundant entries, if any.
  - After you have used the Worker ID data to validate answers and to remove redundant entries, delete it from your dataset. The Worker ID is a unique string that can be used to personally identify people.

2. Analyze the data we previously collected (60 minutes).
  - Cost constraints mean that each group can only collect a small number of responses.  Therefore, we have collected one large dataset that all the groups can analyze. Download the data that we collected with this [questionnaire] (https://docs.google.com/forms/d/e/1FAIpQLSf_FRPaGbeqgVAOasEgSHjGIIYiaFoT8JHd-AW-5aEI4adWrQ/formResponse) from MTurk workers [here](2020_06_clean_mturk_data.csv).
  - Compare the raw (unweighted) estimates to the [results found by Pew](pew_benchmark_question_source_sicss_2020.csv) [3]. Next compare the estimates after doing [cell-based post-stratification]. Use [this template](survey_activity_2020_template.Rmd) as you work through these steps.  The template will help you replicate Figures 1 and 2 from Goel et al. and avoid some common pitfalls.
  - Due to the time constraint, you won't be able to do techniques as complicated in the paper by Goel et al. However, those sections are marked as optional extension in the template code, and we provide the instruction on how to do them in the code [here](survey_activity_2020_solution.Rmd).

## Additional resources
  - [Here](https://psrc.princeton.edu/our-services/using-mturk) are some more resources on web surveys and [here](https://mturkpublic.s3.amazonaws.com/docs/MTURK_BP.pdf) is Amazon's best practices for MTurk Requesters.
  - Dutwin and Buskirk. ["Apples to Oranges or Gala versus Golden Delicious?: Comparing Data Quality of Nonprobability Internet Samples to Low Response Rate Probability Samples"](https://academic.oup.com/poq/article/81/S1/213/3749202/Apples-to-Oranges-or-Gala-versus-Golden-Delicious)
  - Baker et al. ["Summary Report of the AAPOR Task Force on Non-probability Sampling"](https://academic.oup.com/jssam/article/1/2/90/941418/Summary-Report-of-the-AAPOR-Task-Force-on-Non)
  - Kalton and Flores-Cervantes ["Weighting methods"](http://www.jos.nu/Articles/abstract.asp?article=192081)
  - Berinsky, Margolis, and Sances ["Separating the Shirkers from the Workers? Making Sure Respondents Pay Attention on Self‐Administered Surveys"](https://doi.org/10.1111/ajps.12081)
  - [Target Estimation and Adjustment Weighting for Survey Nonresponse and Sampling Bias](https://www.cambridge.org/core/books/target-estimation-and-adjustment-weighting-for-survey-nonresponse-and-sampling-bias/B28F1B4CC17B42D513EC3E0356926C23)
  - [Pewmethods R package](https://github.com/pewresearch/pewmethods)

## Appendix: Qualtrics-specific instructions
-   If you are using Qualtrics instead of Google Forms, you do not have to include a question on the survey asking for MTurk Worker ID. Instead, you can verify survey completion by generating a unique validation code for each survey respondent, and have them enter that on MTurk instead.

-   Here are [detailed instructions](https://blog.mturk.com/getting-great-survey-results-from-mturk-and-qualtrics-be1704ff9786) for generating survey completion codes.

-   Qualtrics has more features and customizable options -- for example, you can randomize the response options to a survey question or enable more sophisticated skip logic. Try playing around with these!

## Footnotes
[1] This activity was designed with input from participants and TAs from SICSS 2017 - 2019, especially Yo-Yo Chen, Janet Xu, and Cambria Naslund.  
[2] Tip: to validate WorkerID matches, you can download a CSV of WorkerIDs from your MTurk results page and match that with your survey results data.  
[3] Technical note: Most survey questions have a "don't know/refuse" residual category, but predicting the percentage of people who refused to answer may not always be substantively relevant. To omit this category from the analysis, we normalized the existing survey results by dividing by the percentage of people who responded to that question.  
