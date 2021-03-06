json2csv
========

Converts a stream of newline separated json data to csv format

    usage: json2csv
        -k fields,to,output
        -i /path/to/input.json (optional; default is stdin)
        -o /path/to/output.csv (optional; default is stdout)
        -v verbose output (to stderr)
        -h this help

To convert:

    {"login":"jehiah", "remote_ip": "127.0.0.1", "dt" : "[20/Aug/2010:01:12:44 -0400]"}
    {"login":"unknown", "remote_ip": "76.216.210.0", "dt" : "[20/Aug/2010:01:12:45 -0400]"}
    
to:

    "jehiah","127.0.0.1"
    "unknown","76.216.210.0"
    
you would either

    json2csv -k login,remote_ip -i input.json -o output.csv

or

    cat input.json | json2csv -k login,remote_ip > output.csv

Installation
============

json-c dependancy

    $ git clone git://github.com/jehiah/json-c.git
    $ cd json-c
    $ sh autogen.sh
    $ ./configure
    $ make
    $ make install

json2csv

    $ git clone git://github.com/jehiah/json2csv.git
    $ cd json2csv
    $ make
    $ make install
