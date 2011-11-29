<!SLIDE code smaller>
# Java query example #

    @@@ java
    SolrServer solrServer = getSolrServer();
    // construct query
    SolrQuery query = new SolrQuery();
    query.setQuery("*.*");
    query.addSortField("price", SolrQuery.ORDER.asc);
    //Get query response
    QueryResponse rsp = solrServer.query(query);

    //Get documents
    SolrDocumentList docs = rsp.getResults();

