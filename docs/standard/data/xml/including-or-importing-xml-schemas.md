---
title: Einfügen oder Importieren von XML-Schemata
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fe1b4a11-37f4-4e1a-93c9-239f4fe736c0
ms.openlocfilehash: d9a18876d8a5ba3067aa35c617b1e20fce0411f5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710777"
---
# <a name="including-or-importing-xml-schemas"></a>Einfügen oder Importieren von XML-Schemata
Ein XML-Schema kann die Elemente `<xs:import />`, `<xs:include />` und `<xs:redefine />` enthalten. Diese Schemaelemente verweisen auf andere XML-Schemata, mit denen die Struktur des Schemas ergänzt werden kann, in das Sie eingefügt bzw. importiert werden. Im SOM-API (Schemaobjektmodell) werden die Klassen <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> und <xref:System.Xml.Schema.XmlSchemaRedefine> diesen Elementen zugeordnet.  
  
## <a name="including-or-importing-an-xml-schema"></a>Einfügen oder Importieren eines XML-Schemas  
 Das folgende Codebeispiel ergänzt das im Thema [Erstellen von XML-Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) erstellte Kundenschema mit dem Adressschema. Wenn das Kundenschema mit dem Adressschema ergänzt wird, werden Adresstypen im Kundenschema verfügbar.  
  
 Das Adressschema kann mithilfe des `<xs:include />`-Elements oder des `<xs:import />`-Elements eingebunden werden, um Komponenten des Adressschemas im vorliegenden Zustand zu verwenden. Es kann auch mithilfe eines `<xs:redefine />`-Elements zum Ändern der Komponenten verwendet werden, um die Anforderungen des Kundenschemas zu erfüllen. Da das Adressschema einen `targetNamespace` aufweist, der sich von dem des Kundenschemas unterscheidet, wird Importsemantik in Form des `<xs:import />`-Elements verwendet.  
  
 Im Codebeispiel wird das Adressschema in den folgenden Schritten eingefügt.  
  
1. Fügt das Kundenschema und das Adressschema einem neuen <xref:System.Xml.Schema.XmlSchemaSet>-Objekt hinzu und kompiliert diese anschließend. Alle beim Lesen oder Kompilieren der Schemata aufgetretenen Schemavalidierungswarnungen und -fehler werden vom <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten behandelt.  
  
2. Ruft die kompilierten <xref:System.Xml.Schema.XmlSchema>-Objekte für die Kunden- und Adressschemata aus dem <xref:System.Xml.Schema.XmlSchemaSet> ab, indem die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft durchlaufen wird. Da die Schemata kompiliert sind, kann auf die Eigenschaften im Post-Schema-Compilation-Infoset (PSCI) zugegriffen werden.  
  
3. Erstellt ein <xref:System.Xml.Schema.XmlSchemaImport>-Objekt, legt die <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A>-Eigenschaft des Imports auf den Namespace des Adressschemas fest, legt die <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>-Eigenschaft des Imports auf das <xref:System.Xml.Schema.XmlSchema>-Objekt des Adressschemas fest, und fügt der <xref:System.Xml.Schema.XmlSchema.Includes%2A>-Eigenschaft des Kundenschemas den Import hinzu.  
  
4. Das geänderte <xref:System.Xml.Schema.XmlSchema>-Objekt des Kundenschemas wird mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode und der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse erneut verarbeitet, kompiliert und in die Konsole geschrieben.  
  
5. Schließlich werden alle in das Kundenschema importierten Schemata mithilfe der <xref:System.Xml.Schema.XmlSchema.Includes%2A>-Eigenschaft des Kundenschemas rekursiv in die Konsole geschrieben. Die <xref:System.Xml.Schema.XmlSchema.Includes%2A>-Eigenschaft bietet Zugriff auf alle einem Schema hinzugefügten Includes, Importe und Neudefinitionen.  
  
 Im Folgenden werden das gesamte Codebeispiel dargestellt und die Kunden- und Adressschemata auf der Konsole ausgegeben.  
  
 [!code-cpp[XmlSchemaImportExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaImportExample/CPP/XmlSchemaImportExample.cpp#1)]
 [!code-csharp[XmlSchemaImportExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaImportExample/CS/XmlSchemaImportExample.cs#1)]
 [!code-vb[XmlSchemaImportExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaImportExample/VB/XmlSchemaImportExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://www.example.com/IPO" />  
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
<schema targetNamespace="http://www.example.com/IPO" xmlns="http://www.w3.org/2001/XMLSchema" xmlns:ipo="http://www.example.com/IPO">  
  <annotation>  
    <documentation xml:lang="en">  
      Addresses for International Purchase order schema  
      Copyright 2000 Example.com. All rights reserved.  
    </documentation>  
  </annotation>  
  <complexType name="Address">  
    <sequence>  
      <element name="name"   type="string"/>  
      <element name="street" type="string"/>  
      <element name="city"   type="string"/>  
    </sequence>  
  </complexType>  
  <complexType name="USAddress">  
    <complexContent>  
      <extension base="ipo:Address">  
        <sequence>  
          <element name="state" type="ipo:USState"/>  
          <element name="zip"   type="positiveInteger"/>  
        </sequence>  
      </extension>  
    </complexContent>  
  </complexType>  
  <!-- other Address derivations for more countries or regions -->  
  <simpleType name="USState">  
    <restriction base="string">  
      <enumeration value="AK"/>  
      <enumeration value="AL"/>  
      <enumeration value="AR"/>  
      <!-- and so on ... -->  
    </restriction>  
  </simpleType>  
</schema>  
```  
  
 Weitere Informationen zu den Elementen `<xs:import />`, `<xs:include />` und `<xs:redefine />` sowie zu den Klassen <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> und <xref:System.Xml.Schema.XmlSchemaRedefine> finden Sie in den [W3C-XML-Schema-Spezifikationen](https://www.w3.org/XML/Schema) und in der Referenzdokumentation zur <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespaceklasse.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das XML-Schemaobjektmodell (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Lesen und Schreiben von XML-Schemas](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Erstellen von XML-Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Durchlaufen von XML-Schemas](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [Bearbeiten von XML-Schemas](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [„XmlSchemaSet“ zur Kompilierung von Schemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
