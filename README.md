# Wikipedia Importer Tool for Apache Sling and Adobe AEM
Tool to import Wikipedia dump file into Apache Sling or Adobe AEM repository.
This is a work-in-progress project. The basic idea is to createa multi-thread python application that extracts pages from a Wikipedia dump file to write data into an Apache Sling or Adobe AEM repository.
This tool is useful to load, stress and test scalability of Apache Jackrabbit OAK and Apache Sling, loading hundred of million of new nodes. After the import the very large JCR repository is useful to study and learn how to administer Apache Jackrabbit OAK and Apache Sling. Finally, this project is useful for me, to understand if Jackrabbit OAK is a good platform to run AI/ML algorythms on structured and unstructured data.  
This is a fork of the original wikiextractor tool https://pypi.org/project/wikiextractor/
