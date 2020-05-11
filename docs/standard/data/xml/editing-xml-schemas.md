---
title: Bearbeiten von XML-Schemata
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fa09c8e5-c2b9-49d2-bb0d-40330cd13e4d
ms.openlocfilehash: a295fee225d7eb5793b725db93e47fc73addf4ef
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794584"
---
# <a name="editing-xml-schemas"></a>Bearbeiten von XML-Schemata

Die Bearbeitung von XML-Schemata ist eines der wichtigsten Funktionen des Schemaobjektmodells (SOM). Alle Eigenschaften des SOM vor der Kompilierung des Schemas können zum Ändern der vorhandenen Werte eines XML-Schemas verwendet werden. Das XML-Schema kann dann erneut kompiliert werden, um die Änderungen widerzuspiegeln.

Der erste Bearbeitungsschritt eines in das DOM geladenen Schemas ist das Durchlaufen des Schemas. Sie sollten mit dem Durchlaufen eines Schemas mithilfe der SOM-API vertraut sein, bevor Sie versuchen, ein Schema zu bearbeiten. Sie sollten auch mit den Eigenschaften vor und nach der Kompilierung des Schemas im Post-Schema-Compilation-Infoset (PSCI) vertraut sein.

## <a name="editing-an-xml-schema"></a>Bearbeiten eines XML-Schemas

In diesem Abschnitt finden Sie zwei Codebeispiele, in denen das im Thema [Erstellen von XML-Schemata](../../../../docs/standard/data/xml/building-xml-schemas.md) erstellte Kundenschema bearbeitet wird. Im ersten Codebeispiel wird dem `PhoneNumber`-Element ein neues `Customer`-Element hinzugefügt, und im zweiten Codebeispiel wird dem `Title`-Element ein neues `FirstName`-Attribut hinzugefügt. Im ersten Beispiel wird die <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung nach der Kompilierung des Schemas zum Durchlaufen des Kundenschemas verwendet, während im zweiten Codebeispiel die <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas verwendet wird.

### <a name="phonenumber-element-example"></a>Beispiel: "PhoneNumber"-Element

Im ersten Codebeispiel wird dem `PhoneNumber`-Element des Kundenschemas ein neues `Customer`-Element hinzugefügt. Im Codebeispiel wird das Kundenschema in den folgenden Schritten bearbeitet.

1. Fügt das Kundenschema einem neuen <xref:System.Xml.Schema.XmlSchemaSet>-Objekt hinzu und kompiliert es anschließend. Alle beim Lesen oder Kompilieren des Schemas aufgetretenen Schemavalidierungswarnungen und -fehler werden vom <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten behandelt.

2. Ruft das kompilierte <xref:System.Xml.Schema.XmlSchema>-Objekt aus <xref:System.Xml.Schema.XmlSchemaSet> ab, indem die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft durchlaufen wird. Da das Schema kompiliert ist, kann auf die Eigenschaften im PSCI zugegriffen werden.

3. Erstellt mithilfe der `PhoneNumber`-Klasse das <xref:System.Xml.Schema.XmlSchemaElement>-Element und mithilfe der `xs:string`-Klasse und der <xref:System.Xml.Schema.XmlSchemaSimpleType>-Klasse die Einschränkung des einfachen <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>-Typs. Fügt außerdem der <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A>-Eigenschaft der Einschränkung ein pattern<xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A>-Facet hinzu, und fügt der <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A>-Eigenschaft des einfachen Typs die Einschränkung sowie dem `PhoneNumber` des -Elements den einfachen Typ hinzu.

4. Durchläuft jedes <xref:System.Xml.Schema.XmlSchemaElement> in der <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A>-Auflistung der <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung nach der Kompilierung des Schemas.

5. Ruft mithilfe der <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>-Klasse den komplexen Typ des `"Customer"`-Elements ab und mithilfe der `Customer`-Klasse den sequence<xref:System.Xml.Schema.XmlSchemaComplexType>-Partikel des komplexen Typs, wenn der <xref:System.Xml.Schema.XmlSchemaSequence> des Elements  ist.

6. Fügt der Sequenz mit dem vorhandenen `PhoneNumber`-Element und dem vorhandenen `FirstName`-Element mithilfe der `LastName`-Auflistung vor der Kompilierung des Schemas das neue <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A>-Element hinzu.

7. Schließlich wird das geänderte <xref:System.Xml.Schema.XmlSchema>-Objekt mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode und der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse erneut verarbeitet, kompiliert und in die Konsole geschrieben.

Nachfolgend ist das vollständige Codebeispiel angegeben.

[!code-cpp[XmlSchemaEditExample1#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample1/CPP/XmlSchemaEditExample1.cpp#1)]
[!code-csharp[XmlSchemaEditExample1#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample1/CS/XmlSchemaEditExample1.cs#1)]
[!code-vb[XmlSchemaEditExample1#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample1/VB/XmlSchemaEditExample1.vb#1)]

Im Folgenden finden Sie das geänderte Kundenschema, das im Thema [Erstellen von XML-Schemata](../../../../docs/standard/data/xml/building-xml-schemas.md) erstellt wurde.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="xs:string" />
        <xs:element name="LastName" type="tns:LastNameType" />
        <xs:element name="PhoneNumber">           <xs:simpleType>             <xs:restriction base="xs:string">               <xs:pattern value="\d{3}-\d{3}-\d(4)" />             </xs:restriction>           </xs:simpleType>         </xs:element>
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

### <a name="title-attribute-example"></a>Beispiel: "Title"-Attribut

Im zweiten Codebeispiel wird dem `Title`-Element des Kundenschemas ein neues `FirstName`-Attribut hinzugefügt. Im ersten Codebeispiel ist der Typ des `FirstName`-Elements `xs:string`. Da das `FirstName`-Element ein Attribut mit Zeichenfolgeninhalt enthalten soll, muss sein Typ mit einem Inhaltsmodell zur Erweiterung einfachen Inhalts in einen komplexen Typ geändert werden.

Im Codebeispiel wird das Kundenschema in den folgenden Schritten bearbeitet.

1. Fügt das Kundenschema einem neuen <xref:System.Xml.Schema.XmlSchemaSet>-Objekt hinzu und kompiliert es anschließend. Alle beim Lesen oder Kompilieren des Schemas aufgetretenen Schemavalidierungswarnungen und -fehler werden vom <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten behandelt.

2. Ruft das kompilierte <xref:System.Xml.Schema.XmlSchema>-Objekt aus <xref:System.Xml.Schema.XmlSchemaSet> ab, indem die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft durchlaufen wird. Da das Schema kompiliert ist, kann auf die Eigenschaften im PSCI zugegriffen werden.

3. Erstellt mithilfe der `FirstName`-Klasse einen neuen komplexen Typ für das <xref:System.Xml.Schema.XmlSchemaComplexType>-Element.

4. Erstellt mithilfe der `xs:string`-Klasse und der <xref:System.Xml.Schema.XmlSchemaSimpleContent>-Klasse eine neue Erweiterung für einfachen Inhalt mit dem Basistyp <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension>.

5. Erstellt mithilfe der `Title`-Klasse das neue <xref:System.Xml.Schema.XmlSchemaAttribute>-Attribut mit dem <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> von `xs:string`, und fügt der Erweiterung für einfachen Inhalt das Attribut hinzu.

6. Legt das Inhaltsmodell für einfachen Inhalt auf die Erweiterung für einfachen Inhalt und das Inhaltsmodell für den komplexen Typ auf den einfachen Inhalt fest.

7. Fügt der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas den neuen komplexen Typ hinzu.

8. Durchläuft alle <xref:System.Xml.Schema.XmlSchemaObject> in der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas.

> [!NOTE]
> Da das `FirstName`-Element in diesem Schema kein globales Element ist, ist es in der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung oder der <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung nicht verfügbar. Im Codebeispiel wird das `FirstName`-Element gefunden, indem zuerst nach dem `Customer`-Element gesucht wird.
>
> Im ersten Codebeispiel wird das Schema mithilfe der <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung nach der Kompilierung des Schemas durchlaufen. In diesem Beispiel wird das Schema mithilfe der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas durchlaufen. Während beide Auflistungen den Zugriff auf die globalen Elemente im Schema bereitstellen, ist das Durchlaufen der <xref:System.Xml.Schema.XmlSchema.Items%2A>-Auflistung zeitaufwendiger, da alle globalen Elemente im Schema durchlaufen werden müssen und das Schema keine PSCI-Eigenschaften aufweist. Die PSCI-Auflistungen (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType> usw.) bieten direkten Zugriff auf die globalen Elemente, Attribute und Typen mit den PSCI-Eigenschaften.

1. Ruft mithilfe der <xref:System.Xml.Schema.XmlSchemaObject>-Klasse den komplexen Typ des <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>-Elements ab sowie mithilfe der `"Customer"`-Klasse den sequence`Customer`-Partikel des komplexen Typs, wenn das <xref:System.Xml.Schema.XmlSchemaComplexType> ein Element ist, dessen <xref:System.Xml.Schema.XmlSchemaSequence> gleich  ist.

2. Durchläuft alle <xref:System.Xml.Schema.XmlSchemaParticle> in der <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas.

3. Legt den <xref:System.Xml.Schema.XmlSchemaParticle> des <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>-Elements auf den neuen komplexen `"FirstName"`-Typ fest, wenn <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> ein Element ist, dessen `FirstName` gleich `FirstName` ist.

4. Schließlich wird das geänderte <xref:System.Xml.Schema.XmlSchema>-Objekt mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode und der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse erneut verarbeitet, kompiliert und in die Konsole geschrieben.

Nachfolgend ist das vollständige Codebeispiel angegeben.

[!code-cpp[XmlSchemaEditExample2#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample2/CPP/XmlSchemaEditExample2.cpp#1)]
[!code-csharp[XmlSchemaEditExample2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample2/CS/XmlSchemaEditExample2.cs#1)]
[!code-vb[XmlSchemaEditExample2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample2/VB/XmlSchemaEditExample2.vb#1)]

Im Folgenden finden Sie das geänderte Kundenschema, das im Thema [Erstellen von XML-Schemata](../../../../docs/standard/data/xml/building-xml-schemas.md) erstellt wurde.

```xml
<?xml version="1.0" encoding=" utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="tns:FirstNameComplexType" />
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
  <xs:complexType name="FirstNameComplexType">     <xs:simpleContent>       <xs:extension base="xs:string">         <xs:attribute name="Title" type="xs:string" />       </xs:extension>     </xs:simpleContent>   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a>Siehe auch

- [Übersicht über das XML-Schemaobjektmodell (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Lesen und Schreiben von XML-Schemas](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Erstellen von XML-Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Durchlaufen von XML-Schemas](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [Einfügen oder Importieren von XML-Schemas](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [„XmlSchemaSet“ zur Kompilierung von Schemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Post-Schema-Compilation-Infoset](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
