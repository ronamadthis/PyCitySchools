

```python
import pandas as pd
import os
```


```python
#Provide path using r for raw. Otherwise \U is interpreted differently.
schools=r"C:\Users\sitra\Desktop\RUTSOM201710DATA5-Class-Repository-DATA\HW4\PyCitySchools\raw_data\schools_complete.csv"
```


```python
#Read CSV file
schools_pd =pd.read_csv(schools,encoding="utf-8", low_memory=False)
```


```python
students = r"C:\Users\sitra\Desktop\RUTSOM201710DATA5-Class-Repository-DATA\HW4\PyCitySchools\raw_data\students_complete.csv"
```


```python
# Read second csv file
students_pd =pd.read_csv(students,encoding="utf-8", low_memory=False)
```


```python
#View schools file
schools_pd.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>name</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Rename "name column to "school" column
schools_pd=schools_pd.rename(columns={"name":"school"})
schools_pd.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>school</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Print total budget of all the schools
Total_budget = schools_pd["budget"].sum()
print(Total_budget)

```

    24649428
    


```python
# View students file
students_pd.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>school</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Merge school and students files around "school" column
schools_students_pd=schools_pd.merge(students_pd,on='school')
schools_students_pd.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>school</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Print total student count
schools_students_pd.count()
```




    School ID        39170
    school           39170
    type             39170
    size             39170
    budget           39170
    Student ID       39170
    name             39170
    gender           39170
    grade            39170
    reading_score    39170
    math_score       39170
    dtype: int64




```python
# Print total number of schools count
Total_schools=schools_pd["school"].count()
print(Total_schools)
```

    15
    


```python
# Print the total number of students in all the schools
Total_students=len(schools_students_pd["name"])
print(Total_students)
```

    39170
    


```python
# Print average math score of all the students
Avg_math_score=round(schools_students_pd['math_score'].mean(),2)
print(Avg_math_score)
```

    78.99
    


```python
# Print average reading score of all the students
Avg_reading_score=round(schools_students_pd['reading_score'].mean(),2)
print(Avg_reading_score)
```

    81.88
    


```python
# Number of students with passing score(.=65) in math
total_passing_math=(schools_students_pd["math_score"] >=65).sum()
print(total_passing_math)
```

    33188
    


```python
# Number of students with passing score(.=65) in reading
total_passing_reading=(schools_students_pd["reading_score"] >=65).sum()
print(total_passing_reading)
```

    37681
    


```python
# percent students with passing scores in reading and math 
Percent_passing_math=round(total_passing_math/Total_students*100,2)
Percent_passing_reading=round(total_passing_reading/Total_students*100,2)
Overall_rate=round((Percent_passing_math+Percent_passing_reading)/2,2)
```


```python
# Create a table with all the above data
summary_district_table=pd.DataFrame({"Total Schools":[Total_schools],"Total Students":[Total_students],"Total Budget":[Total_budget],"Average Math Score":[Avg_math_score],"Average Reading Score":[Avg_reading_score],"% Passing Math":[Percent_passing_math],"% Passing Reading":[Percent_passing_reading],"Overall Passing Rate":[Overall_rate]})
#summary_district_table.reset_index(inplace=False)

# Re-order the columns
summary_district_table=summary_district_table[["Total Schools","Total Students","Total Budget","Average Reading Score","Average Math Score","% Passing Math","% Passing Reading","Overall Passing Rate"]]
summary_district_table.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Total Schools</th>
      <th>Total Students</th>
      <th>Total Budget</th>
      <th>Average Reading Score</th>
      <th>Average Math Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>15</td>
      <td>39170</td>
      <td>24649428</td>
      <td>81.88</td>
      <td>78.99</td>
      <td>84.73</td>
      <td>96.2</td>
      <td>90.46</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Calculate the average reading and math scores per school using groupby function
grouped_school_pd=round(schools_students_pd.groupby("school").mean(),2)
#grouped_school_pd.reset_index(inplace=True)
grouped_school_pd.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
    <tr>
      <th>school</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>7.0</td>
      <td>4976.0</td>
      <td>3124928.0</td>
      <td>20358.5</td>
      <td>81.03</td>
      <td>77.05</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>6.0</td>
      <td>1858.0</td>
      <td>1081356.0</td>
      <td>16941.5</td>
      <td>83.98</td>
      <td>83.06</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>1.0</td>
      <td>2949.0</td>
      <td>1884411.0</td>
      <td>4391.0</td>
      <td>81.16</td>
      <td>76.71</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>13.0</td>
      <td>2739.0</td>
      <td>1763916.0</td>
      <td>36165.0</td>
      <td>80.75</td>
      <td>77.10</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>4.0</td>
      <td>1468.0</td>
      <td>917500.0</td>
      <td>12995.5</td>
      <td>83.82</td>
      <td>83.35</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Add a new column with "Per School Budget" to the grouped school table
grouped_school_pd['Per School Budget']=round(grouped_school_pd['budget']/grouped_school_pd['size'],0)
grouped_school_pd.head()


#schools_pd['Avg reading score']= pd.Series(grouped_school_pd["reading_score"])
#schools_pd['Avg math score']= pd.Series(grouped_school_pd["math_score"])
#schools_pd.reset_index(inplace=False)
#schools_pd.head(15)
grouped_school1_pd=grouped_school_pd.rename(columns={"reading_score":"Avg Reading Score","math_score":"Avg Math Score"})
grouped_school1_pd.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>size</th>
      <th>budget</th>
      <th>Student ID</th>
      <th>Avg Reading Score</th>
      <th>Avg Math Score</th>
      <th>Per School Budget</th>
    </tr>
    <tr>
      <th>school</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>7.0</td>
      <td>4976.0</td>
      <td>3124928.0</td>
      <td>20358.5</td>
      <td>81.03</td>
      <td>77.05</td>
      <td>628.0</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>6.0</td>
      <td>1858.0</td>
      <td>1081356.0</td>
      <td>16941.5</td>
      <td>83.98</td>
      <td>83.06</td>
      <td>582.0</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>1.0</td>
      <td>2949.0</td>
      <td>1884411.0</td>
      <td>4391.0</td>
      <td>81.16</td>
      <td>76.71</td>
      <td>639.0</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>13.0</td>
      <td>2739.0</td>
      <td>1763916.0</td>
      <td>36165.0</td>
      <td>80.75</td>
      <td>77.10</td>
      <td>644.0</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>4.0</td>
      <td>1468.0</td>
      <td>917500.0</td>
      <td>12995.5</td>
      <td>83.82</td>
      <td>83.35</td>
      <td>625.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Create a table(double brackets on reading math scores) of the number of students with passing reading and math scores by school
Students_passing_reading=students_pd[students_pd['reading_score']>=65].groupby("school")[['reading_score']].count()

Students_passing_math=students_pd[students_pd['math_score']>=65].groupby("school")[['math_score']].count()
#School_lst=schools_pd['school']
total_students=schools_pd.groupby('school')['size']
print(Students_passing_reading.head(),Students_passing_math.head() )
#students_pd.head()
```

                          reading_score
    school                             
    Bailey High School             4705
    Cabrera High School            1858
    Figueroa High School           2788
    Ford High School               2571
    Griffin High School            1468                       math_score
    school                          
    Bailey High School          3877
    Cabrera High School         1858
    Figueroa High School        2276
    Ford High School            2142
    Griffin High School         1468
    


```python
group_school=schools_pd.set_index("school")

group_school.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School ID</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
    <tr>
      <th>school</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Huang High School</th>
      <td>0</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>1</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>2</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>3</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>4</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Calculate % passing reading and math by school and pass it on to existing table

Percent_pass_reading=round(Students_passing_reading["reading_score"]/grouped_school1_pd["size"]*100,2)
Percent_pass_math=round(Students_passing_math["math_score"]/grouped_school1_pd["size"]*100,2)
Overall_pass_rate=round((Percent_pass_reading+Percent_pass_math)/2,2)
Percent_pass_reading.head()
grouped_school1_pd["% Passing Reading"]=Percent_pass_reading
grouped_school1_pd["% Passing Math"]=Percent_pass_math
grouped_school1_pd["Overall Pass Rate"]=Overall_pass_rate
grouped_school1_pd["School Type"]=group_school["type"]

grouped_school1_pd.reset_index(inplace=True)
#grouped_school1_pd.head()
renamed_table=grouped_school1_pd.rename(columns={"school":"School Name","size":"Total Students","budget":"Total School Budget"})
renamed_table=renamed_table[["School Name","School Type","Total Students","Total School Budget","Per School Budget","Avg Math Score","Avg Reading Score","% Passing Math","% Passing Reading","Overall Pass Rate","School ID", "Student ID"]]
renamed_table.drop(renamed_table.columns[[10,11]], axis=1, inplace=True)
renamed_table.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School Name</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total School Budget</th>
      <th>Per School Budget</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Pass Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>District</td>
      <td>4976.0</td>
      <td>3124928.0</td>
      <td>628.0</td>
      <td>77.05</td>
      <td>81.03</td>
      <td>77.91</td>
      <td>94.55</td>
      <td>86.23</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858.0</td>
      <td>1081356.0</td>
      <td>582.0</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949.0</td>
      <td>1884411.0</td>
      <td>639.0</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>77.18</td>
      <td>94.54</td>
      <td>85.86</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739.0</td>
      <td>1763916.0</td>
      <td>644.0</td>
      <td>77.10</td>
      <td>80.75</td>
      <td>78.20</td>
      <td>93.87</td>
      <td>86.04</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468.0</td>
      <td>917500.0</td>
      <td>625.0</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Top five schools with highest overall passing rate
Descending_df = renamed_table.sort_values("Overall Pass Rate", ascending=False)
Descending_df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School Name</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total School Budget</th>
      <th>Per School Budget</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Pass Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858.0</td>
      <td>1081356.0</td>
      <td>582.0</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>100.0</td>
      <td>100.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468.0</td>
      <td>917500.0</td>
      <td>625.0</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>100.0</td>
      <td>100.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Holden High School</td>
      <td>Charter</td>
      <td>427.0</td>
      <td>248087.0</td>
      <td>581.0</td>
      <td>83.80</td>
      <td>83.81</td>
      <td>100.0</td>
      <td>100.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962.0</td>
      <td>585858.0</td>
      <td>609.0</td>
      <td>83.84</td>
      <td>84.04</td>
      <td>100.0</td>
      <td>100.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761.0</td>
      <td>1056600.0</td>
      <td>600.0</td>
      <td>83.36</td>
      <td>83.73</td>
      <td>100.0</td>
      <td>100.0</td>
      <td>100.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Bottom five schools with lowest overall passing rate
Ascending_df = renamed_table.sort_values("Overall Pass Rate", ascending=True)
Ascending_df.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School Name</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total School Budget</th>
      <th>Per School Budget</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Pass Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949.0</td>
      <td>1884411.0</td>
      <td>639.0</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>77.18</td>
      <td>94.54</td>
      <td>85.86</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739.0</td>
      <td>1763916.0</td>
      <td>644.0</td>
      <td>77.10</td>
      <td>80.75</td>
      <td>78.20</td>
      <td>93.87</td>
      <td>86.04</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917.0</td>
      <td>1910635.0</td>
      <td>655.0</td>
      <td>76.63</td>
      <td>81.18</td>
      <td>77.72</td>
      <td>94.48</td>
      <td>86.10</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635.0</td>
      <td>3022020.0</td>
      <td>652.0</td>
      <td>77.29</td>
      <td>80.93</td>
      <td>77.73</td>
      <td>94.61</td>
      <td>86.17</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761.0</td>
      <td>3094650.0</td>
      <td>650.0</td>
      <td>77.07</td>
      <td>80.97</td>
      <td>77.97</td>
      <td>94.48</td>
      <td>86.22</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Deteremine min and max budget per student per school to determine bin ranges
max_spending=Ascending_df["Per School Budget"].max()
print(max_spending)
min_spending=Ascending_df["Per School Budget"].min()
print(min_spending)
```

    655.0
    578.0
    


```python
# Determine min and max students in schools to determine bin ranges
max_students=Ascending_df["Total Students"].max()
print(max_students)
min_students=Ascending_df["Total Students"].min()
print(min_students)
```

    4976.0
    427.0
    


```python
# Determine math and reading scores for each grade level at each school
students_pd['Student ID']=students_pd['Student ID'].astype(str)
students_pd['math_score']=students_pd['math_score'].astype(str)
newstudents_pd=students_pd.groupby(["school","grade"])
new_table1_pd=round(newstudents_pd.mean(),2).unstack("grade").sort_index(axis=1)
new_table1_pd.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="4" halign="left">reading_score</th>
    </tr>
    <tr>
      <th>grade</th>
      <th>10th</th>
      <th>11th</th>
      <th>12th</th>
      <th>9th</th>
    </tr>
    <tr>
      <th>school</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>80.91</td>
      <td>80.95</td>
      <td>80.91</td>
      <td>81.30</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>84.25</td>
      <td>83.79</td>
      <td>84.29</td>
      <td>83.68</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>81.41</td>
      <td>80.64</td>
      <td>81.38</td>
      <td>81.20</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>81.26</td>
      <td>80.40</td>
      <td>80.66</td>
      <td>80.63</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>83.71</td>
      <td>84.29</td>
      <td>84.01</td>
      <td>83.37</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Determine math and reading scores for each grade level at each school
students_pd['Student ID']=students_pd['Student ID'].astype(str)
students_pd['math_score']=students_pd['math_score'].astype(float)
students_pd['reading_score']=students_pd['reading_score'].astype(str)
newstudents_pd=students_pd.groupby(["school","grade"])
round(newstudents_pd.mean(),2).unstack()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="4" halign="left">math_score</th>
    </tr>
    <tr>
      <th>grade</th>
      <th>10th</th>
      <th>11th</th>
      <th>12th</th>
      <th>9th</th>
    </tr>
    <tr>
      <th>school</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>77.00</td>
      <td>77.52</td>
      <td>76.49</td>
      <td>77.08</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>83.15</td>
      <td>82.77</td>
      <td>83.28</td>
      <td>83.09</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>76.54</td>
      <td>76.88</td>
      <td>77.15</td>
      <td>76.40</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>77.67</td>
      <td>76.92</td>
      <td>76.18</td>
      <td>77.36</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>84.23</td>
      <td>83.84</td>
      <td>83.36</td>
      <td>82.04</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>77.34</td>
      <td>77.14</td>
      <td>77.19</td>
      <td>77.44</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>83.43</td>
      <td>85.00</td>
      <td>82.86</td>
      <td>83.79</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>75.91</td>
      <td>76.45</td>
      <td>77.23</td>
      <td>77.03</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>76.69</td>
      <td>77.49</td>
      <td>76.86</td>
      <td>77.19</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>83.37</td>
      <td>84.33</td>
      <td>84.12</td>
      <td>83.63</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>76.61</td>
      <td>76.40</td>
      <td>77.69</td>
      <td>76.86</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>82.92</td>
      <td>83.38</td>
      <td>83.78</td>
      <td>83.42</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>83.09</td>
      <td>83.50</td>
      <td>83.50</td>
      <td>83.59</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>83.72</td>
      <td>83.20</td>
      <td>83.04</td>
      <td>83.09</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>84.01</td>
      <td>83.84</td>
      <td>83.64</td>
      <td>83.26</td>
    </tr>
  </tbody>
</table>
</div>




```python
renamed_table1=renamed_table.copy()

# Create the bins in which Data will be held
# Bins are 575 to 595, 595 to 615,615 to 635, 635 to 655
bins = [575,595,615,635,655]

# Create the names for the four bins
group_names = ['Low', 'Medium', 'Large','V.Large']

# Table with Total Students bins
renamed_table1["Spending Ranges"] = pd.cut(renamed_table1["Per School Budget"], bins, labels=group_names)
renamed_table1.drop(renamed_table1.columns[[1,2,3,4]], axis=1, inplace=True)

renamed_table1
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School Name</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Pass Rate</th>
      <th>Spending Ranges</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>77.05</td>
      <td>81.03</td>
      <td>77.91</td>
      <td>94.55</td>
      <td>86.23</td>
      <td>Large</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cabrera High School</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Figueroa High School</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>77.18</td>
      <td>94.54</td>
      <td>85.86</td>
      <td>V.Large</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford High School</td>
      <td>77.10</td>
      <td>80.75</td>
      <td>78.20</td>
      <td>93.87</td>
      <td>86.04</td>
      <td>V.Large</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Large</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Hernandez High School</td>
      <td>77.29</td>
      <td>80.93</td>
      <td>77.73</td>
      <td>94.61</td>
      <td>86.17</td>
      <td>V.Large</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Holden High School</td>
      <td>83.80</td>
      <td>83.81</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Huang High School</td>
      <td>76.63</td>
      <td>81.18</td>
      <td>77.72</td>
      <td>94.48</td>
      <td>86.10</td>
      <td>V.Large</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Johnson High School</td>
      <td>77.07</td>
      <td>80.97</td>
      <td>77.97</td>
      <td>94.48</td>
      <td>86.22</td>
      <td>V.Large</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Pena High School</td>
      <td>83.84</td>
      <td>84.04</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Rodriguez High School</td>
      <td>76.84</td>
      <td>80.74</td>
      <td>77.94</td>
      <td>94.62</td>
      <td>86.28</td>
      <td>V.Large</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Shelton High School</td>
      <td>83.36</td>
      <td>83.73</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Thomas High School</td>
      <td>83.42</td>
      <td>83.85</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>V.Large</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Wilson High School</td>
      <td>83.27</td>
      <td>83.99</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Wright High School</td>
      <td>83.68</td>
      <td>83.96</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Low</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Creating a group based off of the bins
renamed_table1 = renamed_table1.groupby("Spending Ranges")
#renamed_table.head()
round(renamed_table1.mean(),2)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Pass Rate</th>
    </tr>
    <tr>
      <th>Spending Ranges</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Low</th>
      <td>83.45</td>
      <td>83.94</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
    </tr>
    <tr>
      <th>Medium</th>
      <td>83.60</td>
      <td>83.88</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
    </tr>
    <tr>
      <th>Large</th>
      <td>80.20</td>
      <td>82.42</td>
      <td>88.96</td>
      <td>97.28</td>
      <td>93.12</td>
    </tr>
    <tr>
      <th>V.Large</th>
      <td>77.87</td>
      <td>81.37</td>
      <td>80.96</td>
      <td>95.23</td>
      <td>88.10</td>
    </tr>
  </tbody>
</table>
</div>




```python
renamed_table3 =renamed_table.copy()

## Create the bins in which Data will be held
## Bins are 400 to 2000, 2000 to 3500, 3500 to 5000
bins = [400, 2000, 3500, 5000]

## Create the names for the four bins
group_names = ['Small', 'Medium', 'Large']

## Table with Total Students bins
renamed_table3["School Size"] = pd.cut(renamed_table3["Total Students"], bins, labels=group_names)
renamed_table3.drop(renamed_table3.columns[[1,2,3,4]], axis=1, inplace=True)
renamed_table3
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>School Name</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Pass Rate</th>
      <th>School Size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bailey High School</td>
      <td>77.05</td>
      <td>81.03</td>
      <td>77.91</td>
      <td>94.55</td>
      <td>86.23</td>
      <td>Large</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cabrera High School</td>
      <td>83.06</td>
      <td>83.98</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Small</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Figueroa High School</td>
      <td>76.71</td>
      <td>81.16</td>
      <td>77.18</td>
      <td>94.54</td>
      <td>85.86</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford High School</td>
      <td>77.10</td>
      <td>80.75</td>
      <td>78.20</td>
      <td>93.87</td>
      <td>86.04</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Griffin High School</td>
      <td>83.35</td>
      <td>83.82</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Small</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Hernandez High School</td>
      <td>77.29</td>
      <td>80.93</td>
      <td>77.73</td>
      <td>94.61</td>
      <td>86.17</td>
      <td>Large</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Holden High School</td>
      <td>83.80</td>
      <td>83.81</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Small</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Huang High School</td>
      <td>76.63</td>
      <td>81.18</td>
      <td>77.72</td>
      <td>94.48</td>
      <td>86.10</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Johnson High School</td>
      <td>77.07</td>
      <td>80.97</td>
      <td>77.97</td>
      <td>94.48</td>
      <td>86.22</td>
      <td>Large</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Pena High School</td>
      <td>83.84</td>
      <td>84.04</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Small</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Rodriguez High School</td>
      <td>76.84</td>
      <td>80.74</td>
      <td>77.94</td>
      <td>94.62</td>
      <td>86.28</td>
      <td>Large</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Shelton High School</td>
      <td>83.36</td>
      <td>83.73</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Small</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Thomas High School</td>
      <td>83.42</td>
      <td>83.85</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Small</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Wilson High School</td>
      <td>83.27</td>
      <td>83.99</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Wright High School</td>
      <td>83.68</td>
      <td>83.96</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>Small</td>
    </tr>
  </tbody>
</table>
</div>




```python
                                       
#Creating a group based off of the bins
renamed4_table = renamed_table3.groupby("School Size")
round(renamed4_table.mean(),2)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Pass Rate</th>
    </tr>
    <tr>
      <th>School Size</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Small</th>
      <td>83.50</td>
      <td>83.88</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
    </tr>
    <tr>
      <th>Medium</th>
      <td>78.43</td>
      <td>81.77</td>
      <td>83.28</td>
      <td>95.72</td>
      <td>89.50</td>
    </tr>
    <tr>
      <th>Large</th>
      <td>77.06</td>
      <td>80.92</td>
      <td>77.89</td>
      <td>94.56</td>
      <td>86.22</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Creating a group based off of School Type
renamed_table5=renamed_table.copy()
renamed_table5.drop(renamed_table5.columns[[2,3,4]], axis=1, inplace=True)

renamed_table5 = renamed_table5.groupby("School Type")

round(renamed_table5.mean(),2)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Pass Rate</th>
    </tr>
    <tr>
      <th>School Type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Charter</th>
      <td>83.47</td>
      <td>83.90</td>
      <td>100.00</td>
      <td>100.00</td>
      <td>100.00</td>
    </tr>
    <tr>
      <th>District</th>
      <td>76.96</td>
      <td>80.97</td>
      <td>77.81</td>
      <td>94.45</td>
      <td>86.13</td>
    </tr>
  </tbody>
</table>
</div>


