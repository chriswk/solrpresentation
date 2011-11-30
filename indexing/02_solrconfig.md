<!SLIDE smbullets smaller incremental>
# solrconfig.xml #

* Sets defaults for your search index
* Configures warmup searches for cache
* Cache settings
* Replication
* Update chains
* Query handlers
* Caching


<!SLIDE code smaller>
.notes Remember to comment on the directoryFactory and it's relevance, MMap, NIOFS, SimpleFS

    @@@ xml
    <config>
    <luceneMatchVersion>LUCENE_35</luceneMatchVersion>
    <dataDir><!-- Location of index files relative to contextpath --></dataDir>
    <directoryFactory />
    <indexDefaults>
        <useCompoundFile>false</useCompoundFile>
        <mergeFactor>10</mergeFactory>
        <ramBuffer />
    </indexDefaults>
    <jmx />
    <updateHandler class="solr.DirectUpdateHandler2">
    <query />
    </config>





