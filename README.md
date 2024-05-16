# Ironhack-Project-2
In this project we have an A/B test that was set into motion from 3/15/2017 to 6/20/2017 by the team.

Files like CSV and TXT saved in Raw Data File.
Notebooks saved in Notebooks File.

Tableau if the main result of our work.

Control Group: Clients interacted with Vanguard’s traditional online process.
Test Group: Clients experienced the new, spruced-up digital interface.
Both groups navigated through an identical process sequence: an initial page, three subsequent steps, and finally, a confirmation page signaling process completion.

The goal is to see if the new design leads to a better user experience and higher process completion rates.

We had three main TXT files we had to import into python and then convert to a CSV.
Client Profiles (df_final_demo): Demographics like age, gender, and account details of our clients.
Digital Footprints (df_final_web_data): A detailed trace of client interactions online, divided into two parts: pt_1 and pt_2. It’s recommended to concat these two files prior to a comprehensive data analysis and delete duplicated rows. 
Experiment Roster (df_final_experiment_clients): A list revealing which clients were part of the grand experiment.

Contents of Raw data files:

df_final_demo.txt  => Raw data of the clients (client_id, age, tenure, balance of all their accounts, etc.)

df_final_web_data_pt_1.txt => client behaviour on the webpage 3/15/2017 - around have way through of the time line (client behaviour in the webpage)
df_final_web_data_pt_2.txt => rest of the time line

df_final_experiment_clients.txt => Shows which client_id belongs to the Control group and which belongs to the Test group.

df_final_experiment_clients_cleaned.csv => Shows cleanes Control and Test

df_final_demo_cleaned.csv => Shows cleaned data of clients

df_final_web_concat.csv => Concatenated and cleaned data of client behaviour on the webpage

df_merged_sorted.csv => sorted the client behaviour by date merging it with Control Test on client_id

EVERYTHING_MERGED.csv => merged all information on client_id of df_final_demo_cleaned.

Contents of Notebook files: 

checks which clients where test subject and which were control.ipynb => cleans and removed clients with null values and turned txt file into a CSV

cleaning and combining the different text 1 and text 2.ipynb => cleaned and concatenated part1 and part2 making sure we got all of the client behavirous together (there were like around 5600 there were like some cliend_id that had some actions in part 1 and the rest part 2 if we use the function merge 'inner' on 'cliend_id' we would have lost 54.500 clients hence why concatenation was very important and removing duplicated rows.) then saved as a csv file

cleaning the final_demo_df.ipynb => cleanded some cliend_id that had no data in any of their respective columns 7402828, 355337, 8412164, 4666211, 2222915, 4876926, 5277910, 7616759, 8191345, 1227228, 8611797, 5144725, 1037867, 1618749, 6021001 filled some null values with the mean of data results. 

concat test.ipynb => Here we have most of the information. A graph to display the number of per steps taken by clients in Control and Test. Testing by which column we should group by the clients and their behaviour. Finally we came to the conclusion to group them by client_id and visit_id (since several clients share the same visit_id)
FOR CONTEXT
Metadata
client_id: Every client’s unique ID.
variation: Indicates if a client was part of the experiment.
visitor_id: A unique ID for each client-device combination.
visit_id: A unique ID for each web visit/session.
process_step: Marks each step in the digital process.
date_time: Timestamp of each web activity.
clnt_tenure_yr: Represents how long the client has been with Vanguard, measured in years.
clnt_tenure_mnth: Further breaks down the client’s tenure with Vanguard in months.
clnt_age: Indicates the age of the client.
gendr: Specifies the client’s gender.
num_accts: Denotes the number of accounts the client holds with Vanguard.
bal: Gives the total balance spread across all accounts for a particular client.
calls_6_mnth: Records the number of times the client reached out over a call in the past six months.
logons_6_mnth: Reflects the frequency with which the client logged onto Vanguard’s platform over the last six months.

Most of our analysis is based on the grouped by Visit_id and client_id sorted by TIME to have as accurately as possible analysis of everything. 
KPI that were analysed 
Here we have the average time spent on each step.
The error rate per step
The error rate in total. 
The completion rate. 
Hipothesis testing as well.

In tableau everything has been prettyfied and made is as dinamic as possible.