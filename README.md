# TemplateCoder
Java program to take an xsl template file and an xml input file to create an outfile file. This is used to program repetative code.
The motivation behind the program comes from having to write repetive code for a list of items that needs to be updated as the
list of items changes. As an example, a list of fields might produce the exact same code for each field when writing a GUI. By 
having a template approach, the code would be written once in the template file and then as the list of fields changes, the 
generated code could change without having to copy and paste. Conversly, if a bug is discovered in the template itself, the bug 
is changed in one place and the resulting code is simpy regenerated. This approach is well suited to GUI development, network protocol
handlers, database front ends and other patterns that use the same code structure for multiple items.

The gernal usage is:
  java -jar template_coder-7.1.0.jar xmlfile.xml xslfile.xsl outputfile.cpp 

  The exmaple would take a template file xslfile.xsl and apply the input xml file xmlfile.xml to generate the outputfile.cpp file.
 
The xml file needs is to be a well-formed xml document.  That is, all open tags must be followed by closing tags such as
<someelement>some text</someelement>, or have self-contained closing tags such as <someelement2/>. Namespaces and comments are
supported in the xml document. There is no restriction on the schema of the xml document other than what is expected in the xsl 
template file.
 
The xsl template file follows the standard xsl format where x-path expressions are used to pull data from the xml file. There are
several conviences supported in the xsl document that are used to make generating code a little easier.
