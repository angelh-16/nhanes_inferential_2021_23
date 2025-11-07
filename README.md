# HHA507 - Assignment 4: NHANES 2021-2023 Inferential Analytics Assignment

This assignment uses data from National Health and Nutrition Examination Survey (NHANES) to perform basic inferential statistics using Python on Google Colab. Then trying to do the same in the language R. The purpose is to explore relationships and differences in health metrics and demographic variables.

- NHANES Data: [NHANES 2021-2023](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2021-2023)

## Data Preparation

NHANES variables for analysis:

- **Marital Status** (`DMDMARTZ`) - categorical, needs recoding (married or not married).
- **Education Level** (`DMDEDUC2`) - categorical, needs recoding (bachelor’s or higher vs. less than bachelor’s).
- **Age in Years** (`RIDAGEYR`) - continuous.
- **Systolic Blood Pressure** (`BPXOSY3`) - continuous.
- **Diastolic Blood Pressure** (`BPXODI3`) - continuous.
- **Vitamin D Lab Interpretation** (`LBDVD2LC`) - categorical, two levels.
- **Hepatitis B Lab Antibodies** (`LBXHBS`) - categorical, needs recoding to two levels.
- **Weak/Failing Kidneys** (`KIQ022`) - categorical, can be treated as two levels.
- **Minutes of Sedentary Behavior** (`PAD680`) - continuous, needs cleaning (remove values `7777`, `9999`, and null).
- **Current Self-Reported Weight** (`WHD020`) - continuous, needs cleaning (remove values `7777`, `9999`, and null).

## Questions for Analysis

**1. "Is there an association between marital status (married or not married) and education level (bachelor’s degree or higher vs. less than a bachelor’s degree)?"
     - Variables: `DMDMARTZ` (marital status) and `DMDEDUC2` (education level). Recode as specified.**
       \
   There is an association between marital status and education level. 
   The table shows that a higher proportion of married individuals have a bachelor’s degree or higher compared to those not married. Out of a total of 7,772 people, among the not married individuals, 27.2% have a bachelor’s degree or higher while those married, 39.5% have a bachelor’s degree or higher.
   After conducting a chi-square test, χ² was found to be 129.174, degrees of freedom was 1, and p-value was 6.213 × 10⁻³⁰. With p < 0.001, the association between marital status and education level is statistically significant.

**2. "Is there a difference in the mean sedentary behavior time between those who are married and those who are not married?"  
     - Variables: `DMDMARTZ` (marital status, recoded) and `PAD680` (sedentary behavior time, cleaned).**
       \
     There is a difference in the mean sedentary behavior time between those who are married and those who are not married.
     The table showed a total of 7,709 individuals that on average, not married individuals (3,603) spend more time in sedentary behavior with 3721.96 minutes than married individuals(4,106) with 353.29 minutes.
     After conducting the t test, it was found that t = 3.851 and p = 0.0001184. There is statistically significant difference in the mean sedentary behavior time between those who are married and those who are not married since p < 0.05.
     
**3. "How do age and marital status affect systolic blood pressure?"  
     - Variables: `RIDAGEYR` (age), `DMDMARTZ` (marital status, recoded), and `BPXOSY3` (systolic blood pressure).**
       \
     Both age and marital status significantly affect systolic blood pressure, with age having a larger impact.
     The Regression Results shows a total of 5,838 individuals. With the coef of age being 0.3952 and p < 0.0.001, each year of age increases systolic blood pressure by 0.395 mmHg on average. As age increases, so does systolic blood pressure. While the coef of married is -1.342 and p = 0.003, meaning being married lowers systolic blood pressure by 1.342 mmHg compared to not married. Additionally, with R² being 0.134, age and marital status together explain about 13.4% of the variation in systolic blood pressure. The model is statistically significant as f = 453.3 and p < 0.001.

**4. "Is there a correlation between self-reported weight and minutes of sedentary behavior?"  
     - Variables: `WHD020` (self-reported weight, cleaned) and `PAD680` (sedentary behavior time, cleaned).**
       \
There is a correlation between self-reported weight and minutes of sedentary behavior.
After conducting the pearson correlation, r was found to be 0.156 and p < 0.001. This shows the correlation is statistically significant, but the strength is weak. There is a small positive association between weight and sedentary behavior, with weight increasing slightly as sedentary behavior increases.

**5. "Is there an association between education level and being overweight?"
     - Variables: DMDEDUC2  (education level) and WHD020 (self-reported weight, cleaned).**
       \
     There is no association between education level and overweight status. Education does not appear to influence the likelihood of being overweight in this sample.
     The table shows overweight is present is both education groups, with 99.9% overweight having less than a bachelor and 100% overweight with a bachelor or higher. 
     After conducting a chi-square test, χ² was found to be 1.272, degrees of freedom was 1, and p-value was 0.259. With p ≥ 0.05, the association between education level and overweight status is not statistically significant. The Chi-square test was chosen because it helps test whether two categorical variables are independent, which matches the question of whether overweight status is dependent on education level.





