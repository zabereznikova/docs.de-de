---
title: XSD-Validierung (XML Schema) mit „XmlSchemaCollection“
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ad0b5717-3d32-41ad-a4d7-072c3e492b82
ms.openlocfilehash: bd6bb440a00b3e485f4e6794e538f761267236b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733008"
---
# <a name="xml-schema-xsd-validation-with-xmlschemacollection"></a><span data-ttu-id="8201d-102">XSD-Validierung (XML Schema) mit „XmlSchemaCollection“</span><span class="sxs-lookup"><span data-stu-id="8201d-102">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>

<span data-ttu-id="8201d-103">Mit der <xref:System.Xml.Schema.XmlSchemaCollection> können XML-Dokumente anhand von XSD-Schemata (XML Schema Definition Language) validiert werden.</span><span class="sxs-lookup"><span data-stu-id="8201d-103">You can use the <xref:System.Xml.Schema.XmlSchemaCollection> to validate an XML document against XML Schema definition language (XSD) schemas.</span></span> <span data-ttu-id="8201d-104">Die <xref:System.Xml.Schema.XmlSchemaCollection> verbessert die Leistung, indem die Schemata in der Auflistung gespeichert werden, sodass sie nicht bei jeder Validierung erneut in den Speicher geladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8201d-104">The <xref:System.Xml.Schema.XmlSchemaCollection> improves performance by storing schemas in the collection so they are not loaded into memory each time validation occurs.</span></span> <span data-ttu-id="8201d-105">Wenn das Schema in der Auflistung der Schemata enthalten ist, wird es mithilfe des `schemaLocation`-Attributs in der Auflistung gesucht.</span><span class="sxs-lookup"><span data-stu-id="8201d-105">If the schema exists in the schema collection, the `schemaLocation` attribute is used to look up the schema in the collection.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8201d-106">Die <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse ist veraltet und wurde durch die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse ersetzt.</span><span class="sxs-lookup"><span data-stu-id="8201d-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="8201d-107">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaSet>-Klasse finden Sie unter [„XmlSchemaSet“ zur Kompilierung von Schemata](xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="8201d-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](xmlschemaset-for-schema-compilation.md).</span></span>  
  
 <span data-ttu-id="8201d-108">Im folgenden Beispiel wird das Stammelement der Datendatei veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8201d-108">The following example shows the root element of a data file.</span></span>  
  
```xml  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:bookstore-schema"  
    elementFormDefault="qualified"  
    targetNamespace="urn:bookstore-schema">  
```  
  
 <span data-ttu-id="8201d-109">In diesem Beispiel lautet der Wert des `targetNamespace`-Attributs `urn:bookstore-schema`. Es wird also derselbe Namespace verwendet, der beim Hinzufügen des Schemas zur <xref:System.Xml.Schema.XmlSchemaCollection> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8201d-109">For this example, the value of the `targetNamespace` attribute is `urn:bookstore-schema`, which is the same namespace that is used when adding the schema to the <xref:System.Xml.Schema.XmlSchemaCollection>.</span></span>  
  
 <span data-ttu-id="8201d-110">Im folgenden Beispiel wird der <xref:System.Xml.Schema.XmlSchemaCollection> ein XML-Schema hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8201d-110">The following code example adds an XML Schema to the <xref:System.Xml.Schema.XmlSchemaCollection>.</span></span>  
  
```vb  
Dim xsc As New XmlSchemaCollection()  
' XML Schema.  
xsc.Add("urn:bookstore-schema", schema)
reader = New XmlTextReader(filename)  
vreader = New XmlValidatingReader(reader)  
vreader.Schemas.Add(xsc)  
```  
  
```csharp  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
// XML Schema.  
xsc.Add("urn:bookstore-schema", schema);  
reader = new XmlTextReader (filename);  
vreader = new XmlValidatingReader (reader);  
vreader.Schemas.Add(xsc);  
```  
  
 <span data-ttu-id="8201d-111">Das `targetNamespace`-Attribut wird normalerweise verwendet, wenn in der `namespaceURI`-Methode die <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>-Eigenschaft für die <xref:System.Xml.Schema.XmlSchemaCollection> hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8201d-111">The `targetNamespace` attribute is generally used when you add the `namespaceURI` property in the <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> method for the <xref:System.Xml.Schema.XmlSchemaCollection>.</span></span> <span data-ttu-id="8201d-112">Sie können einen NULL-Verweis angeben, bevor Sie der <xref:System.Xml.Schema.XmlSchemaCollection> das Schema hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8201d-112">You can specify a null reference before adding the schema to the <xref:System.Xml.Schema.XmlSchemaCollection>.</span></span> <span data-ttu-id="8201d-113">Für Schemata ohne Namespace muss eine leere Zeichenfolge ("") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8201d-113">An empty string ("") should be used for schemas without a namespace.</span></span> <span data-ttu-id="8201d-114">In der <xref:System.Xml.Schema.XmlSchemaCollection> kann nur ein Schema ohne Namespace enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="8201d-114">The <xref:System.Xml.Schema.XmlSchemaCollection> can have only one schema without a namespace.</span></span>  
  
 <span data-ttu-id="8201d-115">Im folgenden Beispiel wird der <xref:System.Xml.Schema.XmlSchemaCollection> ein XML-Schema (HeadCount.xsd) hinzugefügt, und HeadCount.xml wird validiert.</span><span class="sxs-lookup"><span data-stu-id="8201d-115">The following code example adds an XML Schema, HeadCount.xsd, to the <xref:System.Xml.Schema.XmlSchemaCollection> and validates HeadCount.xml.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Schema  
  
Namespace ValidationSample  
  
   Class Sample  
  
      Public Shared Sub Main()  
         Dim tr As New XmlTextReader("HeadCount.xml")  
         Dim vr As New XmlValidatingReader(tr)  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd")  
         vr.ValidationType = ValidationType.Schema  
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler  
  
         While vr.Read()  
         End While  
         Console.WriteLine("Validation finished")  
      End Sub  
      ' Main  
  
      Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)  
         Console.WriteLine("***Validation error")  
         Console.WriteLine("Severity:{0}", args.Severity)  
         Console.WriteLine("Message:{0}", args.Message)  
      End Sub  
      ' ValidationHandler  
   End Class  
   ' Sample  
End Namespace  
' ValidationSample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Schema;  
  
namespace ValidationSample  
{  
   class Sample  
   {  
      public static void Main()  
      {  
         XmlTextReader tr = new XmlTextReader("HeadCount.xml");  
         XmlValidatingReader vr = new XmlValidatingReader(tr);  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd");  
         vr.ValidationType = ValidationType.Schema;  
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);  
  
         while(vr.Read());  
         Console.WriteLine("Validation finished");  
      }  
  
      public static void ValidationHandler(object sender, ValidationEventArgs args)  
      {  
         Console.WriteLine("***Validation error");  
         Console.WriteLine("\tSeverity:{0}", args.Severity);  
         Console.WriteLine("\tMessage  :{0}", args.Message);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="8201d-116">Im folgenden Beispiel wird der Inhalt der zu validierenden Eingabedatei HeadCount.xml dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8201d-116">The following outlines the contents of the input file, HeadCount.xml, to be validated.</span></span>  
  
```xml  
<!--Load HeadCount.xsd in SchemaCollection for Validation-->  
<hc:HeadCount xmlns:hc='xsdHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</hc:HeadCount>  
```  
  
 <span data-ttu-id="8201d-117">Im folgenden Beispiel wird der Inhalt der XML-Schemadatei HeadCount.xsd dargestellt, die zur Validierung herangezogen wird.</span><span class="sxs-lookup"><span data-stu-id="8201d-117">The following outlines the contents of the XML Schema file, HeadCount.xsd, to be validated against.</span></span>  
  
```xml  
<xs:schema xmlns="xsdHeadCount" targetNamespace="xsdHeadCount" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name='HeadCount' type="HEADCOUNT"/>  
   <xs:complexType name="HEADCOUNT">  
      <xs:sequence>  
         <xs:element name='Name' type='xs:string' maxOccurs='unbounded'/>  
      </xs:sequence>  
      <xs:attribute name='division' type='xs:int' use='optional' default='8'/>  
   </xs:complexType>  
</xs:schema>  
```  
  
 <span data-ttu-id="8201d-118">Im folgenden Codebeispiel wird ein <xref:System.Xml.XmlValidatingReader> erstellt, der einen <xref:System.Xml.XmlTextReader> erfordert.</span><span class="sxs-lookup"><span data-stu-id="8201d-118">The following code example creates an <xref:System.Xml.XmlValidatingReader> that takes an <xref:System.Xml.XmlTextReader>.</span></span> <span data-ttu-id="8201d-119">Die Eingabedatei sample4.xml wird anhand des XML-Schemas sample4.xsd validiert.</span><span class="sxs-lookup"><span data-stu-id="8201d-119">The input file, sample4.xml, is validated against the XML Schema, sample4.xsd.</span></span>  
  
```vb  
Dim tr As New XmlTextReader("sample4.xml")  
Dim vr As New XmlValidatingReader(tr)  
vr.ValidationType = ValidationType.Schema  
vr.Schemas.Add("datatypesTest", "sample4.xsd")  
AddHandler vr.ValidationEventHandler, AddressOf ValidationCallBack  
While vr.Read()  
   Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name)  
End While  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("sample4.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
vr.ValidationType = ValidationType.Schema;  
        vr.Schemas.Add("datatypesTest", "sample4.xsd");  
vr.ValidationEventHandler += new ValidationEventHandler(ValidationCallBack);  
while(vr.Read()) {  
    Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name);  
    }  
```  
  
 <span data-ttu-id="8201d-120">Im folgenden Beispiel wird der Inhalt der zu validierenden Eingabedatei sample4.xml dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8201d-120">The following outlines the contents of the input file, sample4.xml, to be validated.</span></span>  
  
```xml  
<datatypes xmlns="datatypesTest">  
    <number>  
        <number_1>123</number_1>  
    </number>  
</datatypes>  
```  
  
 <span data-ttu-id="8201d-121">Im folgenden Beispiel wird der Inhalt der XML-Schemadatei sample4.xsd dargestellt, die zur Validierung herangezogen wird.</span><span class="sxs-lookup"><span data-stu-id="8201d-121">The following outlines the contents of the XML Schema file, sample4.xsd, to be validated against.</span></span>  
  
```xml  
<xs:schema
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
    xmlns:tns="datatypesTest"
    targetNamespace="datatypesTest"  
    elementFormDefault="qualified">  
  
<xs:element name = "datatypes">  
  <xs:complexType>  
    <xs:all>  
        <xs:element name="number">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="number_1" type="xs:decimal" maxOccurs="unbounded"/>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
    </xs:all>  
  </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8201d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8201d-122">See also</span></span>

- <xref:System.Xml.XmlParserContext>
- <xref:System.Xml.XmlValidatingReader.ValidationEventHandler?displayProperty=nameWithType>
- <xref:System.Xml.XmlValidatingReader.Schemas%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8201d-123">Schemakompilierung mit „XmlSchemaCollection“</span><span class="sxs-lookup"><span data-stu-id="8201d-123">XmlSchemaCollection Schema Compilation</span></span>](xmlschemacollection-schema-compilation.md)
