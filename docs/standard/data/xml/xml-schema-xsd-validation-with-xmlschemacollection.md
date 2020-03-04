---
title: XSD-Validierung (XML Schema) mit „XmlSchemaCollection“
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ad0b5717-3d32-41ad-a4d7-072c3e492b82
ms.openlocfilehash: 994153ba93848ebb120f23bdf6a979462a65142d
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159480"
---
# <a name="xml-schema-xsd-validation-with-xmlschemacollection"></a>XSD-Validierung (XML Schema) mit „XmlSchemaCollection“
Mit der <xref:System.Xml.Schema.XmlSchemaCollection> können XML-Dokumente anhand von XSD-Schemata (XML Schema Definition Language) validiert werden. Die <xref:System.Xml.Schema.XmlSchemaCollection> verbessert die Leistung, indem die Schemata in der Auflistung gespeichert werden, sodass sie nicht bei jeder Validierung erneut in den Speicher geladen werden müssen. Wenn das Schema in der Auflistung der Schemata enthalten ist, wird es mithilfe des `schemaLocation`-Attributs in der Auflistung gesucht.  
  
> [!IMPORTANT]
> Die <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse ist veraltet und wurde durch die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse ersetzt. Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaSet>-Klasse finden Sie unter [„XmlSchemaSet“ zur Kompilierung von Schemata](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
 Im folgenden Beispiel wird das Stammelement der Datendatei veranschaulicht.  
  
```xml  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:bookstore-schema"  
    elementFormDefault="qualified"  
    targetNamespace="urn:bookstore-schema">  
```  
  
 In diesem Beispiel lautet der Wert des `targetNamespace`-Attributs `urn:bookstore-schema`. Es wird also derselbe Namespace verwendet, der beim Hinzufügen des Schemas zur <xref:System.Xml.Schema.XmlSchemaCollection> verwendet wird.  
  
 Im folgenden Beispiel wird der <xref:System.Xml.Schema.XmlSchemaCollection> ein XML-Schema hinzugefügt.  
  
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
  
 Das `targetNamespace`-Attribut wird normalerweise verwendet, wenn in der `namespaceURI`-Methode die <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>-Eigenschaft für die <xref:System.Xml.Schema.XmlSchemaCollection> hinzugefügt wird. Sie können einen NULL-Verweis angeben, bevor Sie der <xref:System.Xml.Schema.XmlSchemaCollection> das Schema hinzufügen. Für Schemata ohne Namespace muss eine leere Zeichenfolge ("") verwendet werden. In der <xref:System.Xml.Schema.XmlSchemaCollection> kann nur ein Schema ohne Namespace enthalten sein.  
  
 Im folgenden Beispiel wird der <xref:System.Xml.Schema.XmlSchemaCollection> ein XML-Schema ({2}HeadCount.xsd{3}) hinzugefügt, und {4}HeadCount.xml{5} wird validiert.  
  
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
  
 Im folgenden Beispiel wird der Inhalt der zu validierenden Eingabedatei {1}HeadCount.xml{2} dargestellt.  
  
```xml  
<!--Load HeadCount.xsd in SchemaCollection for Validation-->  
<hc:HeadCount xmlns:hc='xsdHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</hc:HeadCount>  
```  
  
 Im folgenden Beispiel wird der Inhalt der XML-Schemadatei {1}HeadCount.xsd{2} dargestellt, die zur Validierung herangezogen wird.  
  
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
  
 Im folgenden Codebeispiel wird ein <xref:System.Xml.XmlValidatingReader> erstellt, der einen <xref:System.Xml.XmlTextReader> erfordert. Die Eingabedatei {1}sample4.xml{2} wird anhand des XML-Schemas {3}sample4.xsd{4} validiert.  
  
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
  
 Im folgenden Beispiel wird der Inhalt der zu validierenden Eingabedatei {1}sample4.xml{2} dargestellt.  
  
```xml  
<datatypes xmlns="datatypesTest">  
    <number>  
        <number_1>123</number_1>  
    </number>  
</datatypes>  
```  
  
 Im folgenden Beispiel wird der Inhalt der XML-Schemadatei {1}sample4.xsd{2} dargestellt, die zur Validierung herangezogen wird.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlParserContext>
- <xref:System.Xml.XmlValidatingReader.ValidationEventHandler?displayProperty=nameWithType>
- <xref:System.Xml.XmlValidatingReader.Schemas%2A?displayProperty=nameWithType>
- [Schemakompilierung mit „XmlSchemaCollection“](../../../../docs/standard/data/xml/xmlschemacollection-schema-compilation.md)
