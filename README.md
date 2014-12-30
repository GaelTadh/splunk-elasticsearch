splunk-elasticsearch
====================

I have created a small search command for Splunk which will allow you to search Elastic Search and display the results in the Splunk GUI


This project is now a valid splunk application and installs as you would any other splunk applications

Steps to use
Install python if it is not installed

Install ElasticSearch https://github.com/elasticsearch/elasticsearch-py
"pip install elasticsearch "

This project is now a Splunk Application so just copy the splunk-elasticsearch directory to your splunk $SPLUNK_HOME/etc/apps directory and should work


======================================================
git clone "This Project"
rsync -av splunk-elasticsearch $SPLUNK_HOME/etc/apps

Now you should be able to do a simple search like 
| esearch | top message

or 
| esearch oldest=now-100d earliest=now query="some text" index=nagios* limit=1000 field=message

================================================
<br>
command reference:<br>
esearch<br>
    oldest = default (now-1d)   uses elasticsearch timedate value or function<br>
    earliest = default (now)    uses elasticsearch timedate value or function<br>
    index    = default (*)      sepecify the elasticsearch index to search<br>
    limit    = default (50)     number of records to return<br>
    field    = default ("message")  which elasticsearch field to query and return the value<br>
    query    = default ("*" | might change this to match_all)   the elasticsearch query_string<br>
    


