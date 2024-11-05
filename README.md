# California community college board races data

Most of California’s 73 community college districts have board of trustee seats up for election on November 5, 2024. But over half of these races are canceled due to a  lack of opposition. In at least one case, Trustee Area 4 of the Mendocino-Lake Community College District, no candidates filed for the race.

CalMatters compiled the races and whether they were canceled into a database. Most of the information came from comparing two lists from individual counties:
- List of offices up for election
- List of qualified candidates

Most counties provide these lists on their election websites. In some cases, CalMatters contacted county election offices to clarify the status of races. This dataset does not include election results.

Each board trustee area may cover portions of one or more counties. Only counties with open board seats were included.

## Data Dictionary

### districts-races.csv

Each row refers to a community college district. The online-only district, which does not elect board seats, is excluded. 

<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>district</td>
      <td>Unique name of community college district. Matches the field with the same name in <code>districts-by-county-races.csv</code>
      </td>
    </tr>
    <tr>
      <td>counties</td>
      <td>Counties that the district serves, each separated by a semicolon if there are multiple. Some counties do not have elections for the district this cycle</td>
    </tr>
    <tr>
      <td>numColleges</td>
      <td>Integer number of colleges in the district</td>
    </tr>
    <tr>
      <td>numRacesOnBallot</td>
      <td>Integer number of seats that will be voted on</td>
    </tr>
    <tr>
      <td>numRacesCanceled</td>
      <td>Integer number of seats that will not be voted on</td>
    </tr>
    <tr>
      <td>linkBoard</td>
      <td>Link to district’s board of trustees webpage</td>
    </tr>
  </tbody>
</table>

### districts-by-county-races.csv

Each row refers to a combination of a community college district and a county it serves. For districts with races in multiple counties, there are multiple rows per district.

<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>district</td>
      <td>Name of community college district. Matches the field with the same name in <code>`districts-races.csv`</code>
      </td>
    </tr>
    <tr>
      <td>county</td>
      <td>Name of county the race(s) are occurring in</td>
    </tr>
    <tr>
      <td>racesOnBallot</td>
      <td>List of trustee seats up for election that are on the ballot. Some are labeled as a number (“Trustee Area 1”) and some as letters (“Trustee Area A”). If there are multiple districts, each area is separated by a semicolon (“1; 3”). A few districts do not elect by geographic area, so their areas are denoted with the number of seats (“at large (3)”). Blank if all races were canceled</td>
    </tr>
    <tr>
      <td>racesCanceled</td>
      <td>List of trustee seats up for election that were canceled. Some are labeled as a number (“Trustee Area 1”) and some as letters (“Trustee Area A”). If there are multiple districts, each area is separated by a semicolon (“1; 3”). A few districts do not elect by geographic area, so their areas are denoted with the number of seats (“at large (3)”). Blank if all races are on the ballot</td>
    </tr>
    <tr>
      <td>numRacesOnBallot</td>
      <td>Integer number of seats that will be voted on in the county. Corresponds with the length of the list in <code>racesOnBallot</code></td>
    </tr>
     <tr>
      <td>numRacesCanceled</td>
      <td>Integer number of seats that will not be voted on in the county. Corresponds with the length of the list in the <code>racesCanceled</code> field</td>
    </tr>
    <tr>
      <td>linkSource1</td>
      <td>Link to county list of offices up for election on November 5, 2024, when available. A source of information for this row</td>
    </tr>
    <tr>
      <td>linkSource2</td>
      <td>Link to county list of qualified candidates for election on November 5, 2024 or list of canceled races, when available. A source of information for this row</td>
    </tr>
  </tbody>
</table>

## Examples of Use

This dataset powers the lookup tool in this story: “[Culture wars start to roil elections for California’s community college trustees](https://calmatters.org/education/higher-education/2024/11/california-community-college-3/)” by Adam Echelman and Erica Yee (published November 4, 2024).

## Data Use

If you use this dataset, please mention it was collected and cleaned by CalMatters. If you have any questions about this dataset, feel free to contact erica@calmatters.org.

[CalMatters](https://calmatters.org/) is a nonpartisan, nonprofit journalism venture committed to explaining how California’s state Capitol works and why it matters.

