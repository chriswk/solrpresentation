<!SLIDE smbullets incremental>
# Replication #

* Master / Slave setup
* Easy setup. <10 lines for each replicator
* Secondary masters also possible

<!SLIDE code smaller>
# Master xml #

    @@@ xml
    <requestHandler name="/replication" class="solr.ReplicationHandler">
        <lst name="master">
            <str name="replicateAfter">startup</str>
            <str name="replicateAfter">commit</str>
            <str name="confFiles">schema.xml,stopwords.txt</str>
        </lst>
    </requestHandler>

<!SLIDE code smaller>
# Slave xml #

    @@@ xml
    <requestHandler name="/replication" class="solr.ReplicationHandler">
        <lst name="slave">
            <str name="masterUrl">http://${solr.master.address:localhost}:${solr.master.port:8983}/solr/replication</str>
            <str name="pollInterval">00:00:60</str>
        </lst>
    </requestHandler>


