<!SLIDE commandline incremental>
# curl #

    $ curl http://localhost:8983/solr/select?q=*:*&fl=*&wt=json
<!SLIDE code smaller>

    @@@ javascript
    {"responseHeader":
        {"status":0,
         "QTime":0,
         "params":
            {"fl":"*",
             "wt":"json",
             "q":"*:*",
             "rows":"1"
            }},
     "response":
        {"numFound":17,
         "start":0,
         "docs":[
            {"id":"GB18030TEST",
              "name":"Test with some GB18030 encoded characters",
              "price":0.0,
              "inStock":true,
              "features":["No accents here","这是一个功能","This is a feature (translated)","这份文件是很有光泽","This document is very shiny (translated)"]
            }
         ]
         }
    }


