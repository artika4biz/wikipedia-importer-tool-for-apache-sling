# Wikipedia Importer Tool for Apache Sling and Adobe AEM
Tool to import Wikipedia dump file into Apache Sling or Adobe AEM repository.
This is a work-in-progress project. The basic idea is to createa multi-thread python application that extracts pages from a Wikipedia dump file to write data into an Apache Sling or Adobe AEM repository.
This tool is useful to load, stress and test scalability of Apache Jackrabbit OAK and Apache Sling, loading hundred of million of new nodes. After the import, the very large JCR repository is useful to study and learn how to administer Apache Jackrabbit OAK and Apache Sling. Finally, this project is useful for me, to understand if Jackrabbit OAK is a good platform to run AI/ML algorythms on structured and unstructured data.  
This is a fork of the original wikiextractor tool https://pypi.org/project/wikiextractor/ : I added just few lines of code (literally 6 or 7 lines) to write data into a Sling repository; all the magic is made by Apache Sling!
The Sling / AEM hostname, port and credentials are hard coded into the WikiExtractor.py file, line 490. I know, it's not elegant: one day I will remove any hard coded information and I also will remove not used/needed, original business logic (for examplet, to write articles into a file system, etc).

            requests.post('http://localhost:4502/data/it-wikipedia/' + d['id'] , auth=HTTPBasicAuth('admin', 'admin'), data=d)


# How to run this tool
1. Download the wikipedia dump of your choice, like this one: https://dumps.wikimedia.org/enwiki/latest/enwiki-latest-pages-articles.xml.bz2  (20gb zipped file, more than 70gb unzipped!)
2. Execute this command:
            python3 -m wikiextractor.WikiExtractor  /users/artika/Downloads/enwiki-latest-pages-articles.xml.bz2 --json   -ns article   --no-templates   -o - --processes 5  2>&1

This command line for example import all Wikipedia articles into a Sling/AEM instance, using 5 concurrent thread.






