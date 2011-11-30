<!SLIDE bullets incremental>
# Indexing #

* XML format
* Curl
* Java client
* Ruby etc

<!SLIDE code smaller>
# XML example #

    @@@ xml
    <add>
        <doc>
            <field name="id">3007WFP</field>
            <field name="name">Dell Widescreen UltraSharp 3007WFP</field>
            <field name="manu">Dell, Inc.</field>
            <field name="cat">electronics</field>
            <field name="cat">monitor</field>
            <field name="features">30" TFT active matrix LCD, 2560 x 1600, .25mm dot pitch, 700:1 contrast</field>
            <field name="includes">USB cable</field>
            <field name="weight">401.6</field>
            <field name="price">2199</field>
            <field name="popularity">6</field>
            <field name="inStock">true</field>
            <!-- Buffalo store -->
            <field name="store">43.17614,-90.57341</field>
        </doc>
    </add>

<!SLIDE commandline incremental smaller>
# CURL example #

    $ curl http://localhost:8983/solr/update?commit=true -H "Content-Type: text/xml" \
    --data-binary '<add><doc><field name="id">testdoc</field> \
    <field name="price">10.95</field></doc></add>'


<!SLIDE code smaller>
# Java example (SOLRJ) #

    @@@ java
    // Construct the document
    SolrInputDocument doc1 = new SolrInputDocument();
    doc1.add("id", 1);
    doc1.add("price", 10.5);
    // Get server
    SolrServer server = new CommonsHttpSolrServer("http://localhost:8983/solr/");
    server.add(doc1);
    server.commit();

<!SLIDE code smaller>
# Ruby #

    @@@ ruby
    require 'rsolr'

    solr = RSolr.connect :url => 'http://localhost:8983/solr/'
    //A Solr document is simply a hash
    solr.add :id => 1, :price => 10.5
    solr.commit


