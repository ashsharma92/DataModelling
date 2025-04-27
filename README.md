# DataModelling
Taking data from different sources and using PowerQuery to clean and prepare a data model

This was a short project to get the ball rolling, web link to datasets are here: https://www.deeplearningnerds.com/sample-data-university-dataset/

4 files were uploaded onto PBI:
- Attendance.csv
- Student.xlsx
- Tutor.xml
- Course.json
- Course_Name.csv

This project will walk through the data cleaning process as well as the data model I finalised to visualise certain outcomes.

Limitations of the dataset:
- very limited data
- some unexplained nulls in the data with no real context from the source
- data is synthetic in nature so not much in the way of a thorough analysis could be done

Context for the data - the data shows attendance figures for several student IDs, as well as student information, tutor information and course codes and names. In terms of an analysis a more extensive dataset could have been a good oppurtunity to analyse attendance figures over different courses and spot students with issues. As mentioned with regards to limitations I could only visualise certain things.

I uploaded all files onto PBI and started by examining each one for quality and consistency.

Course name data- promoted first row to headers, and got rid of duplicates

Before:
<img width="448" alt="image" src="https://github.com/user-attachments/assets/b29fa8da-0838-49e6-841b-69403735f31b" />

After:
<img width="301" alt="image" src="https://github.com/user-attachments/assets/fc4fbd4b-9db5-4966-844e-d75094053f40" />


Student data- several issues here, namely 2 columns with no use that I removed, I then split properties column on comma delimeter and this broke up the information to allow me to focus on the key facts- making columns on gender, dob, enrolment semester and current semester and other items of interest. Renamed the query as Students instead of Tabelle.

Before: 
<img width="800" alt="image" src="https://github.com/user-attachments/assets/dc568edf-c287-4a48-b307-a7326dba4ac3" />

After:
<img width="815" alt="image" src="https://github.com/user-attachments/assets/7d257256-efa4-4cba-81bc-a2c0fa3c37c5" />

Course_Info- cleaned up column headings and relabelled query as Course_Info. Slight issue with some nulls in course level and due to lack of context knowledge I couldn't assume or make judgements on this so I deleted the column to avoid any issues with analysis.

Before:
<img width="818" alt="image" src="https://github.com/user-attachments/assets/9eab9ec5-89bd-4171-af0a-2611d9c29b8f" />

After:
<img width="646" alt="image" src="https://github.com/user-attachments/assets/7d873278-4ffb-464b-ad32-a1d39c092a3e" />

Attendance data- as a table of data this was not expected and fairly low level. I was expecting more in the way of descriptive statistics. To just tidy things up I made first row as headers and then capitilized primary and foreign key data as I wanted consistency across the tables. Another issue I had was with blank cells of data which without context did not make much sense, empty student_ids but associated data entered on course_id, tutor_id, grade. I made a decision to remove the empty values to try and ensure completeness of the dataset where possible. The last column on semester was also confusing and it felt like there were only ever 2 semesters in every year (summer and winter) so did not feel realistic. 

Before: 
<img width="761" alt="image" src="https://github.com/user-attachments/assets/356c0670-d515-4574-ab75-7a06d3746c2c" />

After: 
<img width="763" alt="image" src="https://github.com/user-attachments/assets/5fc10329-0d23-4f21-9dac-1fd385173438" />

Data Model before: As you can see before I went through the cleaning steps no such relations existed between the tables due to lack of consistency with labelling of primary and foreign keys. 

<img width="809" alt="image" src="https://github.com/user-attachments/assets/d398c3a6-e276-45d5-b2be-ec8388ce4666" />

After: PBI was able to pick up on more relations between tables but I made 1-many relationship with students and attendance as well as course info and attendance.

<img width="497" alt="image" src="https://github.com/user-attachments/assets/0465ce4d-a6a4-418e-bbed-095515a864a2" />

A positive consequence of this data model was the ability to make some basic visualisations due to relationships being recognised across tables. For example below:

<img width="500" alt="image" src="https://github.com/user-attachments/assets/da5a33ff-b0ad-4192-bfdf-56fade4737d7" />

I was able to create an overall results page to show results of students and use slicers to filter on student name or tutor name or department. This can give insights on student performance but also can be used to look at tutor's results or departmental results. 

Rough Insights gained:




