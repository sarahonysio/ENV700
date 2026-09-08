# USGS Streamflow data for site 02085000


## Summary
This dataset was prepared for Environmental Data Analytics (ENV 700) at Duke University

The dataset contains streamflow data from the USGS streamflow gage site 02085000 (Eno River at Hillsborough, NC). 

## Database Information
Data were collected from the U.S. Geological Survey's Water Services website. More information can be found here: https://waterservices.usgs.gov/

> NOTE: This site will be decommissioned in early 2027. Access to and format of the data will change at that time, with future access done via the `dataRetrieval` package. 
>
> The `dataRetrieval` code to extract these will be:
>
> ```text
> outputData <- readNWISdata(sites = "02085000",
>                     startDT = "1928-01-01",
>                     endDT = "2025-12-31",
>                     siteStatus = "all",
>                     service="dv")
> ```

Data were collected using the Daily Values Service on the USGS Water Services website [link](https://waterservices.usgs.gov/test-tools/?service=dv&siteType=&statTypeCd=all&major-filters=sites&format=json&date-type=type-none&statReportType=daily&statYearType=calendar&missingData=off&siteStatus=all&siteNameMatchOperator=start).
From the Daily Values homepage, the following selections were made: 

* Select Service to Test: `Daily Values Service`
* Select a Major Filter: Site or Sites = `02085000`
* Output format: `USGS RDB (tab-delimited) format`
* Date Ranges
  * Range Values: `Return all values within an absolute date range (start and end dates)`
  * Start Date: `01/01/1928`
  * End Date: <blank>

The generated URL is:  
<https://waterservices.usgs.gov/nwis/dv/?format=rdb&sites=02085000&startDT=1928-01-01&siteStatus=all>

CSV file was saved as `USGS_Site02085000_Flow_Raw.csv`. 

Data were accessed 2026-06-11.

## Data Content Information 
Gathered from waterdata.usgs.gov:
---------------------------------- WARNING ----------------------------------------

Some of the data that you have obtained from this U.S. Geological Survey database may not have received Director's approval.  Any such data values are qualified as provisional and are subject to revision.  Provisional data are released on the condition that neither the USGS nor the United States Government may be held liable for any damages resulting from its use. Go to http://help.waterdata.usgs.gov/policies/provisional-data-statement for more information.

File-format description:  http://help.waterdata.usgs.gov/faq/about-tab-delimited-output
Automated-retrieval info: http://help.waterdata.usgs.gov/faq/automated-retrievals

Contact:   gs-w_support_nwisweb@usgs.gov
retrieved: 2026-06-11 06:06:59 -04:00	(natwebvaas01)

Data for the following 1 site(s) are contained in this file
   USGS 02085000 ENO RIVER AT HILLSBOROUGH, NC

TS_ID - An internal number representing a time series.
IV_TS_ID - An internal number representing the Instantaneous Value time series from which the daily statistic is calculated.

Data provided for site 02085000

TS_ID       Parameter    Statistic  IV_TS_ID       Description
165986      00060        00001      89054          Discharge, cubic feet per second (Maximum)
165987      00060        00002      89054          Discharge, cubic feet per second (Minimum)
84936       00060        00003      89054          Discharge, cubic feet per second (Mean)
84937       00065        00001      89055          Gage height, feet (Maximum)
84938       00065        00002      89055          Gage height, feet (Minimum)
84939       00065        00003      89055          Gage height, feet (Mean)

Data-value qualification codes included in this output:
   A  Approved for publication -- Processing and review completed.
   e  Value has been estimated.
   P  Provisional data subject to revision.

## Additional Information and Support
For more information, please contact the data assembler, **John Fay** (john.fay@duke.edu)