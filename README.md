
# Accessing Data within Pandas - Lab

## Introduction

In this lab, we'll look at a data set which contains information World cup matches. Let's use the pandas commands learned in the previous lecture to learn more about our data!

## Objectives
You will be able to:
* Understand and explain some key Pandas methods
* Access DataFrame data by using the label
* Perform boolean indexing on both Series and DataFrames
* Use simple selectors for series
* Set new Series and DataFrame inputs

## Load the data

Load the file `WorldCupMatches.csv` as a dataframe in Pandas


```python
import pandas as pd
```


```python
df = pd.read_csv('WorldCupMatches.csv')
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1930</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 1</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>France</td>
      <td>4</td>
      <td>1</td>
      <td>Mexico</td>
      <td></td>
      <td>4444.0</td>
      <td>3</td>
      <td>0</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>REGO Gilberto (BRA)</td>
      <td>201</td>
      <td>1096</td>
      <td>FRA</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1930</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 4</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>USA</td>
      <td>3</td>
      <td>0</td>
      <td>Belgium</td>
      <td></td>
      <td>18346.0</td>
      <td>2</td>
      <td>0</td>
      <td>MACIAS Jose (ARG)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>201</td>
      <td>1090</td>
      <td>USA</td>
      <td>BEL</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1930</td>
      <td>14 Jul 1930 - 12:45</td>
      <td>Group 2</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Yugoslavia</td>
      <td>2</td>
      <td>1</td>
      <td>Brazil</td>
      <td></td>
      <td>24059.0</td>
      <td>2</td>
      <td>0</td>
      <td>TEJADA Anibal (URU)</td>
      <td>VALLARINO Ricardo (URU)</td>
      <td>BALWAY Thomas (FRA)</td>
      <td>201</td>
      <td>1093</td>
      <td>YUG</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1930</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3</td>
      <td>1</td>
      <td>Peru</td>
      <td></td>
      <td>2549.0</td>
      <td>1</td>
      <td>0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201</td>
      <td>1098</td>
      <td>ROU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930</td>
      <td>15 Jul 1930 - 16:00</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Argentina</td>
      <td>1</td>
      <td>0</td>
      <td>France</td>
      <td></td>
      <td>23409.0</td>
      <td>0</td>
      <td>0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>RADULESCU Constantin (ROU)</td>
      <td>201</td>
      <td>1085</td>
      <td>ARG</td>
      <td>FRA</td>
    </tr>
  </tbody>
</table>
</div>



## Common methods and attributes

Use the correct method to look at the first 7 rows of the data set.


```python
df.head(7)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1930</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 1</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>France</td>
      <td>4</td>
      <td>1</td>
      <td>Mexico</td>
      <td></td>
      <td>4444.0</td>
      <td>3</td>
      <td>0</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>REGO Gilberto (BRA)</td>
      <td>201</td>
      <td>1096</td>
      <td>FRA</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1930</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 4</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>USA</td>
      <td>3</td>
      <td>0</td>
      <td>Belgium</td>
      <td></td>
      <td>18346.0</td>
      <td>2</td>
      <td>0</td>
      <td>MACIAS Jose (ARG)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>201</td>
      <td>1090</td>
      <td>USA</td>
      <td>BEL</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1930</td>
      <td>14 Jul 1930 - 12:45</td>
      <td>Group 2</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Yugoslavia</td>
      <td>2</td>
      <td>1</td>
      <td>Brazil</td>
      <td></td>
      <td>24059.0</td>
      <td>2</td>
      <td>0</td>
      <td>TEJADA Anibal (URU)</td>
      <td>VALLARINO Ricardo (URU)</td>
      <td>BALWAY Thomas (FRA)</td>
      <td>201</td>
      <td>1093</td>
      <td>YUG</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1930</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3</td>
      <td>1</td>
      <td>Peru</td>
      <td></td>
      <td>2549.0</td>
      <td>1</td>
      <td>0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201</td>
      <td>1098</td>
      <td>ROU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930</td>
      <td>15 Jul 1930 - 16:00</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Argentina</td>
      <td>1</td>
      <td>0</td>
      <td>France</td>
      <td></td>
      <td>23409.0</td>
      <td>0</td>
      <td>0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>RADULESCU Constantin (ROU)</td>
      <td>201</td>
      <td>1085</td>
      <td>ARG</td>
      <td>FRA</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1930</td>
      <td>16 Jul 1930 - 14:45</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Chile</td>
      <td>3</td>
      <td>0</td>
      <td>Mexico</td>
      <td></td>
      <td>9249.0</td>
      <td>1</td>
      <td>0</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>APHESTEGUY Martin (URU)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>201</td>
      <td>1095</td>
      <td>CHI</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1930</td>
      <td>17 Jul 1930 - 12:45</td>
      <td>Group 2</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Yugoslavia</td>
      <td>4</td>
      <td>0</td>
      <td>Bolivia</td>
      <td></td>
      <td>18306.0</td>
      <td>0</td>
      <td>0</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>201</td>
      <td>1092</td>
      <td>YUG</td>
      <td>BOL</td>
    </tr>
  </tbody>
</table>
</div>



Look at the last 3 rows of the data set.


```python
df.tail(3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>849</th>
      <td>2014</td>
      <td>09 Jul 2014 - 17:00</td>
      <td>Semi-finals</td>
      <td>Arena de Sao Paulo</td>
      <td>Sao Paulo</td>
      <td>Netherlands</td>
      <td>0</td>
      <td>0</td>
      <td>Argentina</td>
      <td>Argentina win on penalties (2 - 4)</td>
      <td>63267.0</td>
      <td>0</td>
      <td>0</td>
      <td>C�neyt �AKIR (TUR)</td>
      <td>DURAN Bahattin (TUR)</td>
      <td>ONGUN Tarik (TUR)</td>
      <td>255955</td>
      <td>300186490</td>
      <td>NED</td>
      <td>ARG</td>
    </tr>
    <tr>
      <th>850</th>
      <td>2014</td>
      <td>12 Jul 2014 - 17:00</td>
      <td>Play-off for third place</td>
      <td>Estadio Nacional</td>
      <td>Brasilia</td>
      <td>Brazil</td>
      <td>0</td>
      <td>3</td>
      <td>Netherlands</td>
      <td></td>
      <td>68034.0</td>
      <td>0</td>
      <td>2</td>
      <td>HAIMOUDI Djamel (ALG)</td>
      <td>ACHIK Redouane (MAR)</td>
      <td>ETCHIALI Abdelhak (ALG)</td>
      <td>255957</td>
      <td>300186502</td>
      <td>BRA</td>
      <td>NED</td>
    </tr>
    <tr>
      <th>851</th>
      <td>2014</td>
      <td>13 Jul 2014 - 16:00</td>
      <td>Final</td>
      <td>Estadio do Maracana</td>
      <td>Rio De Janeiro</td>
      <td>Germany</td>
      <td>1</td>
      <td>0</td>
      <td>Argentina</td>
      <td>Germany win after extra time</td>
      <td>74738.0</td>
      <td>0</td>
      <td>0</td>
      <td>Nicola RIZZOLI (ITA)</td>
      <td>Renato FAVERANI (ITA)</td>
      <td>Andrea STEFANI (ITA)</td>
      <td>255959</td>
      <td>300186501</td>
      <td>GER</td>
      <td>ARG</td>
    </tr>
  </tbody>
</table>
</div>



Get a concise summary of your data using `.info()`


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 852 entries, 0 to 851
    Data columns (total 20 columns):
    Year                    852 non-null int64
    Datetime                852 non-null object
    Stage                   852 non-null object
    Stadium                 852 non-null object
    City                    852 non-null object
    Home Team Name          852 non-null object
    Home Team Goals         852 non-null int64
    Away Team Goals         852 non-null int64
    Away Team Name          852 non-null object
    Win conditions          852 non-null object
    Attendance              850 non-null float64
    Half-time Home Goals    852 non-null int64
    Half-time Away Goals    852 non-null int64
    Referee                 852 non-null object
    Assistant 1             852 non-null object
    Assistant 2             852 non-null object
    RoundID                 852 non-null int64
    MatchID                 852 non-null int64
    Home Team Initials      852 non-null object
    Away Team Initials      852 non-null object
    dtypes: float64(1), int64(7), object(12)
    memory usage: 133.2+ KB


Obtain a tuple representing the number of rows and number of columns


```python
df.shape
```




    (852, 20)



Use the appropriate attribute to get the column names


```python
df.columns
```




    Index(['Year', 'Datetime', 'Stage', 'Stadium', 'City', 'Home Team Name',
           'Home Team Goals', 'Away Team Goals', 'Away Team Name',
           'Win conditions', 'Attendance', 'Half-time Home Goals',
           'Half-time Away Goals', 'Referee', 'Assistant 1', 'Assistant 2',
           'RoundID', 'MatchID', 'Home Team Initials', 'Away Team Initials'],
          dtype='object')



## Selecting dataframe information

When looking at the dataframe's `.head()`, you might have noticed that the games are structured chronologically in the dataframe.

Use the right selection method to print all the information from the 3rd to the 5th game.


```python
df.iloc[3:6]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>...</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
      <th>Half-time Goals</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>1930</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3</td>
      <td>1</td>
      <td>Peru</td>
      <td></td>
      <td>...</td>
      <td>1</td>
      <td>0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201</td>
      <td>1098</td>
      <td>ROU</td>
      <td>PER</td>
      <td></td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930</td>
      <td>15 Jul 1930 - 16:00</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Argentina</td>
      <td>1</td>
      <td>0</td>
      <td>France</td>
      <td></td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>RADULESCU Constantin (ROU)</td>
      <td>201</td>
      <td>1085</td>
      <td>ARG</td>
      <td>FRA</td>
      <td></td>
    </tr>
    <tr>
      <th>5</th>
      <td>1930</td>
      <td>16 Jul 1930 - 14:45</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Chile</td>
      <td>3</td>
      <td>0</td>
      <td>Mexico</td>
      <td></td>
      <td>...</td>
      <td>1</td>
      <td>0</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>APHESTEGUY Martin (URU)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>201</td>
      <td>1095</td>
      <td>CHI</td>
      <td>MEX</td>
      <td></td>
    </tr>
  </tbody>
</table>
<p>3 rows × 21 columns</p>
</div>



Now, print all the info from game 5-9, but we're only interested to print out the "Home Team Name" and the "Away Team Name", 


```python
df.loc[5:9, ['Home Team Name', 'Away Team Name']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Home Team Name</th>
      <th>Away Team Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>Chile</td>
      <td>Mexico</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Yugoslavia</td>
      <td>Bolivia</td>
    </tr>
    <tr>
      <th>7</th>
      <td>USA</td>
      <td>Paraguay</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Uruguay</td>
      <td>Peru</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Chile</td>
      <td>France</td>
    </tr>
  </tbody>
</table>
</div>



Next, we'd like the information on all the games played in Group 3 for the 1950 World Cup.


```python
df[(df["Year"] == 1950) & (df["Stage"]=="Group 3")]# df[df['Stage'] == 'Group 3']
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>...</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
      <th>Half-time Goals</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>56</th>
      <td>1950</td>
      <td>25 Jun 1950 - 15:00</td>
      <td>Group 3</td>
      <td>Pacaembu</td>
      <td>Sao Paulo</td>
      <td>Sweden</td>
      <td>3</td>
      <td>2</td>
      <td>Italy</td>
      <td></td>
      <td>...</td>
      <td>2</td>
      <td>1</td>
      <td>LUTZ Jean (SUI)</td>
      <td>BERANEK Alois (AUT)</td>
      <td>TEJADA Carlos (MEX)</td>
      <td>208</td>
      <td>1219</td>
      <td>SWE</td>
      <td>ITA</td>
      <td></td>
    </tr>
    <tr>
      <th>61</th>
      <td>1950</td>
      <td>29 Jun 1950 - 15:30</td>
      <td>Group 3</td>
      <td>Durival de Brito</td>
      <td>Curitiba</td>
      <td>Sweden</td>
      <td>2</td>
      <td>2</td>
      <td>Paraguay</td>
      <td></td>
      <td>...</td>
      <td>2</td>
      <td>1</td>
      <td>MITCHELL Robert (SCO)</td>
      <td>LEMESIC Leo (YUG)</td>
      <td>GARCIA Prudencio (USA)</td>
      <td>208</td>
      <td>1228</td>
      <td>SWE</td>
      <td>PAR</td>
      <td></td>
    </tr>
    <tr>
      <th>65</th>
      <td>1950</td>
      <td>02 Jul 1950 - 15:00</td>
      <td>Group 3</td>
      <td>Pacaembu</td>
      <td>Sao Paulo</td>
      <td>Italy</td>
      <td>2</td>
      <td>0</td>
      <td>Paraguay</td>
      <td></td>
      <td>...</td>
      <td>1</td>
      <td>0</td>
      <td>ELLIS Arthur (ENG)</td>
      <td>GARCIA Prudencio (USA)</td>
      <td>DE LA SALLE Charles (FRA)</td>
      <td>208</td>
      <td>1218</td>
      <td>ITA</td>
      <td>PAR</td>
      <td></td>
    </tr>
  </tbody>
</table>
<p>3 rows × 21 columns</p>
</div>



Let's repeat the command above, but now we only want to print out the attendance column for the Group 3 games

You can combine conditions like this:

`df[(condition1) | (condition2)]`  -> Returns rows where either condition is true

`df[(condition1) & (condition2)]`  -> Returns rows where both conditions are true


```python
df.loc[(df["Year"] == 1950) & (df["Stage"]=="Group 3"), "Attendance"]
```




    56    36502.0
    61     7903.0
    65    25811.0
    Name: Attendance, dtype: float64



Throughout the entire history of the world cup, How many Home games were played by the Netherlands?


```python
len(df[df["Home Team Name"] == 'Netherlands'])
```




    32



How many games were played by the Netherlands in total?


```python
len(df[ (df["Home Team Name"] == 'Netherlands') | (df["Away Team Name"] == 'Netherlands') ])
```




    54



Next, let's try and figure out how many games the USA played in the 2014 world cup. 


```python
len(df[((df['Home Team Name'] == 'USA') | (df['Away Team Name'] == 'USA') )  & (df['Year'] == 2014)])
```




    5



Now, let's try to find out how many countries participated in the 1986 world cup.

Hint 1: as a first step, create a new data set that only contain games in that year.

Hint 2: You can use `.unique()` to make sure you don't end up with duplicate country names.


```python
df_1 = df[df['Year'] == 1986]
home_team = list(df_1['Home Team Name'].unique())
away_team = list(df_1['Away Team Name'].unique())
home_team += away_team
len(set(home_team))
```




    24



In the world cup history, how matches had more than 5 goals in total?


```python
df['Total_Goals'] = df['Home Team Goals'] + df['Away Team Goals']
len(df[ df['Total_Goals'] >= 5 ])
```




    147



## Changing values and creating new columns

With the information you currently have in your `df`, create a new column "Half-time Goals".


```python
df['Half-time Goals'] = df['Half-time Home Goals'] + df['Half-time Away Goals']
```

Run the code below. You'll notice that for Korea, there are records for both North-Korea (Korea DPR) and South-Korea (Korea Republic). 


```python
df.loc[df["Home Team Name"].str.contains('Korea'), "Home Team Name" ]
```




    179         Korea DPR
    187         Korea DPR
    374    Korea Republic
    386    Korea Republic
    434    Korea Republic
    444    Korea Republic
    480    Korea Republic
    524    Korea Republic
    593    Korea Republic
    609    Korea Republic
    635    Korea Republic
    642    Korea Republic
    655    Korea Republic
    710    Korea Republic
    753         Korea DPR
    802    Korea Republic
    818    Korea Republic
    Name: Home Team Name, dtype: object



Imagine that for some reason, we simply want Korea listed as one entry, so we want to replace every "Home Team Name" and "Away Team Name" entry that contains "Korea" to simply "Korea". In the same way, we want to change the columns "Home Team Initials" and "Away Team Initials" to NSK (North & South Korea) instead of "KOR" and "PRK". 


```python
df.loc[df["Home Team Name"].str.contains('Korea'), "Home Team Name" ] = "Korea"
df.loc[df["Away Team Name"].str.contains('Korea'), "Away Team Name" ] = "Korea"
df.loc[df["Home Team Initials"].str.contains('KOR'), "Home Team Initials" ] = "NSK"
df.loc[df["Home Team Initials"].str.contains('PRK'), "Home Team Initials" ] = "NSK"
df.loc[df["Away Team Initials"].str.contains('KOR'), "Away Team Initials" ] = "NSK"
df.loc[df["Away Team Initials"].str.contains('PRK'), "Away Team Initials" ] = "NSK"
```

Make sure to verify your answer!


```python
df.loc[df["Home Team Name"].str.contains('Korea'), "Home Team Name" ]
```




    179    Korea
    187    Korea
    374    Korea
    386    Korea
    434    Korea
    444    Korea
    480    Korea
    524    Korea
    593    Korea
    609    Korea
    635    Korea
    642    Korea
    655    Korea
    710    Korea
    753    Korea
    802    Korea
    818    Korea
    Name: Home Team Name, dtype: object




```python
df.loc[df["Away Team Name"].str.contains('Korea'), "Away Team Name" ]
```




    80     Korea
    88     Korea
    171    Korea
    195    Korea
    364    Korea
    421    Korea
    464    Korea
    490    Korea
    542    Korea
    556    Korea
    625    Korea
    639    Korea
    640    Korea
    672    Korea
    691    Korea
    721    Korea
    725    Korea
    737    Korea
    742    Korea
    756    Korea
    788    Korea
    Name: Away Team Name, dtype: object




```python
df.loc[df["Away Team Initials"].str.contains('NSK'), "Away Team Initials" ]
```




    80     NSK
    88     NSK
    171    NSK
    195    NSK
    364    NSK
    421    NSK
    464    NSK
    490    NSK
    542    NSK
    556    NSK
    625    NSK
    639    NSK
    640    NSK
    672    NSK
    691    NSK
    721    NSK
    725    NSK
    737    NSK
    742    NSK
    756    NSK
    788    NSK
    Name: Away Team Initials, dtype: object




```python
df.loc[df["Home Team Initials"].str.contains('NSK'), "Home Team Initials" ]
```




    179    NSK
    187    NSK
    374    NSK
    386    NSK
    434    NSK
    444    NSK
    480    NSK
    524    NSK
    593    NSK
    609    NSK
    635    NSK
    642    NSK
    655    NSK
    710    NSK
    753    NSK
    802    NSK
    818    NSK
    Name: Home Team Initials, dtype: object




```python

```
