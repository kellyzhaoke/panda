

```python
import pandas as pd

```


```python
school="raw_data/schools_complete.csv"
school_df=pd.read_csv(school,encoding='iso-8859-1', low_memory=False)
school_df
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
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858</td>
      <td>1081356</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>Bailey High School</td>
      <td>District</td>
      <td>4976</td>
      <td>3124928</td>
    </tr>
    <tr>
      <th>8</th>
      <td>8</td>
      <td>Holden High School</td>
      <td>Charter</td>
      <td>427</td>
      <td>248087</td>
    </tr>
    <tr>
      <th>9</th>
      <td>9</td>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
    </tr>
    <tr>
      <th>10</th>
      <td>10</td>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
    </tr>
    <tr>
      <th>11</th>
      <td>11</td>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
    </tr>
    <tr>
      <th>12</th>
      <td>12</td>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
    </tr>
    <tr>
      <th>13</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
    </tr>
    <tr>
      <th>14</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
    </tr>
  </tbody>
</table>
</div>




```python
school_df = school_df.rename(columns={"name":"school",
                                       "type":"School Type",
                                       "size":"School Size",
                                       "budget":"Budget"})
school_df.columns
```




    Index(['School ID', 'school', 'School Type', 'School Size', 'Budget'], dtype='object')




```python
students="raw_data/students_complete.csv"
students_df=pd.read_csv(students,encoding='iso-8859-1', low_memory=False)
students_df
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
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Bryan Miranda</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>94</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>Sheena Carter</td>
      <td>F</td>
      <td>11th</td>
      <td>Huang High School</td>
      <td>82</td>
      <td>80</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>Nicole Baker</td>
      <td>F</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>96</td>
      <td>69</td>
    </tr>
    <tr>
      <th>8</th>
      <td>8</td>
      <td>Michael Roth</td>
      <td>M</td>
      <td>10th</td>
      <td>Huang High School</td>
      <td>95</td>
      <td>87</td>
    </tr>
    <tr>
      <th>9</th>
      <td>9</td>
      <td>Matthew Greene</td>
      <td>M</td>
      <td>10th</td>
      <td>Huang High School</td>
      <td>96</td>
      <td>84</td>
    </tr>
    <tr>
      <th>10</th>
      <td>10</td>
      <td>Andrew Alexander</td>
      <td>M</td>
      <td>10th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>70</td>
    </tr>
    <tr>
      <th>11</th>
      <td>11</td>
      <td>Daniel Cooper</td>
      <td>M</td>
      <td>10th</td>
      <td>Huang High School</td>
      <td>78</td>
      <td>77</td>
    </tr>
    <tr>
      <th>12</th>
      <td>12</td>
      <td>Brittney Walker</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>64</td>
      <td>79</td>
    </tr>
    <tr>
      <th>13</th>
      <td>13</td>
      <td>William Long</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>71</td>
      <td>79</td>
    </tr>
    <tr>
      <th>14</th>
      <td>14</td>
      <td>Tammy Hebert</td>
      <td>F</td>
      <td>10th</td>
      <td>Huang High School</td>
      <td>85</td>
      <td>67</td>
    </tr>
    <tr>
      <th>15</th>
      <td>15</td>
      <td>Dr. Jordan Carson</td>
      <td>M</td>
      <td>11th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>88</td>
    </tr>
    <tr>
      <th>16</th>
      <td>16</td>
      <td>Donald Zamora</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>88</td>
      <td>55</td>
    </tr>
    <tr>
      <th>17</th>
      <td>17</td>
      <td>Kimberly Santiago</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>74</td>
      <td>75</td>
    </tr>
    <tr>
      <th>18</th>
      <td>18</td>
      <td>Kevin Stevens</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>64</td>
      <td>69</td>
    </tr>
    <tr>
      <th>19</th>
      <td>19</td>
      <td>Brandi Lyons</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>89</td>
      <td>80</td>
    </tr>
    <tr>
      <th>20</th>
      <td>20</td>
      <td>Lisa Davis</td>
      <td>F</td>
      <td>10th</td>
      <td>Huang High School</td>
      <td>91</td>
      <td>89</td>
    </tr>
    <tr>
      <th>21</th>
      <td>21</td>
      <td>Kristen Lopez</td>
      <td>F</td>
      <td>10th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>77</td>
    </tr>
    <tr>
      <th>22</th>
      <td>22</td>
      <td>Kimberly Stewart</td>
      <td>F</td>
      <td>11th</td>
      <td>Huang High School</td>
      <td>99</td>
      <td>84</td>
    </tr>
    <tr>
      <th>23</th>
      <td>23</td>
      <td>Christopher Parker</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>81</td>
      <td>68</td>
    </tr>
    <tr>
      <th>24</th>
      <td>24</td>
      <td>Chelsea Griffith</td>
      <td>F</td>
      <td>11th</td>
      <td>Huang High School</td>
      <td>85</td>
      <td>73</td>
    </tr>
    <tr>
      <th>25</th>
      <td>25</td>
      <td>Cesar Morris</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>92</td>
      <td>70</td>
    </tr>
    <tr>
      <th>26</th>
      <td>26</td>
      <td>Melanie Decker</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>63</td>
      <td>85</td>
    </tr>
    <tr>
      <th>27</th>
      <td>27</td>
      <td>Tracey Oconnor</td>
      <td>F</td>
      <td>10th</td>
      <td>Huang High School</td>
      <td>80</td>
      <td>58</td>
    </tr>
    <tr>
      <th>28</th>
      <td>28</td>
      <td>Kelly James</td>
      <td>F</td>
      <td>11th</td>
      <td>Huang High School</td>
      <td>73</td>
      <td>55</td>
    </tr>
    <tr>
      <th>29</th>
      <td>29</td>
      <td>Nicole Brown</td>
      <td>F</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>88</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>39140</th>
      <td>39140</td>
      <td>Cheyenne Hernandez</td>
      <td>F</td>
      <td>9th</td>
      <td>Thomas High School</td>
      <td>76</td>
      <td>99</td>
    </tr>
    <tr>
      <th>39141</th>
      <td>39141</td>
      <td>Jonathan Sullivan</td>
      <td>M</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>86</td>
      <td>93</td>
    </tr>
    <tr>
      <th>39142</th>
      <td>39142</td>
      <td>Deborah Higgins DDS</td>
      <td>F</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>96</td>
      <td>83</td>
    </tr>
    <tr>
      <th>39143</th>
      <td>39143</td>
      <td>Steven Jackson</td>
      <td>M</td>
      <td>11th</td>
      <td>Thomas High School</td>
      <td>71</td>
      <td>93</td>
    </tr>
    <tr>
      <th>39144</th>
      <td>39144</td>
      <td>Cristian Webster</td>
      <td>M</td>
      <td>12th</td>
      <td>Thomas High School</td>
      <td>77</td>
      <td>87</td>
    </tr>
    <tr>
      <th>39145</th>
      <td>39145</td>
      <td>Audrey Fry</td>
      <td>F</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>94</td>
      <td>74</td>
    </tr>
    <tr>
      <th>39146</th>
      <td>39146</td>
      <td>Michael Carroll</td>
      <td>M</td>
      <td>9th</td>
      <td>Thomas High School</td>
      <td>69</td>
      <td>95</td>
    </tr>
    <tr>
      <th>39147</th>
      <td>39147</td>
      <td>Raymond Hawkins</td>
      <td>M</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>88</td>
      <td>81</td>
    </tr>
    <tr>
      <th>39148</th>
      <td>39148</td>
      <td>Christopher Wilson</td>
      <td>M</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>89</td>
      <td>89</td>
    </tr>
    <tr>
      <th>39149</th>
      <td>39149</td>
      <td>Glenda Fletcher</td>
      <td>F</td>
      <td>11th</td>
      <td>Thomas High School</td>
      <td>82</td>
      <td>93</td>
    </tr>
    <tr>
      <th>39150</th>
      <td>39150</td>
      <td>Jennifer Hamilton</td>
      <td>F</td>
      <td>11th</td>
      <td>Thomas High School</td>
      <td>80</td>
      <td>75</td>
    </tr>
    <tr>
      <th>39151</th>
      <td>39151</td>
      <td>Shannon Williams</td>
      <td>F</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>84</td>
      <td>73</td>
    </tr>
    <tr>
      <th>39152</th>
      <td>39152</td>
      <td>Lori Moore</td>
      <td>F</td>
      <td>9th</td>
      <td>Thomas High School</td>
      <td>98</td>
      <td>84</td>
    </tr>
    <tr>
      <th>39153</th>
      <td>39153</td>
      <td>William Hubbard</td>
      <td>M</td>
      <td>9th</td>
      <td>Thomas High School</td>
      <td>80</td>
      <td>75</td>
    </tr>
    <tr>
      <th>39154</th>
      <td>39154</td>
      <td>Bradley Johnson</td>
      <td>M</td>
      <td>12th</td>
      <td>Thomas High School</td>
      <td>91</td>
      <td>71</td>
    </tr>
    <tr>
      <th>39155</th>
      <td>39155</td>
      <td>John Brooks</td>
      <td>M</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>92</td>
      <td>98</td>
    </tr>
    <tr>
      <th>39156</th>
      <td>39156</td>
      <td>Stephanie Contreras</td>
      <td>F</td>
      <td>11th</td>
      <td>Thomas High School</td>
      <td>79</td>
      <td>95</td>
    </tr>
    <tr>
      <th>39157</th>
      <td>39157</td>
      <td>Kristen Gonzalez</td>
      <td>F</td>
      <td>9th</td>
      <td>Thomas High School</td>
      <td>79</td>
      <td>94</td>
    </tr>
    <tr>
      <th>39158</th>
      <td>39158</td>
      <td>Kari Holloway</td>
      <td>F</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>87</td>
      <td>90</td>
    </tr>
    <tr>
      <th>39159</th>
      <td>39159</td>
      <td>Kimberly Cabrera</td>
      <td>F</td>
      <td>11th</td>
      <td>Thomas High School</td>
      <td>85</td>
      <td>72</td>
    </tr>
    <tr>
      <th>39160</th>
      <td>39160</td>
      <td>Katie Weaver</td>
      <td>F</td>
      <td>11th</td>
      <td>Thomas High School</td>
      <td>89</td>
      <td>86</td>
    </tr>
    <tr>
      <th>39161</th>
      <td>39161</td>
      <td>April Reyes</td>
      <td>F</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>70</td>
      <td>84</td>
    </tr>
    <tr>
      <th>39162</th>
      <td>39162</td>
      <td>Derek Weeks</td>
      <td>M</td>
      <td>12th</td>
      <td>Thomas High School</td>
      <td>94</td>
      <td>77</td>
    </tr>
    <tr>
      <th>39163</th>
      <td>39163</td>
      <td>John Reese</td>
      <td>M</td>
      <td>11th</td>
      <td>Thomas High School</td>
      <td>90</td>
      <td>75</td>
    </tr>
    <tr>
      <th>39164</th>
      <td>39164</td>
      <td>Joseph Anthony</td>
      <td>M</td>
      <td>9th</td>
      <td>Thomas High School</td>
      <td>97</td>
      <td>76</td>
    </tr>
    <tr>
      <th>39165</th>
      <td>39165</td>
      <td>Donna Howard</td>
      <td>F</td>
      <td>12th</td>
      <td>Thomas High School</td>
      <td>99</td>
      <td>90</td>
    </tr>
    <tr>
      <th>39166</th>
      <td>39166</td>
      <td>Dawn Bell</td>
      <td>F</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>95</td>
      <td>70</td>
    </tr>
    <tr>
      <th>39167</th>
      <td>39167</td>
      <td>Rebecca Tanner</td>
      <td>F</td>
      <td>9th</td>
      <td>Thomas High School</td>
      <td>73</td>
      <td>84</td>
    </tr>
    <tr>
      <th>39168</th>
      <td>39168</td>
      <td>Desiree Kidd</td>
      <td>F</td>
      <td>10th</td>
      <td>Thomas High School</td>
      <td>99</td>
      <td>90</td>
    </tr>
    <tr>
      <th>39169</th>
      <td>39169</td>
      <td>Carolyn Jackson</td>
      <td>F</td>
      <td>11th</td>
      <td>Thomas High School</td>
      <td>95</td>
      <td>75</td>
    </tr>
  </tbody>
</table>
<p>39170 rows × 7 columns</p>
</div>




```python
merge_table=pd.merge (school_df, students_df, on="school")
merge_table
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
      <th>School Type</th>
      <th>School Size</th>
      <th>Budget</th>
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
    <tr>
      <th>5</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>5</td>
      <td>Bryan Miranda</td>
      <td>M</td>
      <td>9th</td>
      <td>94</td>
      <td>94</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>6</td>
      <td>Sheena Carter</td>
      <td>F</td>
      <td>11th</td>
      <td>82</td>
      <td>80</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>7</td>
      <td>Nicole Baker</td>
      <td>F</td>
      <td>12th</td>
      <td>96</td>
      <td>69</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>8</td>
      <td>Michael Roth</td>
      <td>M</td>
      <td>10th</td>
      <td>95</td>
      <td>87</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9</td>
      <td>Matthew Greene</td>
      <td>M</td>
      <td>10th</td>
      <td>96</td>
      <td>84</td>
    </tr>
    <tr>
      <th>10</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>10</td>
      <td>Andrew Alexander</td>
      <td>M</td>
      <td>10th</td>
      <td>90</td>
      <td>70</td>
    </tr>
    <tr>
      <th>11</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>11</td>
      <td>Daniel Cooper</td>
      <td>M</td>
      <td>10th</td>
      <td>78</td>
      <td>77</td>
    </tr>
    <tr>
      <th>12</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12</td>
      <td>Brittney Walker</td>
      <td>F</td>
      <td>9th</td>
      <td>64</td>
      <td>79</td>
    </tr>
    <tr>
      <th>13</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>13</td>
      <td>William Long</td>
      <td>M</td>
      <td>9th</td>
      <td>71</td>
      <td>79</td>
    </tr>
    <tr>
      <th>14</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>14</td>
      <td>Tammy Hebert</td>
      <td>F</td>
      <td>10th</td>
      <td>85</td>
      <td>67</td>
    </tr>
    <tr>
      <th>15</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>15</td>
      <td>Dr. Jordan Carson</td>
      <td>M</td>
      <td>11th</td>
      <td>94</td>
      <td>88</td>
    </tr>
    <tr>
      <th>16</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>16</td>
      <td>Donald Zamora</td>
      <td>M</td>
      <td>9th</td>
      <td>88</td>
      <td>55</td>
    </tr>
    <tr>
      <th>17</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>17</td>
      <td>Kimberly Santiago</td>
      <td>F</td>
      <td>9th</td>
      <td>74</td>
      <td>75</td>
    </tr>
    <tr>
      <th>18</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>18</td>
      <td>Kevin Stevens</td>
      <td>M</td>
      <td>9th</td>
      <td>64</td>
      <td>69</td>
    </tr>
    <tr>
      <th>19</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>19</td>
      <td>Brandi Lyons</td>
      <td>F</td>
      <td>9th</td>
      <td>89</td>
      <td>80</td>
    </tr>
    <tr>
      <th>20</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>20</td>
      <td>Lisa Davis</td>
      <td>F</td>
      <td>10th</td>
      <td>91</td>
      <td>89</td>
    </tr>
    <tr>
      <th>21</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>21</td>
      <td>Kristen Lopez</td>
      <td>F</td>
      <td>10th</td>
      <td>90</td>
      <td>77</td>
    </tr>
    <tr>
      <th>22</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>22</td>
      <td>Kimberly Stewart</td>
      <td>F</td>
      <td>11th</td>
      <td>99</td>
      <td>84</td>
    </tr>
    <tr>
      <th>23</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>23</td>
      <td>Christopher Parker</td>
      <td>M</td>
      <td>9th</td>
      <td>81</td>
      <td>68</td>
    </tr>
    <tr>
      <th>24</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>24</td>
      <td>Chelsea Griffith</td>
      <td>F</td>
      <td>11th</td>
      <td>85</td>
      <td>73</td>
    </tr>
    <tr>
      <th>25</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>25</td>
      <td>Cesar Morris</td>
      <td>M</td>
      <td>9th</td>
      <td>92</td>
      <td>70</td>
    </tr>
    <tr>
      <th>26</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>26</td>
      <td>Melanie Decker</td>
      <td>F</td>
      <td>9th</td>
      <td>63</td>
      <td>85</td>
    </tr>
    <tr>
      <th>27</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>27</td>
      <td>Tracey Oconnor</td>
      <td>F</td>
      <td>10th</td>
      <td>80</td>
      <td>58</td>
    </tr>
    <tr>
      <th>28</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>28</td>
      <td>Kelly James</td>
      <td>F</td>
      <td>11th</td>
      <td>73</td>
      <td>55</td>
    </tr>
    <tr>
      <th>29</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>29</td>
      <td>Nicole Brown</td>
      <td>F</td>
      <td>12th</td>
      <td>90</td>
      <td>88</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>39140</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39140</td>
      <td>Cheyenne Hernandez</td>
      <td>F</td>
      <td>9th</td>
      <td>76</td>
      <td>99</td>
    </tr>
    <tr>
      <th>39141</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39141</td>
      <td>Jonathan Sullivan</td>
      <td>M</td>
      <td>10th</td>
      <td>86</td>
      <td>93</td>
    </tr>
    <tr>
      <th>39142</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39142</td>
      <td>Deborah Higgins DDS</td>
      <td>F</td>
      <td>10th</td>
      <td>96</td>
      <td>83</td>
    </tr>
    <tr>
      <th>39143</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39143</td>
      <td>Steven Jackson</td>
      <td>M</td>
      <td>11th</td>
      <td>71</td>
      <td>93</td>
    </tr>
    <tr>
      <th>39144</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39144</td>
      <td>Cristian Webster</td>
      <td>M</td>
      <td>12th</td>
      <td>77</td>
      <td>87</td>
    </tr>
    <tr>
      <th>39145</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39145</td>
      <td>Audrey Fry</td>
      <td>F</td>
      <td>10th</td>
      <td>94</td>
      <td>74</td>
    </tr>
    <tr>
      <th>39146</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39146</td>
      <td>Michael Carroll</td>
      <td>M</td>
      <td>9th</td>
      <td>69</td>
      <td>95</td>
    </tr>
    <tr>
      <th>39147</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39147</td>
      <td>Raymond Hawkins</td>
      <td>M</td>
      <td>10th</td>
      <td>88</td>
      <td>81</td>
    </tr>
    <tr>
      <th>39148</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39148</td>
      <td>Christopher Wilson</td>
      <td>M</td>
      <td>10th</td>
      <td>89</td>
      <td>89</td>
    </tr>
    <tr>
      <th>39149</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39149</td>
      <td>Glenda Fletcher</td>
      <td>F</td>
      <td>11th</td>
      <td>82</td>
      <td>93</td>
    </tr>
    <tr>
      <th>39150</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39150</td>
      <td>Jennifer Hamilton</td>
      <td>F</td>
      <td>11th</td>
      <td>80</td>
      <td>75</td>
    </tr>
    <tr>
      <th>39151</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39151</td>
      <td>Shannon Williams</td>
      <td>F</td>
      <td>10th</td>
      <td>84</td>
      <td>73</td>
    </tr>
    <tr>
      <th>39152</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39152</td>
      <td>Lori Moore</td>
      <td>F</td>
      <td>9th</td>
      <td>98</td>
      <td>84</td>
    </tr>
    <tr>
      <th>39153</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39153</td>
      <td>William Hubbard</td>
      <td>M</td>
      <td>9th</td>
      <td>80</td>
      <td>75</td>
    </tr>
    <tr>
      <th>39154</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39154</td>
      <td>Bradley Johnson</td>
      <td>M</td>
      <td>12th</td>
      <td>91</td>
      <td>71</td>
    </tr>
    <tr>
      <th>39155</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39155</td>
      <td>John Brooks</td>
      <td>M</td>
      <td>10th</td>
      <td>92</td>
      <td>98</td>
    </tr>
    <tr>
      <th>39156</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39156</td>
      <td>Stephanie Contreras</td>
      <td>F</td>
      <td>11th</td>
      <td>79</td>
      <td>95</td>
    </tr>
    <tr>
      <th>39157</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39157</td>
      <td>Kristen Gonzalez</td>
      <td>F</td>
      <td>9th</td>
      <td>79</td>
      <td>94</td>
    </tr>
    <tr>
      <th>39158</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39158</td>
      <td>Kari Holloway</td>
      <td>F</td>
      <td>10th</td>
      <td>87</td>
      <td>90</td>
    </tr>
    <tr>
      <th>39159</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39159</td>
      <td>Kimberly Cabrera</td>
      <td>F</td>
      <td>11th</td>
      <td>85</td>
      <td>72</td>
    </tr>
    <tr>
      <th>39160</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39160</td>
      <td>Katie Weaver</td>
      <td>F</td>
      <td>11th</td>
      <td>89</td>
      <td>86</td>
    </tr>
    <tr>
      <th>39161</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39161</td>
      <td>April Reyes</td>
      <td>F</td>
      <td>10th</td>
      <td>70</td>
      <td>84</td>
    </tr>
    <tr>
      <th>39162</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39162</td>
      <td>Derek Weeks</td>
      <td>M</td>
      <td>12th</td>
      <td>94</td>
      <td>77</td>
    </tr>
    <tr>
      <th>39163</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39163</td>
      <td>John Reese</td>
      <td>M</td>
      <td>11th</td>
      <td>90</td>
      <td>75</td>
    </tr>
    <tr>
      <th>39164</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39164</td>
      <td>Joseph Anthony</td>
      <td>M</td>
      <td>9th</td>
      <td>97</td>
      <td>76</td>
    </tr>
    <tr>
      <th>39165</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39165</td>
      <td>Donna Howard</td>
      <td>F</td>
      <td>12th</td>
      <td>99</td>
      <td>90</td>
    </tr>
    <tr>
      <th>39166</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39166</td>
      <td>Dawn Bell</td>
      <td>F</td>
      <td>10th</td>
      <td>95</td>
      <td>70</td>
    </tr>
    <tr>
      <th>39167</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39167</td>
      <td>Rebecca Tanner</td>
      <td>F</td>
      <td>9th</td>
      <td>73</td>
      <td>84</td>
    </tr>
    <tr>
      <th>39168</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39168</td>
      <td>Desiree Kidd</td>
      <td>F</td>
      <td>10th</td>
      <td>99</td>
      <td>90</td>
    </tr>
    <tr>
      <th>39169</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>39169</td>
      <td>Carolyn Jackson</td>
      <td>F</td>
      <td>11th</td>
      <td>95</td>
      <td>75</td>
    </tr>
  </tbody>
</table>
<p>39170 rows × 11 columns</p>
</div>




```python
District = "District"
district_school_df = merge_table.loc[merge_table["School Type"] == District]
district_school_df
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
      <th>School Type</th>
      <th>School Size</th>
      <th>Budget</th>
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
    <tr>
      <th>5</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>5</td>
      <td>Bryan Miranda</td>
      <td>M</td>
      <td>9th</td>
      <td>94</td>
      <td>94</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>6</td>
      <td>Sheena Carter</td>
      <td>F</td>
      <td>11th</td>
      <td>82</td>
      <td>80</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>7</td>
      <td>Nicole Baker</td>
      <td>F</td>
      <td>12th</td>
      <td>96</td>
      <td>69</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>8</td>
      <td>Michael Roth</td>
      <td>M</td>
      <td>10th</td>
      <td>95</td>
      <td>87</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9</td>
      <td>Matthew Greene</td>
      <td>M</td>
      <td>10th</td>
      <td>96</td>
      <td>84</td>
    </tr>
    <tr>
      <th>10</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>10</td>
      <td>Andrew Alexander</td>
      <td>M</td>
      <td>10th</td>
      <td>90</td>
      <td>70</td>
    </tr>
    <tr>
      <th>11</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>11</td>
      <td>Daniel Cooper</td>
      <td>M</td>
      <td>10th</td>
      <td>78</td>
      <td>77</td>
    </tr>
    <tr>
      <th>12</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12</td>
      <td>Brittney Walker</td>
      <td>F</td>
      <td>9th</td>
      <td>64</td>
      <td>79</td>
    </tr>
    <tr>
      <th>13</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>13</td>
      <td>William Long</td>
      <td>M</td>
      <td>9th</td>
      <td>71</td>
      <td>79</td>
    </tr>
    <tr>
      <th>14</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>14</td>
      <td>Tammy Hebert</td>
      <td>F</td>
      <td>10th</td>
      <td>85</td>
      <td>67</td>
    </tr>
    <tr>
      <th>15</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>15</td>
      <td>Dr. Jordan Carson</td>
      <td>M</td>
      <td>11th</td>
      <td>94</td>
      <td>88</td>
    </tr>
    <tr>
      <th>16</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>16</td>
      <td>Donald Zamora</td>
      <td>M</td>
      <td>9th</td>
      <td>88</td>
      <td>55</td>
    </tr>
    <tr>
      <th>17</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>17</td>
      <td>Kimberly Santiago</td>
      <td>F</td>
      <td>9th</td>
      <td>74</td>
      <td>75</td>
    </tr>
    <tr>
      <th>18</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>18</td>
      <td>Kevin Stevens</td>
      <td>M</td>
      <td>9th</td>
      <td>64</td>
      <td>69</td>
    </tr>
    <tr>
      <th>19</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>19</td>
      <td>Brandi Lyons</td>
      <td>F</td>
      <td>9th</td>
      <td>89</td>
      <td>80</td>
    </tr>
    <tr>
      <th>20</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>20</td>
      <td>Lisa Davis</td>
      <td>F</td>
      <td>10th</td>
      <td>91</td>
      <td>89</td>
    </tr>
    <tr>
      <th>21</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>21</td>
      <td>Kristen Lopez</td>
      <td>F</td>
      <td>10th</td>
      <td>90</td>
      <td>77</td>
    </tr>
    <tr>
      <th>22</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>22</td>
      <td>Kimberly Stewart</td>
      <td>F</td>
      <td>11th</td>
      <td>99</td>
      <td>84</td>
    </tr>
    <tr>
      <th>23</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>23</td>
      <td>Christopher Parker</td>
      <td>M</td>
      <td>9th</td>
      <td>81</td>
      <td>68</td>
    </tr>
    <tr>
      <th>24</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>24</td>
      <td>Chelsea Griffith</td>
      <td>F</td>
      <td>11th</td>
      <td>85</td>
      <td>73</td>
    </tr>
    <tr>
      <th>25</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>25</td>
      <td>Cesar Morris</td>
      <td>M</td>
      <td>9th</td>
      <td>92</td>
      <td>70</td>
    </tr>
    <tr>
      <th>26</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>26</td>
      <td>Melanie Decker</td>
      <td>F</td>
      <td>9th</td>
      <td>63</td>
      <td>85</td>
    </tr>
    <tr>
      <th>27</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>27</td>
      <td>Tracey Oconnor</td>
      <td>F</td>
      <td>10th</td>
      <td>80</td>
      <td>58</td>
    </tr>
    <tr>
      <th>28</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>28</td>
      <td>Kelly James</td>
      <td>F</td>
      <td>11th</td>
      <td>73</td>
      <td>55</td>
    </tr>
    <tr>
      <th>29</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>29</td>
      <td>Nicole Brown</td>
      <td>F</td>
      <td>12th</td>
      <td>90</td>
      <td>88</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>37505</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37505</td>
      <td>Jason Wagner</td>
      <td>M</td>
      <td>12th</td>
      <td>97</td>
      <td>80</td>
    </tr>
    <tr>
      <th>37506</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37506</td>
      <td>Maurice Nielsen</td>
      <td>M</td>
      <td>12th</td>
      <td>76</td>
      <td>66</td>
    </tr>
    <tr>
      <th>37507</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37507</td>
      <td>James Turner</td>
      <td>M</td>
      <td>12th</td>
      <td>73</td>
      <td>74</td>
    </tr>
    <tr>
      <th>37508</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37508</td>
      <td>Larry Pope</td>
      <td>M</td>
      <td>9th</td>
      <td>74</td>
      <td>61</td>
    </tr>
    <tr>
      <th>37509</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37509</td>
      <td>Robert Martin</td>
      <td>M</td>
      <td>12th</td>
      <td>80</td>
      <td>67</td>
    </tr>
    <tr>
      <th>37510</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37510</td>
      <td>Darius Jimenez</td>
      <td>M</td>
      <td>12th</td>
      <td>89</td>
      <td>82</td>
    </tr>
    <tr>
      <th>37511</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37511</td>
      <td>Daniel Turner</td>
      <td>M</td>
      <td>10th</td>
      <td>68</td>
      <td>58</td>
    </tr>
    <tr>
      <th>37512</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37512</td>
      <td>Lauren Cook</td>
      <td>F</td>
      <td>9th</td>
      <td>84</td>
      <td>72</td>
    </tr>
    <tr>
      <th>37513</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37513</td>
      <td>Wayne Washington</td>
      <td>M</td>
      <td>11th</td>
      <td>79</td>
      <td>63</td>
    </tr>
    <tr>
      <th>37514</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37514</td>
      <td>Leslie White</td>
      <td>F</td>
      <td>12th</td>
      <td>80</td>
      <td>73</td>
    </tr>
    <tr>
      <th>37515</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37515</td>
      <td>Maria Andrade</td>
      <td>F</td>
      <td>12th</td>
      <td>69</td>
      <td>87</td>
    </tr>
    <tr>
      <th>37516</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37516</td>
      <td>Tracy Sanchez</td>
      <td>F</td>
      <td>11th</td>
      <td>76</td>
      <td>75</td>
    </tr>
    <tr>
      <th>37517</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37517</td>
      <td>Kayla Johnson</td>
      <td>F</td>
      <td>9th</td>
      <td>71</td>
      <td>80</td>
    </tr>
    <tr>
      <th>37518</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37518</td>
      <td>Daniel Andrews</td>
      <td>M</td>
      <td>9th</td>
      <td>89</td>
      <td>98</td>
    </tr>
    <tr>
      <th>37519</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37519</td>
      <td>Ruben Ramirez</td>
      <td>M</td>
      <td>12th</td>
      <td>84</td>
      <td>65</td>
    </tr>
    <tr>
      <th>37520</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37520</td>
      <td>Benjamin Odonnell</td>
      <td>M</td>
      <td>11th</td>
      <td>63</td>
      <td>74</td>
    </tr>
    <tr>
      <th>37521</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37521</td>
      <td>Meredith Tapia</td>
      <td>F</td>
      <td>9th</td>
      <td>77</td>
      <td>78</td>
    </tr>
    <tr>
      <th>37522</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37522</td>
      <td>Ricky Little</td>
      <td>M</td>
      <td>12th</td>
      <td>90</td>
      <td>68</td>
    </tr>
    <tr>
      <th>37523</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37523</td>
      <td>Rebecca Valenzuela</td>
      <td>F</td>
      <td>10th</td>
      <td>90</td>
      <td>84</td>
    </tr>
    <tr>
      <th>37524</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37524</td>
      <td>Carrie Fletcher</td>
      <td>F</td>
      <td>9th</td>
      <td>84</td>
      <td>72</td>
    </tr>
    <tr>
      <th>37525</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37525</td>
      <td>Steven Summers</td>
      <td>M</td>
      <td>9th</td>
      <td>71</td>
      <td>71</td>
    </tr>
    <tr>
      <th>37526</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37526</td>
      <td>Jon Santiago</td>
      <td>M</td>
      <td>10th</td>
      <td>98</td>
      <td>56</td>
    </tr>
    <tr>
      <th>37527</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37527</td>
      <td>Thomas Christensen</td>
      <td>M</td>
      <td>9th</td>
      <td>98</td>
      <td>60</td>
    </tr>
    <tr>
      <th>37528</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37528</td>
      <td>Nicholas Perry</td>
      <td>M</td>
      <td>11th</td>
      <td>83</td>
      <td>83</td>
    </tr>
    <tr>
      <th>37529</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37529</td>
      <td>Victoria Rodriguez</td>
      <td>F</td>
      <td>11th</td>
      <td>76</td>
      <td>69</td>
    </tr>
    <tr>
      <th>37530</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37530</td>
      <td>William Rivera</td>
      <td>M</td>
      <td>9th</td>
      <td>63</td>
      <td>59</td>
    </tr>
    <tr>
      <th>37531</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37531</td>
      <td>Bernard Reid</td>
      <td>M</td>
      <td>9th</td>
      <td>94</td>
      <td>80</td>
    </tr>
    <tr>
      <th>37532</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37532</td>
      <td>Dawn Sawyer</td>
      <td>F</td>
      <td>12th</td>
      <td>91</td>
      <td>66</td>
    </tr>
    <tr>
      <th>37533</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37533</td>
      <td>Thomas Knapp</td>
      <td>M</td>
      <td>12th</td>
      <td>75</td>
      <td>70</td>
    </tr>
    <tr>
      <th>37534</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>37534</td>
      <td>Melissa Porter</td>
      <td>F</td>
      <td>9th</td>
      <td>76</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
<p>26976 rows × 11 columns</p>
</div>




```python
grouped_df=merge_table.groupby("School Type")
d_school_df = grouped_df["school"].nunique()
d_school_df
```




    School Type
    Charter     8
    District    7
    Name: school, dtype: int64




```python
total_student=len(district_school_df["school"].value_counts())
total_student
```




    7




```python
total_d_students=district_school_df["Student ID"].count()
total_d_students
```




    26976




```python
total_d_budget=district_school_df["Budget"].unique().sum()
total_d_budget
```




    17347923




```python
avg_math_score=district_school_df["math_score"].mean()
avg_math_score
```




    76.98702550415184




```python
avg_reading_score=district_school_df["reading_score"].mean()
avg_reading_score
```




    80.96248517200475




```python
#total_student= district_school_df["reading_score"].value_count()
#total_student
pass_reading = (district_school_df["reading_score"] >=70).value_counts()
pass_reading

```




    True     21825
    False     5151
    Name: reading_score, dtype: int64




```python
pass_reading_rate=21825/total_d_students*100
pass_reading_rate
```




    80.905249110320284




```python
pass_math = (district_school_df["math_score"] >=70).value_counts()
pass_math
```




    True     17944
    False     9032
    Name: math_score, dtype: int64




```python
pass_math_rate=17944/total_d_students*100
pass_math_rate
```




    66.518386714116247




```python
overall_passing_rate=(pass_reading_rate + pass_math_rate)/2
overall_passing_rate
```




    73.711817912218265




```python
district_summary = pd.DataFrame({"Total School": [total_student],
                                   "Total Student": [total_d_students],
                                   "Total Budget": [total_d_budget],
                                   "Avg Math Score": [avg_math_score],
                                   "Avg Reading Score": [avg_reading_score],
                                   "% Passing Math":[pass_math_rate],
                                   "% Passing Reading":[pass_reading_rate],
                                   "% Overall Passing Rate": [overall_passing_rate]
                                   })
district_summary = district_summary[["Total School", 
                                       "Total Student", 
                                         "Total Budget", 
                                         "Avg Math Score", 
                                         "Avg Reading Score", 
                                          "% Passing Math", 
                                         "% Passing Reading",
                                         "% Overall Passing Rate"
                                   ]]
district_summary
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
      <th>Total School</th>
      <th>Total Student</th>
      <th>Total Budget</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>26976</td>
      <td>17347923</td>
      <td>76.987026</td>
      <td>80.962485</td>
      <td>66.518387</td>
      <td>80.905249</td>
      <td>73.711818</td>
    </tr>
  </tbody>
</table>
</div>




```python
district_summary["Total Budget"] = district_summary["Total Budget"].map("${0:,.0f}".format)
```


```python
district_summary
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
      <th>Total School</th>
      <th>Total Student</th>
      <th>Total Budget</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>% Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>26976</td>
      <td>$17,347,923</td>
      <td>76.987026</td>
      <td>80.962485</td>
      <td>66.518387</td>
      <td>80.905249</td>
      <td>73.711818</td>
    </tr>
  </tbody>
</table>
</div>




```python
cut_school_df=merge_table.iloc[:,1:5]
cut_school_df.head()
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
      <th>school</th>
      <th>School Type</th>
      <th>School Size</th>
      <th>Budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
  </tbody>
</table>
</div>




```python
total_school_df=cut_school_df.drop_duplicates(['school'], keep='last')
total_school_df
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
      <th>school</th>
      <th>School Type</th>
      <th>School Size</th>
      <th>Budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2916</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>5865</th>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>7626</th>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>12261</th>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>13729</th>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
    <tr>
      <th>16012</th>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
    </tr>
    <tr>
      <th>17870</th>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858</td>
      <td>1081356</td>
    </tr>
    <tr>
      <th>22846</th>
      <td>Bailey High School</td>
      <td>District</td>
      <td>4976</td>
      <td>3124928</td>
    </tr>
    <tr>
      <th>23273</th>
      <td>Holden High School</td>
      <td>Charter</td>
      <td>427</td>
      <td>248087</td>
    </tr>
    <tr>
      <th>24235</th>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
    </tr>
    <tr>
      <th>26035</th>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
    </tr>
    <tr>
      <th>30034</th>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
    </tr>
    <tr>
      <th>34795</th>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
    </tr>
    <tr>
      <th>37534</th>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
    </tr>
    <tr>
      <th>39169</th>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
    </tr>
  </tbody>
</table>
</div>




```python
total_school_df['Per Student Budget'] = (total_school_df['Budget'] / total_school_df['School Size'])
total_school_df
```

    /Users/kezhao/anaconda3/lib/python3.6/site-packages/ipykernel_launcher.py:1: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy
      """Entry point for launching an IPython kernel.





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
      <th>school</th>
      <th>School Type</th>
      <th>School Size</th>
      <th>Budget</th>
      <th>Per Student Budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2916</th>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>655.0</td>
    </tr>
    <tr>
      <th>5865</th>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
      <td>639.0</td>
    </tr>
    <tr>
      <th>7626</th>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
      <td>600.0</td>
    </tr>
    <tr>
      <th>12261</th>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
      <td>652.0</td>
    </tr>
    <tr>
      <th>13729</th>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
      <td>625.0</td>
    </tr>
    <tr>
      <th>16012</th>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
      <td>578.0</td>
    </tr>
    <tr>
      <th>17870</th>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858</td>
      <td>1081356</td>
      <td>582.0</td>
    </tr>
    <tr>
      <th>22846</th>
      <td>Bailey High School</td>
      <td>District</td>
      <td>4976</td>
      <td>3124928</td>
      <td>628.0</td>
    </tr>
    <tr>
      <th>23273</th>
      <td>Holden High School</td>
      <td>Charter</td>
      <td>427</td>
      <td>248087</td>
      <td>581.0</td>
    </tr>
    <tr>
      <th>24235</th>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
      <td>609.0</td>
    </tr>
    <tr>
      <th>26035</th>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
      <td>583.0</td>
    </tr>
    <tr>
      <th>30034</th>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
      <td>637.0</td>
    </tr>
    <tr>
      <th>34795</th>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
      <td>650.0</td>
    </tr>
    <tr>
      <th>37534</th>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
      <td>644.0</td>
    </tr>
    <tr>
      <th>39169</th>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
      <td>638.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
high_school_df = merge_table.groupby("school")
sum_reading_school_df = high_school_df["reading_score"].mean()
sum_reading_school_df
```




    school
    Bailey High School       81.033963
    Cabrera High School      83.975780
    Figueroa High School     81.158020
    Ford High School         80.746258
    Griffin High School      83.816757
    Hernandez High School    80.934412
    Holden High School       83.814988
    Huang High School        81.182722
    Johnson High School      80.966394
    Pena High School         84.044699
    Rodriguez High School    80.744686
    Shelton High School      83.725724
    Thomas High School       83.848930
    Wilson High School       83.989488
    Wright High School       83.955000
    Name: reading_score, dtype: float64




```python
sum_math_school_df = high_school_df["math_score"].mean()
sum_math_school_df
```




    school
    Bailey High School       77.048432
    Cabrera High School      83.061895
    Figueroa High School     76.711767
    Ford High School         77.102592
    Griffin High School      83.351499
    Hernandez High School    77.289752
    Holden High School       83.803279
    Huang High School        76.629414
    Johnson High School      77.072464
    Pena High School         83.839917
    Rodriguez High School    76.842711
    Shelton High School      83.359455
    Thomas High School       83.418349
    Wilson High School       83.274201
    Wright High School       83.682222
    Name: math_score, dtype: float64


