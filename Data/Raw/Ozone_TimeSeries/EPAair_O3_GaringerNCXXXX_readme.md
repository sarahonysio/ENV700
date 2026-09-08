# EPA Air Time Series Data

This code downloads daily AQS Ozone data for a given year into a CSV file, repeating for a span of years.

Returns data summarized at the daily level. All daily summaries are  calculated on midnight to midnight basis in local time. Variables  returned include date, mean value, maximum value, etc. Data is at the  monitor level and may include more than one entry per monitor. There may be multiple entries for different (1) sample durations, (2) pollutant  standards. This notebook screens for data at the "`Ozone 8-hour 2015`" pollutant standard level for site `371190041` (Garinger School, near Charlotte, NC.)

- API Documentation: https://aqs.epa.gov/aqsweb/documents/data_api.html#daily
- Site ID = '371190041'

Data were accessed June 12 2026
 For more information contact John Fay (`john.fay@duke.edu`)

------



```python
# Packages
import requests
import pandas as pd

# Get the API Key
with open('EPA-AQS-key.txt','r') as the_file: aqs_key = the_file.readline()

# Set the base URL
the_url = 'https://aqs.epa.gov/data/api/dailyData/bySite'
params = {
    'email':'john.fay@duke.edu',
    'key':aqs_key,
    'param':'44201',
    'bdate':'20100101',
    'edate':'20101231',
    'state':'37',
    'county':'119',
    'site':'0041'
}

#Iterate through years and fetch dataframes
for the_year in range(2010,2026):

    #Update the bdate and edate parameters
    params['bdate'] = f'{the_year}0101'
    params['edate'] = f'{the_year}1231'

    #Fetch the data
    response = requests.get(the_url, params)

    #Convert to dataframe
    the_df = pd.DataFrame(response.json()['Data'])

    #Filter for pollutant_standard = Ozone 8-hour 2015
    the_df = the_df.query("pollutant_standard == 'Ozone 8-hour 2015'")

    #Write to file
    the_df.to_csv(f'Ozone_Timeseries/EPAair_O3_GaringerNC{the_year}_raw.csv',index=False)
```

