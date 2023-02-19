# Student Performance - Excel Project 

## Introduction
The **Student Performance** dataset contains the personal data of students from several Portuguese colleges, as well as their scores in mathematics. Data and descriptions are available at the [link](https://archive.ics.uci.edu/ml/datasets/student+performance).

## Data set description
This data approach student achievement in secondary education of two Portuguese schools. The data attributes include student grades, demographic, social and school related features) and it was collected by using school reports and questionnaires. Two datasets are provided regarding the performance in two distinct subjects: Mathematics (mat) and Portuguese language (por).

**Attribute Information:**


| № | Attribute| Description 
| - |--------- | -------------------------------------------------------------------------------
| 1 | school   | student's school (binary: 'GP' - Gabriel Pereira or 'MS' - Mousinho da Silveira)  
| 2 | sex      | student's sex (binary: 'F' - female or 'M' - male)  
| 3 | age      | student's age (numeric: from 15 to 22)  
| 4 | address  | student's home address type (binary: 'U' - urban or 'R' - rural)  
| 5 | famsize  | family size (binary: 'LE3' - less or equal to 3 or 'GT3' - greater than 3)  
| 6 | Pstatus  | parent's cohabitation status (binary: 'T' - living together or 'A' - apart)  
| 7 | Medu | mother's education (numeric: 0 - none, 1 - primary education (4th grade), 2 - 5th to 9th grade, 3 - secondary education or 4 - higher education)  
| 8 | Fedu | father's education (numeric: 0 - none, 1 - primary education (4th grade), 2 - 5th to 9th grade, 3 - secondary education or 4 - higher education)  
| 9 | Mjob | mother's job (nominal: 'teacher', 'health' care related, civil 'services' (e.g. administrative or police), 'at_home' or 'other')  
| 10 | Fjob | father's job (nominal: 'teacher', 'health' care related, civil 'services' (e.g. administrative or police), 'at_home' or 'other')  
| 11 | reason | reason to choose this school (nominal: close to 'home', school 'reputation', 'course' preference or 'other')  
| 12 | guardian | student's guardian (nominal: 'mother', 'father' or 'other')  
| 13 | traveltime | home to school travel time (numeric: 1 - <15 min., 2 - 15 to 30 min., 3 - 30 min. to 1 hour, or 4 - >1 hour)  
| 14 | studytime | weekly study time (numeric: 1 - <2 hours, 2 - 2 to 5 hours, 3 - 5 to 10 hours, or 4 - >10 hours)  
| 15 | failures | number of past class failures (numeric: n if 1<=n<3, else 4)  
| 16 | schoolsup | extra educational support (binary: yes or no)  
| 17 | famsup | family educational support (binary: yes or no)  
| 18 | paid | extra paid classes within the course subject (Math or Portuguese) (binary: yes or no)  
| 19 | activities | extra-curricular activities (binary: yes or no)  
| 20 | nursery | attended nursery school (binary: yes or no)  
| 21 | higher | wants to take higher education (binary: yes or no)  
| 22 | internet | Internet access at home (binary: yes or no)  
| 23 | romantic | with a romantic relationship (binary: yes or no)  
| 24 | famrel | quality of family relationships (numeric: from 1 - very bad to 5 - excellent)  
| 25 | freetime | free time after school (numeric: from 1 - very low to 5 - very high)  
| 26 | goout | going out with friends (numeric: from 1 - very low to 5 - very high)  
| 27 | Dalc | workday alcohol consumption (numeric: from 1 - very low to 5 - very high)  
| 28 | Walc | weekend alcohol consumption (numeric: from 1 - very low to 5 - very high)  
| 29 | health | current health status (numeric: from 1 - very bad to 5 - very good)  
| 30 | absences | number of school absences (numeric: from 0 to 93)  
| 31 | G1 | first period grade (numeric: from 0 to 20)  
| 31 | G2 | second period grade (numeric: from 0 to 20)  
| 32 | G3 | final grade (numeric: from 0 to 20, output target)


* **Fragment of the source data table**

![Source data table](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/source_data.png)

1. First, we will establish whether it is true that the more time a student devotes to studying (studytime), the more successful their results are (target feature G3) and build an infographic.

To do this, we create a **pivot table**, where the rows are the time for studying (studytime). They have the value “Average Grade”. Using the resulting table, we build a graph (line chart) and a column chart. Where the *x-axis* is the time spent studying, and the *y-axis* is the average grade.

![G3 vs Studytime](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/G3vs.studytime.png)

![G3 vs Studytime](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/G3vs.studytime(column).png)

*Conclusion*

As expected, people who spend the least amount of time studying (less than 2 hours) score lower than the rest (10.05).

Approximately the same success and people with 2-5 hours of study. Their average score is only 0.12 higher than the previous ones (10.17).

The highest average score is obtained by devoting 5-10 hours to study (11.4). And for those who spent more than 10 hours, the average score was lower than the previous ones by 0.14 (11.26).

So, the best results are obtained by people who spend 5 to 10 hours studying.

2. Is the conclusion of the previous paragraph correct for girls?

We create a similar **pivot table** by adding the **filter** *'F'* - we consider only girls.

Among girls, those who study 2-5 hours (9.5) get the lowest average score.

Those who spend less than 2 hours get 0.15 more (9.85).
Now those who study 5-10 hours do not get the highest score, although they are 1.23 higher than the previous ones (10.73).

The best marks are given by the girls who spend the most time - more than 10 hours (11.00).

![G3 vs Studytime (female version)](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/G3vs.studytime(female).png)

![G3 vs Studytime (female version)](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/G3vs.studytime(female_column).png)

So, the conclusion of the previous paragraph for girls is not correct. Here, the greatest amount of study time corresponds to the highest score. And the worst score is obtained by studying 2-5 hours a week.

3. Next, we will find out how the average score of students living in the city and in the suburbs differs (address attribute) and build an infographic.

We create a pivot table where the rows are the `address` (city U and suburb R). They have the “Average Grade” value.

With the help of the resulting table, we create a column chart, where one column shows the average score of urban dwellers, and the other - people from the suburbs.

![G3 vs address](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/G3vs.address.png)

![G3 vs address](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/G3vs.sex%26address.png)

*Conclusion*

The average score of urban dwellers (10.67) is higher than that of people from the suburbs (9.51) by 1.16.

4. Does the number of absences correlate with grade? Plot a scatterplot, calculate the correlation coefficient. Try to approximate this dependence with different trend lines, compare the R<sup>2</sup> coefficient.

Using the `CORREL(absences, G3)` function, we find the correlation coefficient.

Based on the `absences` and `G3` columns, we build a scatter plot and a line chart showing the relationship between the average number of absences and the grade.

![Grade vs Absences](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/Gradevs.Absences.png)

![Grade vs Absences](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/Gradevs.Absences(line).png)

*Conclusion*

Applying the `CORREL()` function gives R = 0.034, which indicates a very weak correlation and (in most cases) we do not take it into account.

5. Is it true that students who plan to get higher education (higher sign) study better at school?

We build a column chart, showing the average score of those who want to enter the university and the rest.

We also create a pivot table, where the rows are the grade, and the columns are whether the person plans to get higher education. The value of the cells is the corresponding number of people.

Using the resulting table, we build a column chart showing the number of people who want and do not want to enter the university.

![Higher education vs Grades](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/Gradesvs.HigherEducation(bar_chart).png)

![Higher education vs Grades](https://github.com/arina-korkhova/excel-projects/blob/main/images%20for%20readme/Gradesvs.HigherEducation.png)

*Conclusion*

Indeed, students who plan to pursue higher education do better in school. Moreover, the difference in estimates is noticeable - 3.8 points.

## Results
Students who study longer get better grades. Moreover, girls, on average, study worse than boys. City dwellers score one point higher than those from the suburbs. Those who plan to pursue higher education score significantly higher than those who do not intend to continue their education at a university.

