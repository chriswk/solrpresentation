<!SLIDE smbullets incremental>
# Key elements of schema.xml #

* Unique identifier
* Default search field
* Types
* Fields and Dynamic Fields
* Copy Fields

<!SLIDE code incremental smaller>

    @@@ xml
    <?xml version="1.0" encoding="UTF-8">
    <schema name="example" version="3.5">
        <uniqueKey>id</uniqueKey>
        <defaultSearchField>text</defaultSearchField>
        <solrQueryParser defaultOperator="OR" />
        <types>
        </types>
        <fields>
        </fields>
    </schema>

<!SLIDE smbullets incremental smaller>
# Types #

* Not going to say too much
* But custom types gives lots of power to SOLR
* PatternReplaceFilters
* Analyzers
* Indexing time
* Search time

<!SLIDE code smaller>

    @@@ xml
    <fieldType name="text_ws"
        class="solr.TextField"
        positionIncrementGap="100">
        <analyzer>
            <tokenizer class="solr.WhiteSpaceTokenizerFactory" />
        </analyzer>
    </fieldType>

<!SLIDE code smaller>

    @@@ xml
    <fieldType name="text_general" class="solr.TextField" positionIncrementGap="100">
        <analyzer type="index">
            <tokenizer class="solr.StandardTokenizerFactory" />
            <filter class="solr.StopFilterFactory" ignoreCase="true" words="stopwords.txt" enablePositionIncrements="true" />
            <filter class="solr.LowerCaseFilterFactory" />
        </analyzer>
        <analyzer type="search">

        </analyzer>
    </fieldType>


<!SLIDE smbullets incremental>
# Fields #

* Defines the fields solr knows about
* Only defines the outer boundaries
* A Document does not need to contain all fields defined
