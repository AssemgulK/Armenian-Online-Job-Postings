
# Data Wrangling Template

## Gather


```python
import pandas as pd
import zipfile
```


```python
# Extract all contents from zip file
with zipfile.ZipFile('armenian-online-job-postings.zip', 'r') as myzip:
    myzip.extractall()
```


```python
# Read CSV (comma-separated) file into DataFrame
df = pd.read_csv('online-job-postings.csv')
```

## Assess


```python
df
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
      <th>jobpost</th>
      <th>date</th>
      <th>Title</th>
      <th>Company</th>
      <th>AnnouncementCode</th>
      <th>Term</th>
      <th>Eligibility</th>
      <th>Audience</th>
      <th>StartDate</th>
      <th>Duration</th>
      <th>...</th>
      <th>Salary</th>
      <th>ApplicationP</th>
      <th>OpeningDate</th>
      <th>Deadline</th>
      <th>Notes</th>
      <th>AboutC</th>
      <th>Attach</th>
      <th>Year</th>
      <th>Month</th>
      <th>IT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>AMERIA Investment Consulting Company\r\nJOB TI...</td>
      <td>Jan 5, 2004</td>
      <td>Chief Financial Officer</td>
      <td>AMERIA Investment Consulting Company</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>To apply for this position, please submit a\r\...</td>
      <td>NaN</td>
      <td>26 January 2004</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>International Research &amp; Exchanges Board (IREX...</td>
      <td>Jan 7, 2004</td>
      <td>Full-time Community Connections Intern (paid i...</td>
      <td>International Research &amp; Exchanges Board (IREX)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3 months</td>
      <td>...</td>
      <td>NaN</td>
      <td>Please submit a cover letter and resume to:\r\...</td>
      <td>NaN</td>
      <td>12 January 2004</td>
      <td>NaN</td>
      <td>The International Research &amp; Exchanges Board (...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Caucasus Environmental NGO Network (CENN)\r\nJ...</td>
      <td>Jan 7, 2004</td>
      <td>Country Coordinator</td>
      <td>Caucasus Environmental NGO Network (CENN)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Renewable annual contract\r\nPOSITION</td>
      <td>...</td>
      <td>NaN</td>
      <td>Please send resume or CV toursula.kazarian@......</td>
      <td>NaN</td>
      <td>20 January 2004\r\nSTART DATE:  February 2004</td>
      <td>NaN</td>
      <td>The Caucasus Environmental NGO Network is a\r\...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Manoff Group\r\nJOB TITLE:  BCC Specialist\r\n...</td>
      <td>Jan 7, 2004</td>
      <td>BCC Specialist</td>
      <td>Manoff Group</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Please send cover letter and resume to Amy\r\n...</td>
      <td>NaN</td>
      <td>23 January 2004\r\nSTART DATE:  Immediate</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Yerevan Brandy Company\r\nJOB TITLE:  Software...</td>
      <td>Jan 10, 2004</td>
      <td>Software Developer</td>
      <td>Yerevan Brandy Company</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Successful candidates should submit\r\n- CV; \...</td>
      <td>NaN</td>
      <td>20 January 2004, 18:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>True</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Boutique "Appollo"\r\nJOB TITLE:  Saleswoman\r...</td>
      <td>Jan 10, 2004</td>
      <td>Saleswoman</td>
      <td>Boutique "Appollo"</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>For further information, please contact Irina\...</td>
      <td>NaN</td>
      <td>01 February 2004</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>6</th>
      <td>OSI Assistance Foundation - Armenian Branch Of...</td>
      <td>Jan 11, 2004</td>
      <td>Chief Accountant/ Finance Assistant</td>
      <td>OSI Assistance Foundation - Armenian Branch Of...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>For submission of applications/ CVs, please\r\...</td>
      <td>NaN</td>
      <td>16 January 2004, 6:00 pm.</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>7</th>
      <td>International Research &amp; Exchanges Board (IREX...</td>
      <td>Jan 13, 2004</td>
      <td>Non-paid part or full time Programmatic Intern</td>
      <td>International Research &amp; Exchanges Board (IREX)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6 months</td>
      <td>...</td>
      <td>NaN</td>
      <td>To apply, please download and submit the\r\nap...</td>
      <td>NaN</td>
      <td>16 January 2004</td>
      <td>NaN</td>
      <td>The International Research &amp; Exchanges Board (...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Yerevan Brandy Company \r\nJOB TITLE:  Assista...</td>
      <td>Jan 13, 2004</td>
      <td>Assistant to Managing Director</td>
      <td>Yerevan Brandy Company</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Successful candidates should submit\r\n- CV; \...</td>
      <td>NaN</td>
      <td>27 January 2004, 18:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>9</th>
      <td>American Embassy Yerevan\r\nANNOUNCEMENT NUMBE...</td>
      <td>Jan 13, 2004</td>
      <td>Program Assistant (INL), FSN-8; FP-6*</td>
      <td>American Embassy Yerevan\r\nANNOUNCEMENT NUMBE...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested candidates for this position should...</td>
      <td>NaN</td>
      <td>26 January 2004  \r\nDrafted:   GSargsyan\r\nC...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>10</th>
      <td>International Research &amp; Exchanges Board (IREX...</td>
      <td>Jan 13, 2004</td>
      <td>Short-Term Travel Grants (STG) Program</td>
      <td>International Research &amp; Exchanges Board (IREX)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>For more information on this program, please\r...</td>
      <td>NaN</td>
      <td>Applications are due in the IREX office by 01\...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>11</th>
      <td>International Research &amp; Exchanges Board (IREX...</td>
      <td>Jan 13, 2004</td>
      <td>Non-paid part or full time Administrative Intern</td>
      <td>International Research &amp; Exchanges Board (IREX)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6 months</td>
      <td>...</td>
      <td>NaN</td>
      <td>To apply, please download and submit the\r\nap...</td>
      <td>NaN</td>
      <td>16 January 2004</td>
      <td>NaN</td>
      <td>The International Research &amp; Exchanges Board (...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Institute for Sustainable Communities (ISC)\r\...</td>
      <td>Jan 13, 2004</td>
      <td>Chief of Party (COP)</td>
      <td>Institute for Sustainable Communities (ISC)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5 year\r\nPOSITION</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested applicants should send a cover\r\nl...</td>
      <td>NaN</td>
      <td>08 February 2004</td>
      <td>NaN</td>
      <td>Water User Associations Support Program (WUASP...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Food Security Regional Cooperation and Stabili...</td>
      <td>Jan 14, 2004</td>
      <td>Community Development, Capacity Building and C...</td>
      <td>Food Security Regional Cooperation and Stabili...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested persons should submit cover letter,...</td>
      <td>NaN</td>
      <td>Open until filled</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Teleplus LLC\r\nJOB TITLE:  General Manager\r\...</td>
      <td>Jan 14, 2004</td>
      <td>General Manager</td>
      <td>Teleplus LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>If you believe that you fulfill the above\r\np...</td>
      <td>NaN</td>
      <td>Open</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>15</th>
      <td>NetCall Communications\r\nJOB TITLE:  Network ...</td>
      <td>Jan 15, 2004</td>
      <td>Network Administrator</td>
      <td>NetCall Communications</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Successful candidates should submit CV and 1-2...</td>
      <td>NaN</td>
      <td>28 February 2004, 18:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>True</td>
    </tr>
    <tr>
      <th>16</th>
      <td>SOC.Stockholm\r\nTITLE:   Utopian World Champi...</td>
      <td>Jan 15, 2004</td>
      <td>Utopian World Championship 2004</td>
      <td>SOC.Stockholm</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Visit http://www.soc.nu for detailed\r\ninform...</td>
      <td>NaN</td>
      <td>Deadline for entry is on 31 January 2004 and f...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>17</th>
      <td>United Nations Development Programme, Armenia\...</td>
      <td>Jan 15, 2004</td>
      <td>Country Economist (NOB)</td>
      <td>United Nations Development Programme, Armenia</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3 months initial.</td>
      <td>...</td>
      <td>NaN</td>
      <td>Applications can be submitted throughhttp://oc...</td>
      <td>NaN</td>
      <td>24 January 2004, 17:00.</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Counterpart International, Inc.\r\nCounterpart...</td>
      <td>Jan 16, 2004</td>
      <td>Driver/ Logistics Assistant</td>
      <td>Counterpart International, Inc.\r\nCounterpart...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Qualified individuals should submit a current\...</td>
      <td>NaN</td>
      <td>21 January 2004, 5 pm\r\nABOUT PROGRAM:  The C...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Xalt LLC\r\nJOB TITLE:  Graphic Designer\r\nPO...</td>
      <td>Jan 16, 2004</td>
      <td>Graphic Designer</td>
      <td>Xalt LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested applicants should send CVs by email...</td>
      <td>NaN</td>
      <td>26 January 2004</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>True</td>
    </tr>
    <tr>
      <th>20</th>
      <td>CUTS Centre for International Trade, Economics...</td>
      <td>Jan 19, 2004</td>
      <td>Administrative Assistant</td>
      <td>CUTS Centre for International Trade, Economics...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>There is no application pack. Send your CV,\r\...</td>
      <td>NaN</td>
      <td>26 January 2004\r\nSTART DATE:  End of February</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Yerevan Brandy Company\r\nJOB TITLE:  Lawyer\r...</td>
      <td>Jan 19, 2004</td>
      <td>Lawyer</td>
      <td>Yerevan Brandy Company</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Successful candidates should submit\r\n- CV; \...</td>
      <td>NaN</td>
      <td>06 February 2004, 18:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>22</th>
      <td>ACDI/VOCA\r\nJOB TITLE:  Marketing Advisor\r\n...</td>
      <td>Jan 19, 2004</td>
      <td>Marketing Advisor</td>
      <td>ACDI/VOCA</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>30 month position   \r\nPOSITION</td>
      <td>...</td>
      <td>NaN</td>
      <td>Submit CV and salary requirements toeurasia@.....</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ACDI/VOCA is an international development and ...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Armenia TV\r\nJOB TITLE:  Chief/ Supervisor of...</td>
      <td>Jan 20, 2004</td>
      <td>Chief/ Supervisor of Programs Department</td>
      <td>Armenia TV</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3 year\r\nPOSITION</td>
      <td>...</td>
      <td>NaN</td>
      <td>Please, call 584969 (10.00-18.30)\r\nPlease cl...</td>
      <td>NaN</td>
      <td>Until hired\r\nSTART DATE:  As soon as possible</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Media Diversity Institute\r\nJOB TITLE:  Journ...</td>
      <td>Jan 20, 2004</td>
      <td>Journalism Trainer</td>
      <td>Media Diversity Institute</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Applicants are required to submit:\r\n- Short ...</td>
      <td>NaN</td>
      <td>26 January 2004</td>
      <td>NaN</td>
      <td>The Media Diversity Institute (MDI) is a Londo...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Armenia School Connectivity Program\r\nJOB TIT...</td>
      <td>Jan 21, 2004</td>
      <td>Deputy Program Director</td>
      <td>Armenia School Connectivity Program</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested applicants should send cover letter...</td>
      <td>NaN</td>
      <td>06 February 2004\r\nABOUT PROGRAM:  Armenia Sc...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Yerevan State University (YSU) and Civic Educa...</td>
      <td>Jan 21, 2004</td>
      <td>Student Forum: Student Conference and Debate F...</td>
      <td>Yerevan State University (YSU) and Civic Educa...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>17-18 April 2004\r\nDESCRIPTION:   The confere...</td>
      <td>...</td>
      <td>NaN</td>
      <td>For further details and the student applicatio...</td>
      <td>NaN</td>
      <td>21 February 2004</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Media Diversity Institute\r\nJOB TITLE:  Repor...</td>
      <td>Jan 21, 2004</td>
      <td>Reporting Diversity Workshop for Journalists</td>
      <td>Media Diversity Institute</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Please, submit your CVs to Artur Papyan, MDI\r...</td>
      <td>NaN</td>
      <td>26 January 2004</td>
      <td>NaN</td>
      <td>The Media Diversity Institute (MDI) is a Londo...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Media Diversity Institute\r\nTITLE:   Reportin...</td>
      <td>Jan 21, 2004</td>
      <td>Reporting Diversity Workshop for Journalists</td>
      <td>Media Diversity Institute</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3 days</td>
      <td>...</td>
      <td>NaN</td>
      <td>Applicants are required to submit:\r\n- Short ...</td>
      <td>NaN</td>
      <td>31 January 2004</td>
      <td>NaN</td>
      <td>The Media Diversity Institute (MDI) is a Londo...</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>29</th>
      <td>SEF International\r\nJOB TITLE:  Chief Account...</td>
      <td>Jan 23, 2004</td>
      <td>Chief Accountant</td>
      <td>SEF International</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Please submit your CVs to the following e-mail...</td>
      <td>NaN</td>
      <td>29 January 2004</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2004</td>
      <td>1</td>
      <td>False</td>
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
      <th>18971</th>
      <td>Career Center NGO\r\n\r\n\r\nTITLE:  Reception...</td>
      <td>Dec 22, 2015</td>
      <td>Receptionist/ Administrative Assistant</td>
      <td>Career Center NGO</td>
      <td>NaN</td>
      <td>Part-time/ Full-time</td>
      <td>Everyone</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>To apply for this position, please open\r\nwww...</td>
      <td>23 December 2015</td>
      <td>06 January 2016</td>
      <td>This is an excellent opportunity especially fo...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18972</th>
      <td>Essential Solutions LLC\r\n\r\n\r\nTITLE:  Jav...</td>
      <td>Dec 22, 2015</td>
      <td>Java, Grails/ Groovie Developer</td>
      <td>Essential Solutions LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>To apply, please send a CV to:\r\ninfo@... .\r...</td>
      <td>23 December 2015</td>
      <td>22 January 2016</td>
      <td>NaN</td>
      <td>Essential Solutions specializes in providing I...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18973</th>
      <td>Essential Solutions LLC\r\n\r\n\r\nTITLE:  Sen...</td>
      <td>Dec 22, 2015</td>
      <td>Senior Java Software Engineer</td>
      <td>Essential Solutions LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>Permanent</td>
      <td>...</td>
      <td>Competitive, family medical insurance coverage.</td>
      <td>Interested candidates are asked to send their\...</td>
      <td>23 December 2015</td>
      <td>22 January 2016</td>
      <td>NaN</td>
      <td>Please visit: www.essentialsln.com for more in...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18974</th>
      <td>LTX-Credence Armenia LLC\r\n\r\n\r\nTITLE:  CA...</td>
      <td>Dec 23, 2015</td>
      <td>CAD Librarian (Printed Circuit Board Design)</td>
      <td>LTX-Credence Armenia LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested candidates are kindly requested to\...</td>
      <td>23 December 2015</td>
      <td>22 January 2016</td>
      <td>NaN</td>
      <td>LTX-Credence Armenia is an engineering develop...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18975</th>
      <td>LTX-Credence Armenia LLC\r\n\r\n\r\nTITLE:  In...</td>
      <td>Dec 23, 2015</td>
      <td>Intern ( Coop Tech): Precision Analog HW Design</td>
      <td>LTX-Credence Armenia LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested candidates are kindly requested to\...</td>
      <td>23 December 2015</td>
      <td>22 January 2016</td>
      <td>NaN</td>
      <td>LTX-Credence Armenia is an engineering develop...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18976</th>
      <td>SAS Group LLC\r\n\r\n\r\nTITLE:  Senior Financ...</td>
      <td>Dec 22, 2015</td>
      <td>Senior Financial Specialist</td>
      <td>SAS Group LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>Long-term</td>
      <td>...</td>
      <td>Highly competitive</td>
      <td>Interested candidates are encouraged to submit...</td>
      <td>23 December 2015</td>
      <td>22 January 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18977</th>
      <td>Strategic Development Agency (SDA) NGO\r\n\r\n...</td>
      <td>Dec 22, 2015</td>
      <td>Business Consultant</td>
      <td>Strategic Development Agency (SDA) NGO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Long-term, with a probation period of 3 months.</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested candidates can send their full CVs\...</td>
      <td>23 December 2015</td>
      <td>15 January 2016</td>
      <td>NaN</td>
      <td>"Strategic Development Agency" (SDA) NGO is a ...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18978</th>
      <td>Representation of the "French Office for Immig...</td>
      <td>Dec 22, 2015</td>
      <td>National Expert on Socio-Demographic Statistics</td>
      <td>Representation of the "French Office for Immig...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>15 February 2015</td>
      <td>4 - 5 months</td>
      <td>...</td>
      <td>NaN</td>
      <td>To apply for this position, please submit a\r\...</td>
      <td>23 December 2015</td>
      <td>12 January 2016</td>
      <td>NaN</td>
      <td>The French Office for Immigration and Integrat...</td>
      <td>The following attachment(s) to this announceme...</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18979</th>
      <td>Care Building Services LLC\r\n\r\n\r\nTITLE:  ...</td>
      <td>Dec 23, 2015</td>
      <td>Project Assistant</td>
      <td>Care Building Services LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>All eligible candidates.</td>
      <td>NaN</td>
      <td>Immediately</td>
      <td>Long-term</td>
      <td>...</td>
      <td>Highly competitive</td>
      <td>To apply for this position, please submit your...</td>
      <td>23 December 2015</td>
      <td>20 January 2016</td>
      <td>NaN</td>
      <td>Care Building Services LLC is a Yerevan based\...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18980</th>
      <td>LTX-Credence Armenia LLC\r\n\r\n\r\nTITLE:  Ha...</td>
      <td>Dec 23, 2015</td>
      <td>Hardware Engineer</td>
      <td>LTX-Credence Armenia LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested candidates are kindly requested to\...</td>
      <td>23 December 2015</td>
      <td>22 January 2016</td>
      <td>NaN</td>
      <td>LTX-Credence Armenia is an engineering develop...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18981</th>
      <td>BDO Armenia CJSC\r\n\r\n\r\nTITLE:  Auditor\r\...</td>
      <td>Dec 23, 2015</td>
      <td>Auditor</td>
      <td>BDO Armenia CJSC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>NaN</td>
      <td>...</td>
      <td>Based on the companys remuneration scheme.</td>
      <td>All interested and qualified candidates are\r\...</td>
      <td>23 December 2015</td>
      <td>11 January 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>The following attachment(s) to this announceme...</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18982</th>
      <td>BDO Armenia CJSC\r\n\r\n\r\nTITLE:  Senior Aud...</td>
      <td>Dec 23, 2015</td>
      <td>Senior Auditor</td>
      <td>BDO Armenia CJSC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>NaN</td>
      <td>...</td>
      <td>Based on the companys remuneration scheme.</td>
      <td>All interested and qualified candidates are\r\...</td>
      <td>23 December 2015</td>
      <td>11 January 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>The following attachment(s) to this announceme...</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18983</th>
      <td>Care Building Services LLC\r\n\r\n\r\nTITLE:  ...</td>
      <td>Dec 23, 2015</td>
      <td>Construction Site Manager</td>
      <td>Care Building Services LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>All eligible candidates.</td>
      <td>NaN</td>
      <td>Immediately</td>
      <td>Long-term</td>
      <td>...</td>
      <td>Highly competitive</td>
      <td>To apply for this position, please submit your...</td>
      <td>23 December 2015</td>
      <td>20 January 2016</td>
      <td>NaN</td>
      <td>Care Building Services LLC is a Yerevan based\...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18984</th>
      <td>Care Building Services LLC\r\n\r\n\r\nTITLE:  ...</td>
      <td>Dec 23, 2015</td>
      <td>Electrical Engineer</td>
      <td>Care Building Services LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>All eligible candidates.</td>
      <td>NaN</td>
      <td>Immediately</td>
      <td>Long-term</td>
      <td>...</td>
      <td>Highly competitive</td>
      <td>To apply for this position, please submit your...</td>
      <td>23 December 2015</td>
      <td>20 January 2016</td>
      <td>NaN</td>
      <td>Care Building Services LLC is a Yerevan based\...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18985</th>
      <td>Strategic Development Agency (SDA) NGO\r\n\r\n...</td>
      <td>Dec 22, 2015</td>
      <td>Project Assistant</td>
      <td>Strategic Development Agency (SDA) NGO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Long-term, with a probation period of 3 months.</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested candidates can send their full CVs\...</td>
      <td>23 December 2015</td>
      <td>15 January 2016</td>
      <td>NaN</td>
      <td>"Strategic Development Agency" (SDA) NGO is a ...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18986</th>
      <td>Strategic Development Agency (SDA) NGO\r\n\r\n...</td>
      <td>Dec 22, 2015</td>
      <td>Public Relations Specialist</td>
      <td>Strategic Development Agency (SDA) NGO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Long-term, with a probation period of 3 months.</td>
      <td>...</td>
      <td>NaN</td>
      <td>Interested candidates can send their full CVs\...</td>
      <td>23 December 2015</td>
      <td>15 January 2016</td>
      <td>NaN</td>
      <td>"Strategic Development Agency" (SDA) NGO is a ...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18987</th>
      <td>PicsArt LLC\r\n\r\n\r\nTITLE:  Junior Mobile V...</td>
      <td>Dec 24, 2015</td>
      <td>Junior Mobile Visual UI/ UX Designer</td>
      <td>PicsArt LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>Long-term</td>
      <td>...</td>
      <td>NaN</td>
      <td>To apply for this position, please send a lett...</td>
      <td>24 December 2015</td>
      <td>23 January 2016</td>
      <td>NaN</td>
      <td>PicsArt LLC is a US based free and full featur...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18988</th>
      <td>Berg Development LLC\r\n\r\n\r\nTITLE:  JavaSc...</td>
      <td>Dec 24, 2015</td>
      <td>JavaScript Professional</td>
      <td>Berg Development LLC</td>
      <td>NaN</td>
      <td>Full-time</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Immediately</td>
      <td>NaN</td>
      <td>...</td>
      <td>Highly competitive</td>
      <td>To apply for this position please send your\r\...</td>
      <td>24 December 2015</td>
      <td>23 January 2016</td>
      <td>Berg Development LLC does not hire smokers.</td>
      <td>Bergx2 GmbH is a German specialist for digital...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18989</th>
      <td>"Transport PIU" State Institution of the RA Mi...</td>
      <td>Dec 24, 2015</td>
      <td>Leading Specialist/ Accountant of Financial an...</td>
      <td>"Transport PIU" State Institution of the RA Mi...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>All interested and qualified candidates.</td>
      <td>NaN</td>
      <td>As soon as possible.</td>
      <td>Long-term with a probation period of 3 months.</td>
      <td>...</td>
      <td>Commensurate with skills and experience.</td>
      <td>Interested candidates are asked to submit the\...</td>
      <td>25 December 2015</td>
      <td>24 January 2016, 17:00 p.m.</td>
      <td>NaN</td>
      <td>The "Transport PIU" SI (PIU) of the RA Ministr...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18990</th>
      <td>NASDAQ OMX Armenia OJSC\r\n\r\n\r\nTITLE:  Jav...</td>
      <td>Dec 24, 2015</td>
      <td>Java Developer</td>
      <td>NASDAQ OMX Armenia OJSC</td>
      <td>NaN</td>
      <td>Full-time</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>Competitive</td>
      <td>Interested candidates can submit their CVs to:...</td>
      <td>25 December 2015</td>
      <td>24 January 2016</td>
      <td>NaN</td>
      <td>For more information please visit: www.nasdaqo...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18991</th>
      <td>NASDAQ OMX Armenia OJSC\r\n\r\n\r\nTITLE:  C/ ...</td>
      <td>Dec 24, 2015</td>
      <td>C/ C++ Developer</td>
      <td>NASDAQ OMX Armenia OJSC</td>
      <td>NaN</td>
      <td>Full-time</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>Competitive</td>
      <td>Interested candidates can submit their CVs to:...</td>
      <td>25 December 2015</td>
      <td>24 January 2016</td>
      <td>NaN</td>
      <td>For more information, please visit: www.nasdaq...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18992</th>
      <td>Macadamian AR CJSC\r\n\r\n\r\nTITLE:  .NET Dev...</td>
      <td>Dec 25, 2015</td>
      <td>.NET Developer</td>
      <td>Macadamian AR CJSC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>To apply for this position, please email your ...</td>
      <td>25 December 2015</td>
      <td>24 January 2016</td>
      <td>NaN</td>
      <td>Macadamian AR is a global software development...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18993</th>
      <td>"Coca-Cola Hellenic Bottling Company Armenia" ...</td>
      <td>Dec 25, 2015</td>
      <td>Recruitment Specialist</td>
      <td>"Coca-Cola Hellenic Bottling Company Armenia" ...</td>
      <td>NaN</td>
      <td>Full-time</td>
      <td>All interested candidates.</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>Long-term with a probation period of 3 months.</td>
      <td>...</td>
      <td>NaN</td>
      <td>All interested candidates are kindly requested...</td>
      <td>25 December 2015</td>
      <td>24 January 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18994</th>
      <td>"Coca-Cola Hellenic Bottling Company Armenia" ...</td>
      <td>Dec 25, 2015</td>
      <td>Capability Development Specialist</td>
      <td>"Coca-Cola Hellenic Bottling Company Armenia" ...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>All interested candidates.</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>Long-term with a probation period of 3 months.</td>
      <td>...</td>
      <td>NaN</td>
      <td>All interested candidates are kindly requested...</td>
      <td>25 December 2015</td>
      <td>24 January 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18995</th>
      <td>"Transport PIU" State Institution of the RA Mi...</td>
      <td>Dec 24, 2015</td>
      <td>Deputy Director</td>
      <td>"Transport PIU" State Institution of the RA Mi...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>All interested and qualified candidates.</td>
      <td>NaN</td>
      <td>As soon as possible.</td>
      <td>Long-term with a probation period of 3 months.</td>
      <td>...</td>
      <td>Commensurate with skills and experience.</td>
      <td>Interested candidates are asked to submit the\...</td>
      <td>25 December 2015</td>
      <td>24 January 2016, 17:00 p.m.</td>
      <td>NaN</td>
      <td>The "Transport PIU" SI (PIU) of the RA Ministr...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18996</th>
      <td>Technolinguistics NGO\r\n\r\n\r\nTITLE:  Senio...</td>
      <td>Dec 28, 2015</td>
      <td>Senior Creative UX/ UI Designer</td>
      <td>Technolinguistics NGO</td>
      <td>NaN</td>
      <td>Full-time</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Long-term</td>
      <td>...</td>
      <td>Competitive</td>
      <td>To apply for this position, please send your\r...</td>
      <td>29 December 2015</td>
      <td>28 January 2016</td>
      <td>NaN</td>
      <td>As a company Technolinguistics has a mandate t...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18997</th>
      <td>"Coca-Cola Hellenic Bottling Company Armenia" ...</td>
      <td>Dec 30, 2015</td>
      <td>Category Development Manager</td>
      <td>"Coca-Cola Hellenic Bottling Company Armenia" ...</td>
      <td>NaN</td>
      <td>Full-time</td>
      <td>All interested professionals.</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>Long-term with a probation period of 3 months.</td>
      <td>...</td>
      <td>NaN</td>
      <td>All interested candidates are kindly requested...</td>
      <td>30 December 2015</td>
      <td>20 January 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18998</th>
      <td>"Coca-Cola Hellenic Bottling Company Armenia" ...</td>
      <td>Dec 30, 2015</td>
      <td>Operational Marketing Manager</td>
      <td>"Coca-Cola Hellenic Bottling Company Armenia" ...</td>
      <td>NaN</td>
      <td>Full-time</td>
      <td>All interested professionals.</td>
      <td>NaN</td>
      <td>ASAP</td>
      <td>Long-term with a probation period of 3 months.</td>
      <td>...</td>
      <td>NaN</td>
      <td>All interested candidates are kindly requested...</td>
      <td>30 December 2015</td>
      <td>20 January 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18999</th>
      <td>San Lazzaro   LLC\r\n\r\n\r\nTITLE:  Head of O...</td>
      <td>Dec 30, 2015</td>
      <td>Head of Online Sales Department</td>
      <td>San Lazzaro   LLC</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Long-term</td>
      <td>...</td>
      <td>Highly competitive</td>
      <td>Interested candidates can send their CVs to:\r...</td>
      <td>30 December 2015</td>
      <td>29 January 2016</td>
      <td>NaN</td>
      <td>San Lazzaro LLC works with several internation...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>19000</th>
      <td>"Kamurj" UCO CJSC\r\n\r\n\r\nTITLE:  Lawyer in...</td>
      <td>Dec 30, 2015</td>
      <td>Lawyer in Legal Department</td>
      <td>"Kamurj" UCO CJSC</td>
      <td>NaN</td>
      <td>Full-time</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Indefinite</td>
      <td>...</td>
      <td>NaN</td>
      <td>All qualified applicants are encouraged to\r\n...</td>
      <td>30 December 2015</td>
      <td>20 January 2016</td>
      <td>NaN</td>
      <td>"Kamurj" UCO CJSC is providing micro and small...</td>
      <td>NaN</td>
      <td>2015</td>
      <td>12</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>19001 rows × 24 columns</p>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 19001 entries, 0 to 19000
    Data columns (total 24 columns):
    jobpost             19001 non-null object
    date                19001 non-null object
    Title               18973 non-null object
    Company             18994 non-null object
    AnnouncementCode    1208 non-null object
    Term                7676 non-null object
    Eligibility         4930 non-null object
    Audience            640 non-null object
    StartDate           9675 non-null object
    Duration            10798 non-null object
    Location            18969 non-null object
    JobDescription      15110 non-null object
    JobRequirment       16479 non-null object
    RequiredQual        18517 non-null object
    Salary              9623 non-null object
    ApplicationP        18941 non-null object
    OpeningDate         18295 non-null object
    Deadline            18936 non-null object
    Notes               2211 non-null object
    AboutC              12470 non-null object
    Attach              1559 non-null object
    Year                19001 non-null int64
    Month               19001 non-null int64
    IT                  19001 non-null bool
    dtypes: bool(1), int64(2), object(21)
    memory usage: 3.4+ MB


- Missing values (NaN)
- StartDate inconsistencies (ASAP)
- Fix nondescriptive column headers (ApplicationP, AboutC, RequiredQual ... and also JobRequirment)

## Clean
#### Define
- Select all nondescriptive and misspelled column headers (ApplicationP, AboutC, RequiredQual, JobRequirment) and replace them with full words (ApplicationProcedure, AboutCompany, RequiredQualifications, JobRequirement)
- Select all records in the StartDate column that have "As soon as possible", "Immediately", etc. and replace the text in those cells with "ASAP"

#### Code


```python
df_clean = df.copy()
```

- Select all nondescriptive and misspelled column headers (ApplicationP, AboutC, RequiredQual, JobRequirment) and replace them with full words (ApplicationProcedure, AboutCompany, RequiredQualifications, JobRequirement)


```python
df_clean = df_clean.rename(columns={'ApplicationP': 'ApplicationProcedure',
                                    'AboutC': 'AboutCompany',
                           
                                    'RequiredQual': 'RequiredQualifications',
                                    'JobRequirment': 'JobRequirements'})
```

- Select all records in the StartDate column that have "As soon as possible", "Immediately", etc. and replace the text in those cells with "ASAP"


```python
asap_list = ['Immediately', 'As soon as possible', 'Upon hiring',
             'Immediate', 'Immediate employment', 'As soon as possible.', 'Immediate job opportunity',
             '"Immediate employment, after passing the interview."',
             'ASAP preferred', 'Employment contract signature date',
             'Immediate employment opportunity', 'Immidiately', 'ASA',
             'Asap', '"The position is open immediately but has a flexible start date depending on the candidates earliest availability."',
             'Immediately upon agreement', '20 November 2014 or ASAP',
             'immediately', 'Immediatelly',
             '"Immediately upon selection or no later than November 15, 2009."',
             'Immediate job opening', 'Immediate hiring', 'Upon selection',
             'As soon as practical', 'Immadiate', 'As soon as posible',
             'Immediately with 2 months probation period',
             '12 November 2012 or ASAP', 'Immediate employment after passing the interview',
             'Immediately/ upon agreement', '01 September 2014 or ASAP',
             'Immediately or as per agreement', 'as soon as possible',
             'As soon as Possible', 'in the nearest future', 'immediate',
             '01 April 2014 or ASAP', 'Immidiatly', 'Urgent',
             'Immediate or earliest possible', 'Immediate hire',
             'Earliest  possible', 'ASAP with 3 months probation period.',
             'Immediate employment opportunity.', 'Immediate employment.',
             'Immidietly', 'Imminent', 'September 2014 or ASAP', 'Imediately']

for phrase in asap_list:
    df_clean.StartDate.replace(phrase, 'ASAP', inplace=True)
```

#### Test


```python
df_clean.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 19001 entries, 0 to 19000
    Data columns (total 24 columns):
    jobpost                   19001 non-null object
    date                      19001 non-null object
    Title                     18973 non-null object
    Company                   18994 non-null object
    AnnouncementCode          1208 non-null object
    Term                      7676 non-null object
    Eligibility               4930 non-null object
    Audience                  640 non-null object
    StartDate                 9675 non-null object
    Duration                  10798 non-null object
    Location                  18969 non-null object
    JobDescription            15110 non-null object
    JobRequirements           16479 non-null object
    RequiredQualifications    18517 non-null object
    Salary                    9623 non-null object
    ApplicationProcedure      18941 non-null object
    OpeningDate               18295 non-null object
    Deadline                  18936 non-null object
    Notes                     2211 non-null object
    AboutCompany              12470 non-null object
    Attach                    1559 non-null object
    Year                      19001 non-null int64
    Month                     19001 non-null int64
    IT                        19001 non-null bool
    dtypes: bool(1), int64(2), object(21)
    memory usage: 3.4+ MB



```python
df_clean.StartDate.value_counts()
```




    ASAP                                              6856
    01 September 2012                                   31
    March 2006                                          27
    November 2006                                       22
    January 2010                                        19
    February 2014                                       17
    01 February 2005                                    17
    February 2011                                       16
    September 2010                                      16
    TBD                                                 16
    March 2011                                          15
    September 2008                                      15
    February 2007                                       14
    01 February 2015                                    14
    01 July 2014                                        14
    01 March 2006                                       13
    01 September 2010                                   13
    01 September 2008                                   13
    January 2016                                        13
    01 April 2014                                       12
    01 October 2008                                     12
    September 2013                                      12
    01 October 2012                                     12
    01 March 2012                                       12
    June 2008                                           12
    Fall 2010                                           12
    01 April 2012                                       11
    01 September 2004                                   11
    01 February 2012                                    11
    January 2011                                        11
                                                      ... 
    10 May 2007                                          1
    20 November 2009                                     1
    Beginning of March 2006                              1
    07 May 2012                                          1
    20 May 2015                                          1
    The start period of trainings is mid November.       1
    08 April 2015                                        1
    28 July 2008                                         1
    08 October 2012                                      1
    30 October                                           1
    15 November 2004                                     1
    10 June 2006                                         1
    15 October 2014                                      1
    09 September 2013                                    1
    21 January 2010 to 25 June 2010                      1
    01 March  2009                                       1
    17 December 2012                                     1
    26 October 2011                                      1
    09 August 04                                         1
    September  2005                                      1
    28 March 2005                                        1
    15 February 2012                                     1
    08 June 2009                                         1
    03 November 2008                                     1
    09 April 2012                                        1
    23 May 2009, 18:00                                   1
    1 October 2007                                       1
    15 August 2011                                       1
    7 December 2007                                      1
    Mid-December 2007                                    1
    Name: StartDate, Length: 1140, dtype: int64




```python
for phrase in asap_list:
    assert phrase not in df_clean.StartDate.values
```

#### Visualisation


```python
# Number of 'ASAP' start date 
asap_counts= df_clean.StartDate.value_counts()['ASAP']
asap_counts
```




    6856




```python
# Number of non-empty start date
nonempty_counts= df_clean.StartDate.count()
nonempty_counts
```




    9675




```python
#Percentage of positions with an urgent start date 'ASAP'
asap_counts / nonempty_counts
```




    0.70863049095607233




```python
%matplotlib inline
import numpy as np
labels = np.full(len(df_clean.StartDate.value_counts())," ",dtype = object)
labels[0]='ASAP'
df_clean.StartDate.value_counts().plot(kind='pie',labels=labels)
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f2a899d1f28>




![png](output_22_1.png)



```python

```
