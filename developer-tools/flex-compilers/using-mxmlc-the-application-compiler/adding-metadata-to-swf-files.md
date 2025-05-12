# Adding metadata to SWF files

The application compilers support adding metadata to SWF files. This metadata
can be used by search engines and other utilities to gather information about
the SWF file. This metadata represents a subset of the Dublin Core schema.

You can set the following values:

- `contributor`

- `creator`

- `date`

- `description`

- `language`

- `localized-description`

- `localized-title`

- `publisher`

- `title`

For the mxmlc command-line compiler, the default metadata settings in the
flex-config.xml file are as follows:

    <metadata>
        <title>Adobe Flex 4 Application</title>
        <description>http://www.adobe.com/products/flex</description>
        <publisher>unknown</publisher>
        <creator>unknown</creator>
        <language>EN</language>
    </metadata>

You can also set the metadata values as command-line options. The following
example sets some of the metadata values:

    mxmlc -language+=klingon -title "checkintest!"
        -localized-description "it r0x0rs" en-us
        -localized-description "c'est magnifique!" fr-fr
        -creator "Flexy Frank" -publisher "Franks Beans" flexstore.mxml

In this example, the following values are compiled into the resulting SWF file:

    <rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#'>
        <rdf:Description rdf:about='' xmlns:dc='http://purl.org/dc/elements/1.1'>
            <dc:format>application/x-shockwave-flash</dc:format>
            <dc:title>checkintest!</dc:title>
            <dc:description>
                <rdf:Alt>
                    <rdf:li xml:lang='fr-fr'>c'est magnifique!</rdf:li>
                    <rdf:li xml:lang='x-default'>http://www.adobe.com/products/flex</rdf:li>
                    <rdf:li xml:lang='en-us'>it r0x0rs</rdf:li>
                </rdf:Alt>
            </dc:description>
            <dc:publisher>Franks Beans</dc:publisher>
            <dc:creator>Flexy Frank</dc:creator>
            <dc:language>EN</dc:language>
            <dc:language>klingon</dc:language>
            <dc:date>Mar 16, 2010</dc:date>
        </rdf:Description>
    </rdf:RDF>

For information on the SWF file format, see the Flash File Format Specification,
which is available through the Player Licensing program.
