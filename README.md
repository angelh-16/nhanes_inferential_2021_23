# HHA507 - Assignment 4: NHANES 2021-2023 Inferential Analytics Assignment

This assignment uses data from National Health and Nutrition Examination Survey (NHANES) to perform basic inferential statistics using Python in Google Colab. The purpose is to explore relationships and differences in health metrics and demographic variables.

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

1. "Is there **an association** between marital status (married or not married) and education level (bachelor’s degree or higher vs. less than a bachelor’s degree)?"  
     - Variables: `DMDMARTZ` (marital status) and `DMDEDUC2` (education level). Recode as specified.

2. "Is there **a difference in the mean** sedentary behavior time between those who are married and those who are not married?"  
     - Variables: `DMDMARTZ` (marital status, recoded) and `PAD680` (sedentary behavior time, cleaned).

3. "How do age and marital status affect systolic blood pressure?"  
     - Variables: `RIDAGEYR` (age), `DMDMARTZ` (marital status, recoded), and `BPXOSY3` (systolic blood pressure).

4. "Is there a **correlation** between self-reported weight and minutes of sedentary behavior?"  
     - Variables: `WHD020` (self-reported weight, cleaned) and `PAD680` (sedentary behavior time, cleaned).

5. (Creative Analysis): Develop your own unique question using at least one of the variables listed above. Ensure that your question can be answered using one of the following tests: chi-square, t-test, ANOVA, or correlation. Clearly state your question, explain why you chose the test, and document your findings.
