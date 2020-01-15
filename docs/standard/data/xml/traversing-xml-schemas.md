---
title: Durchlaufen von XML-Schemata
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: cce69574-5861-4a30-b730-2e18d915d8ee
ms.openlocfilehash: dbe02242f9bb8654e3f12d87b6ff6c2aea1f76b1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710114"
---
# <a name="traversing-xml-schemas"></a>Durchlaufen von XML-Schemata

Das Durchlaufen eines XML-Schemas mithilfe einer SOM-API (Schema Object Model) ermöglicht den Zugriff auf die im SOM gespeicherten Elemente, Attribute und Typen. Der erste Schritt beim Bearbeiten eines XML-Schemas mithilfe der SOM-API ist das Durchlaufen des im SOM geladenen XML-Schemas.

## <a name="traversing-an-xml-schema"></a>Durchlaufen eines XML-Schemas

Die folgenden Eigenschaften der <xref:System.Xml.Schema.XmlSchema>-Klasse ermöglichen einen Zugriff auf die Auflistung aller globalen Elemente, die dem XML-Schema hinzugefügt wurden.

|Die Eigenschaften-|Objekttyp, der in der Auflistung oder im Array gespeichert ist|
|--------------|---------------------------------------------------|
|<xref:System.Xml.Schema.XmlSchema.Elements%2A>|<xref:System.Xml.Schema.XmlSchemaElement>|
|<xref:System.Xml.Schema.XmlSchema.Attributes%2A>|<xref:System.Xml.Schema.XmlSchemaAttribute>|
|<xref:System.Xml.Schema.XmlSchema.AttributeGroups%2A>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|
|<xref:System.Xml.Schema.XmlSchema.Groups%2A>|<xref:System.Xml.Schema.XmlSchemaGroup>|
|<xref:System.Xml.Schema.XmlSchema.Includes%2A>|<xref:System.Xml.Schema.XmlSchemaExternal>, <xref:System.Xml.Schema.XmlSchemaInclude>, <xref:System.Xml.Schema.XmlSchemaImport> oder <xref:System.Xml.Schema.XmlSchemaRedefine>|
|<xref:System.Xml.Schema.XmlSchema.Items%2A>|<xref:System.Xml.Schema.XmlSchemaObject> (ermöglicht den Zugriff auf alle Elemente, Attribute und Typen auf globaler Ebene).|
|<xref:System.Xml.Schema.XmlSchema.Notations%2A>|<xref:System.Xml.Schema.XmlSchemaNotation>|
|<xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A>|<xref:System.Xml.Schema.XmlSchemaType>ist <xref:System.Xml.Schema.XmlSchemaSimpleType>ist <xref:System.Xml.Schema.XmlSchemaComplexType>|
|<xref:System.Xml.Schema.XmlSchema.UnhandledAttributes%2A>|<xref:System.Xml.XmlAttribute> (ermöglicht den Zugriff auf Attribute, die nicht zum Schemanamespace gehören)|

> [!NOTE]
> Alle in der obigen Tabelle aufgelisteten Eigenschaften (mit Ausnahme der <xref:System.Xml.Schema.XmlSchema.Items%2A>-Eigenschaft) sind PSCI-Eigenschaften (Post-Schema-Compilation-Infoset), die erst nach dem Kompilieren des Schemas zur Verfügung stehen. Die <xref:System.Xml.Schema.XmlSchema.Items%2A>-Eigenschaft ist eine Eigenschaft vor der Kompilierung des Schemas, mit der vor der Kompilierung des Schemas auf Elemente, Attribute und Typen auf globaler Ebene zugegriffen bzw. diese bearbeitet werden können.
>
> Die <xref:System.Xml.Schema.XmlSchema.UnhandledAttributes%2A>-Eigenschaft ermöglicht den Zugriff auf alle Attribute, die nicht zum Schemanamespace gehören. Diese Attribute werden bei der Schemaverarbeitung nicht verarbeitet.

Im folgenden Codebeispiel wird das Durchlaufen des Kundenschemas veranschaulicht, das im Thema [Erstellen von XML-Schemata](../../../../docs/standard/data/xml/building-xml-schemas.md) erstellt wurde. Im Codebeispiel werden das Durchlaufen des Schemas mithilfe der oben beschriebenen Auflistungen und das Schreiben aller Elemente und Attribute im Schema in die Konsole veranschaulicht.

Im Codebeispiel wird das Kundenschema in den folgenden Schritten durchlaufen.

1. Fügt das Kundenschema einem neuen <xref:System.Xml.Schema.XmlSchemaSet>-Objekt hinzu und kompiliert es anschließend. Alle beim Lesen oder Kompilieren des Schemas aufgetretenen Schemavalidierungswarnungen und -fehler werden vom <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten behandelt.

2. Ruft das kompilierte <xref:System.Xml.Schema.XmlSchema>-Objekt aus <xref:System.Xml.Schema.XmlSchemaSet> ab, indem die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft durchlaufen wird. Da das Schema kompiliert ist, kann auf die Eigenschaften im PSCI zugegriffen werden.

3. Durchläuft jedes <xref:System.Xml.Schema.XmlSchemaElement> in der <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A>-Auflistung der Post-Schema-Compilation-<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung. Dabei werden die Namen der einzelnen Elemente in die Konsole geschrieben.

4. Ruft den komplexen Typ des `Customer`-Elements mithilfe der <xref:System.Xml.Schema.XmlSchemaComplexType>-Klasse ab.

5. Wenn der komplexe Typ über Attribute verfügt, wird ein <xref:System.Collections.IDictionaryEnumerator> abgerufen, um jedes <xref:System.Xml.Schema.XmlSchemaAttribute> aufzuzählen und den Namen in die Konsole zu schreiben.

6. Ruft den <xref:System.Xml.Schema.XmlSchemaSequence> sequence-Partikel des komplexen Typs mithilfe der -Klasse ab.

7. Durchläuft jedes <xref:System.Xml.Schema.XmlSchemaElement> in der <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType>-Auflistung und schreibt die Namen der einzelnen untergeordneten Elemente in die Konsole.

Nachfolgend ist das vollständige Codebeispiel angegeben.

[!code-cpp[XmlSchemaTraverseExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaTraverseExample/CPP/XmlSchemaTraverseExample.cpp#1)]
[!code-csharp[XmlSchemaTraverseExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaTraverseExample/CS/XmlSchemaTraverseExample.cs#1)]
[!code-vb[XmlSchemaTraverseExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaTraverseExample/VB/XmlSchemaTraverseExample.vb#1)]

Die <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A?displayProperty=nameWithType>-Eigenschaft kann <xref:System.Xml.Schema.XmlSchemaSimpleType> oder <xref:System.Xml.Schema.XmlSchemaComplexType> sein, wenn es sich um einen benutzerdefinierten einfachen oder komplexen Typ handelt. Sie kann auch <xref:System.Xml.Schema.XmlSchemaDatatype> sein, wenn es sich um einen der integrierten Datentypen handelt, die in der XML-Schemaempfehlung des W3C definiert sind. Im Kundenschema ist der <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> des `Customer`-Elements <xref:System.Xml.Schema.XmlSchemaComplexType>, und das `FirstName`-Element und das `LastName`-Element sind <xref:System.Xml.Schema.XmlSchemaSimpleType>.

Im Codebeispiel im Thema [Erstellen von XML-Schemata](../../../../docs/standard/data/xml/building-xml-schemas.md) wurde mithilfe der <xref:System.Xml.Schema.XmlSchemaComplexType.Attributes%2A?displayProperty=nameWithType>-Auflistung dem `Customer`-Element das `CustomerId`-Attribut hinzugefügt. Es handelt sich dabei um eine Eigenschaft vor der Kompilierung des Schemas. Die zugehörige PSCI-Eigenschaft (Post-Schema-Validation Infoset) ist die <xref:System.Xml.Schema.XmlSchemaComplexType.AttributeUses%2A?displayProperty=nameWithType>-Auflistung, in der alle Attribute der komplexen Typen enthalten sind, einschließlich der durch Ableitung geerbten Attribute.

## <a name="see-also"></a>Siehe auch

- [Übersicht über das XML-Schemaobjektmodell (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Lesen und Schreiben von XML-Schemas](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Erstellen von XML-Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Bearbeiten von XML-Schemas](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [Einfügen oder Importieren von XML-Schemas](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [„XmlSchemaSet“ zur Kompilierung von Schemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Post-Schema-Compilation-Infoset](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
