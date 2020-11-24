---
title: Erstellen von XML-Schemata
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 8a5ea56c-0140-4b51-8997-875ae6a8e0cb
ms.openlocfilehash: bb011a8b81d9808c7517ebc2517529af7c4b975a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819370"
---
# <a name="building-xml-schemas"></a>Erstellen von XML-Schemata
Die Klassen im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace werden den Strukturen zugeordnet, die in der XML-Schemaempfehlung des W3C (World Wide Web Consortium) definiert sind, und können zum speicherinternen Erstellen von XML-Schemata verwendet werden.  
  
## <a name="building-an-xml-schema"></a>Erstellen eines XML-Schemas  
 Im folgenden Codebeispiel wird mithilfe der SOM-API speicherintern ein Kunden-XML-Schema erstellt.  
  
### <a name="creating-element-and-attributes"></a>Erstellen von Elementen und Attributen  
 In den Codebeispielen werden die Kundenschemata von unten nach oben erstellt, wobei zuerst die untergeordneten Elemente und Attribute und die entsprechenden Typen erstellt werden, und dann die Elemente der obersten Ebene.  
  
 Im folgenden Codebeispiel werden das `FirstName`-Element und das `LastName`-Element sowie das `CustomerId`-Attribut des Kundenschemas mithilfe der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse und der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse des SOMs erstellt. Außer der <xref:System.Xml.Schema.XmlSchemaElement.Name%2A>-Eigenschaften der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse und der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse, die dem "name"-Attribut des `<xs:element />`-Elements und des `<xs:attribute />`-Elements in einem XML-Schema entsprechen, verfügen alle anderen im Schema zulässigen Attribute (`defaultValue`, `fixedValue`, `form` usw.) über entsprechende Eigenschaften in der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse und der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse.  
  
 [!code-cpp[XmlSchemaCreateExample#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#2)]
 [!code-csharp[XmlSchemaCreateExample#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#2)]
 [!code-vb[XmlSchemaCreateExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#2)]  
  
### <a name="creating-schema-types"></a>Erstellen von Schematypen  
 Der Inhalt von Elementen und Attributen wird von den jeweiligen Typen definiert. Zum Erstellen von Elementen und Attributen, deren Typen einem der integrierten Schematypen entsprechen, wird die <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A>-Eigenschaft der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse mithilfe der <xref:System.Xml.XmlQualifiedName>-Klasse mit dem entsprechenden qualifizierten Namen des integrierten Typs festgelegt. Zum Erstellen eines benutzerdefinierten Typs für Elemente und Attribute wird mithilfe der <xref:System.Xml.Schema.XmlSchemaSimpleType>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaComplexType>-Klasse ein neuer einfacher oder komplexer Typ erstellt.  
  
> [!NOTE]
> Zum Erstellen unbenannter einfacher oder komplexer Typen, die anonyme untergeordnete Elemente eines Elements oder Attributs sind (für Attribute gelten nur einfache Typen), legen Sie die <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A>-Eigenschaft der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse anstelle der <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A>-Eigenschaft der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse auf den unbenannten einfachen oder komplexen Typ fest.  
  
 Bei XML-Schemata können durch Einschränkung anonyme und benannte einfache Typen von anderen einfachen Typen (integriert oder benutzerdefiniert) abgeleitet werden. Außerdem können diese als Liste oder Union von anderen einfachen Typen erstellt werden. Mithilfe der <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>-Klasse wird ein einfacher Typ durch Einschränkung des integrierten `xs:string`-Typs erstellt. Sie können auch mit der <xref:System.Xml.Schema.XmlSchemaSimpleTypeList>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion>-Klasse Listentypen oder Union-Typen erstellen. Die <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType>-Eigenschaft gibt an, ob es sich um eine Einschränkung, eine Liste oder eine Union von einem einfachen Typ handelt.  
  
 Im folgenden Codebeispiel ist der Typ des `FirstName`-Elements der integrierte Typ `xs:string`. Der Typ des `LastName`-Elements ist ein benannter einfacher Typ, der eine Einschränkung des integrierten Typs `xs:string` mit einem Wert des `MaxLength`-Facets von 20 ist. Der Typ des `CustomerId`-Attributs ist der integrierte Typ `xs:positiveInteger`. Das `Customer`-Element ist ein anonymer komplexer Typ, dessen Partikel eine Sequenz des `FirstName`-Elements und des `LastName`-Elements ist und dessen Attribute das `CustomerId`-Attribut enthalten.  
  
> [!NOTE]
> Die <xref:System.Xml.Schema.XmlSchemaChoice>-Klasse und die <xref:System.Xml.Schema.XmlSchemaAll>-Klasse können auch als Partikel des komplexen Typs zum Replizieren der `<xs:choice />`-Semantik oder der `<xs:all />`-Semantik verwendet werden.  
  
 [!code-cpp[XmlSchemaCreateExample#3](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#3)]
 [!code-csharp[XmlSchemaCreateExample#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#3)]
 [!code-vb[XmlSchemaCreateExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#3)]  
  
### <a name="creating-and-compiling-schemas"></a>Erstellen und Kompilieren von Schemata  
 Bisher wurden die untergeordneten Elemente und Attribute, deren jeweilige Typen und das `Customer`-Element der obersten Ebene speicherintern mithilfe der SOM-API erstellt. Im folgenden Codebeispiel wird das Schemaelement mithilfe der <xref:System.Xml.Schema.XmlSchema>-Klasse erstellt, diesem werden die Elemente und Typen der obersten Ebene mithilfe der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Eigenschaft hinzugefügt, und das gesamte Schema wird mithilfe der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse kompiliert und auf der Konsole ausgegeben.  
  
 [!code-cpp[XmlSchemaCreateExample#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#4)]
 [!code-csharp[XmlSchemaCreateExample#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#4)]
 [!code-vb[XmlSchemaCreateExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#4)]  
  
 Die <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType>-Methode validiert das Kundenschema anhand der Regeln für ein XML-Schema und macht Post-Schema-Compilation-Eigenschaften verfügbar.  
  
> [!NOTE]
> Alle Post-Schema-Compilation-Eigenschaften in der SOM-API weichen vom Post-Schema-Validation-Infoset ab.  
  
 Der dem <xref:System.Xml.Schema.ValidationEventHandler> hinzugefügte <xref:System.Xml.Schema.XmlSchemaSet> ist ein Delegat, der die Rückrufmethode `ValidationCallback` zum Behandeln der Schemavalidierungswarnungen und -fehler aufruft.  
  
 Im Folgenden wird das gesamte Codebeispiel dargestellt und das Kundenschema auf der Konsole ausgegeben.  
  
 [!code-cpp[XmlSchemaCreateExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#1)]
 [!code-csharp[XmlSchemaCreateExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#1)]
 [!code-vb[XmlSchemaCreateExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name="Customer">  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="FirstName" type="xs:string" />  
            <xs:element name="LastName" type="tns:LastNameType" />  
         </xs:sequence>  
         <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" />  
      </xs:complexType>  
   </xs:element>  
   <xs:simpleType name="LastNameType">  
      <xs:restriction base="xs:string">  
         <xs:maxLength value="20" />  
      </xs:restriction>  
   </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das XML-Schemaobjektmodell (SOM)](xml-schema-object-model-overview.md)
- [Lesen und Schreiben von XML-Schemas](reading-and-writing-xml-schemas.md)
- [Durchlaufen von XML-Schemas](traversing-xml-schemas.md)
- [Bearbeiten von XML-Schemas](editing-xml-schemas.md)
- [Einfügen oder Importieren von XML-Schemas](including-or-importing-xml-schemas.md)
- [„XmlSchemaSet“ zur Kompilierung von Schemas](xmlschemaset-for-schema-compilation.md)
- [Post-Schema-Compilation-Infoset](post-schema-compilation-infoset.md)
