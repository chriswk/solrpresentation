<!SLIDE code smaller>
# Ruby query example #

    @@@ ruby

    solr = RSolr.connect :url => 'http://localhost:8983/solr'
    response = solr.get 'select', :params => {
    :q => '*:*',
    :sort => 'price asc'
    }
    response["response"]["docs"].each{|doc| puts doc["id"]}

