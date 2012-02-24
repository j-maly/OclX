OclX - XML validation library
=============================

By: Jakub Maly
email: jakub@maly.cz

OclX is a library of XSLT functions designed to check integrity constraints written in OCL in XML data. It can be used on its own, but is meant to support eXolutio project (http://eXolutio.com). Using eXolutio, you can model schemas in your XML application and add integrity constraints. The tool translates the integrity constraints into Schematron schemas, which can be validated when linked with OclX library. 

To use the library for schema validation 

1) generate a Schematron schema in eXolutio.
2) pass the schema to XProc pipeline that you can find in Pipeline/oclx-schematron-pipeline.xpl together with the validated document. 

OclX comes in two version 
 - dynamic 
 - functional

Dynamic version was tested with Saxon 9.3 and utilizes Saxon's dynamic evaluation extension functions(saxon:evaluate, see http://saxon.sourceforge.net/saxon7.9/extensions.html#evaluate).

Functional version was tested with Saxon 9.4, but should work with any XSLT 3.0 compliant processor. 

You can choose which version to use in validation by setting the corresponding option in oclx-schematron-pipeline.xpl. As an alternative to XProc, you can use the batch file, providing that your XSLT processor supports command line interface. You may have to modify the paths in the batch file to refer to your XSLT processor executable and check, whether the notation for arguments is correct (the batch file uses notation used by Saxon).  

You can look into Examples to see some examples of Schematron schemas that can be validated using OclX. The examples use functional version and you can test both schema-aware and non-schema-aware processing. In Calabash (see http://xmlcalabash.com/), schema-aware processing is triggered automatically, when the input document is provided with a schema. Note: in Saxon, schema-aware processing is supported only in Enterprise Edition. 