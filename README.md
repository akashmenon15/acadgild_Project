# acadgild_Project
Music Data Anaylsis

Execution Steps : 

1) Copy the project and uzip it Move the entire directory structure to /home/acadgild

2) Run MySQL sudo service mysqld start

3) Make sure all the scripts in /home/acadgild/project/scripts have 774 permissions Run below command:

4) chmod 774 /home/acadgild/project/scripts/*

5) Run The Below Scripts:

  a) generate_web_data.py -- Generates some random data coming from web application

--> python /home/acadgild/project/scripts/generate_web_data.py

  b) generate_mob_data.py -- Generates some random data coming from mobile application

--> python /home/acadgild/project/scripts/generate_mob_data.py

  c) start-daemons.sh -- Launches all necessary daemons

--> sh /home/acadgild/project/scripts/start-daemons.sh

  d) create_hive_hbase_lookup.sh -- Creates hive table over HBase

--> sh /home/acadgild/project/scripts/create_hive_hbase_lookup.sh

  e) populate-lookup.sh -- Populates lookup tables

--> sh /home/acadgild/project/scripts/populate-lookup.sh

  f) dataformatting.sh -- Performs data formatting

--> sh /home/acadgild/project/scripts/dataformatting.sh

  g) data_enrichment.sh -- Performs data enrichment and cleaning

--> sh /home/acadgild/project/scripts/data_enrichment.sh

  h) data_analysis.sh -- Performs data analysis

--> sh /home/acadgild/project/scripts/data_analysis.sh

6) Scheduling:
We'll be using crontab for job scheduling. Job has to run every 3 hours

sudo crontab -e

(Press i to enter insert mode)

*/3 * * * /home/acadgild/project/scripts/wrapper.sh
(Press Esc and then type :wq! and press Enter)
