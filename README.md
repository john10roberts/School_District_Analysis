# School_District_Analysis
Python Pandas School District Data Analysis

## Overview of Project
The school board has determined that the student data shows evidence of academic dishonesty; specifically, reading and math grades for Thomas High School ninth graders.  The board does not know the full extent of the dishonesty and have requested that the scores for Thomas High School be updated to uphold state-testing standards. It is determined that the best course of action is to: 
- Replace the ninth grade reading and math scores from Thomas High School
- Repeat the school district analysis using the updated reading and math scores for         Thomas High School 

### Purpose
Update the school district analysis to uphold state-testing standards. 

## Analysis and Challenges
Began by importing the schools_complete and the students_complete csv files.  Did some initial cleaning of the data sources to replace unappropriate prefixes and suffixes.  Next, we filtered the student data to only show Thomas High 9th graders and replaced all the reading and math scores with NaN.  The scores were removed to allow us to get an accurate breakdown of Thomas High School in relation to peers. 

### District Analysis
    District Prior to Changes
        - Average Math Scores - 79.0
        - Average Reading Scores - 81.9
        - % Passing Math - 75.0
        - % Passing Reading - 85.8
        - % Overall Passing - 65.2

    ![DistrictBefore](https://github.com/john10roberts/School_District_Analysis/blob/main/Resources/DistrictBefore.png)
    
        District After to Changes
        - Average Math Scores - 78.9
        - Average Reading Scores - 81.9
        - % Passing Math - 74.8
        - % Passing Reading - 85.7
        - % Overall Passing - 64.9
  
    ![DistrictBefore](https://github.com/john10roberts/School_District_Analysis/blob/main/Resources/DistrictBefore.png)

    The district appears relatively unchanged after the changes to the 9th graders at Thomas High      

    
### School Analysis
    Thomas High School Scores With 9th Graders as NaN
        - Average Math Scores - 83.35
        - Average Reading Scores - 83.90
        - % Passing Math - 66.91
        - % Passing Reading - 69.66
        - % Overall Passing - 65.08

    ![Thomas High Before](https://github.com/john10roberts/School_District_Analysis/blob/main/Resources/ThomasHighBefore.png)

    Thomas High School Scores After Removing 9th Graders
        - Average Math Scores - 83.35
        - Average Reading Scores - 83.90
        - % Passing Math - 93.19
        - % Passing Reading - 97.02
        - % Overall Passing - 90.63

    ![Thomas High After](https://github.com/john10roberts/School_District_Analysis/blob/main/Resources/ThomasHighAfter.png)

    The scores for Thomas High increased dramatically after removing the ninth graders with changes in passing scores of 25+ points for every category.  

### Top 5 Schools 
    After the changes to the 9th grade class as Thomas High, Thomas High remains in the top 5 schools and remains as the second overall best school.  Prior to the changes Thomas High had an overall passing percentage of 90.95.  After removing the 9th graders, the overall passing percentage decreassed to 90.63.  This change was not enough to remove them from the second overall position. 

    ![Top 5 Before](https://github.com/john10roberts/School_District_Analysis/blob/main/Resources/Top5Before.png)

    ![Top 5 After](https://github.com/john10roberts/School_District_Analysis/blob/main/Resources/Top5After.png)

### Math and Reading Scores by Grade
    After making the changes to the 9th Graders at Thomas High the math and reading scores by grade level remains unchanged for 10, 11, and 12th grade.  Because all the 9th graders now have a NaN grade for math and reading, they do not show scores, so the result is a NaN value. 

### Scores by School Spending, Size and Type
    After making the changes for the 9th graders and because the only values updated in the data frame were the scores (there was no change to the number of students).  The values for all these fields are equal to the previous analysis provided. 

    However, if you were to remove the 9th Grade students completely     ![(see PyCitySchools_Challenge_testingThomas9thRemoved)](https://github.com/john10roberts/School_District_Analysis/blob/main/Resources/PyCitySchools_Challenge_testingThomas9thRemoved.ipynb) then Thomas High School spending per student goes from $638 to 889.  This change creates a new upper level in our bins and changes the original $645-675 bin to 645-890.  The 630-644 bins would see all off the averages decrease with a major change in overall passing rate.  

    The change in the overall school size of Thomas from 1635 to 1174 is not significant enough to move the school from its current postion of medium size school (1000 - 2000 enrollment).  Because of that there is no impact to the average scores based on School Type. 

    Also, because the removal of students has no impact on on the school type, there is no change in any of the scores based on school type. 

## Summary
The district analysis will remain largely unchanged after updating the 9th Grade Students from Thomas High school.  The school analysis will change based on how we choose to either include each of the 9th Grade Students as either NaN or omit those scores.  If the scores are allowed to Remain NaN Thomas High goes from a school that has 90% of its students passing overall vs 65% passing.  Depending on how the 9th Grade is handled could potentially take Thomas from the 2nd overall rated school down to the bottom 10 schools. If only the students from 10-12 at Thomas are included, then Thomas would still be considered a top two overall passing school.   The changing of the grades for Thomas High will change the averages by grades to NaN values while the rest of the scores will remain consistent with the previous analysis. 


