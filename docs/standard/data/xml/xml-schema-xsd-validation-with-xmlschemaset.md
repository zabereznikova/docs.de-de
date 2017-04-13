---
title: "Validierung eines XML-Schemas (XSD) mit &quot;XmlSchemaSet&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Validierung eines XML-Schemas (XSD) mit &quot;XmlSchemaSet&quot;
XML\-Dokumente können anhand eines XSD\-Schemas \(XML Schema Definition Language\) in einem <xref:System.Xml.Schema.XmlSchemaSet> validiert werden.  
  
## Validierung von XML\-Dokumenten  
 XML\-Dokumente werden von der <xref:System.Xml.XmlReader.Create%2A>\-Methode der <xref:System.Xml.XmlReader>\-Klasse validiert.  Wenn Sie ein XML\-Dokument validieren möchten, müssen Sie ein <xref:System.Xml.XmlReaderSettings>\-Objekt erstellen, das ein XSD\-Schema \(XML Schema Definition\) enthält, mit dem das XML\-Dokument validiert wird.  
  
> [!NOTE]
>  Der <xref:System.Xml.Schema>\-Namespace enthält Erweiterungsmethoden, die bei Verwendung von [LINQ to XML](../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md) ein einfaches Validieren einer XML\-Struktur anhand einer XSD\-Datei ermöglichen.  Weitere Informationen zum Validieren von XML\-Dokumenten mit LINQ to XML finden Sie unter [Vorgehensweise: Validieren mit XSD](../Topic/How%20to:%20Validate%20Using%20XSD%20\(LINQ%20to%20XML\).md).  
  
 Um einem <xref:System.Xml.Schema.XmlSchemaSet> ein einzelnes Schema oder mehrere Schemas \(als <xref:System.Xml.Schema.XmlSchemaSet>\) hinzuzufügen, muss eines von beiden als Parameter an die <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>\-Methode des <xref:System.Xml.Schema.XmlSchemaSet> übergeben werden.  Beachten Sie beim Validieren von Dokumenten, dass der Namespace des Dokuments dem Zielnamespace des Schemas im Schemasatz entsprechen muss.  
  
 Es folgt ein Beispiel für ein XML\-Dokument.  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 Im Folgenden wird das Schema dargestellt, das das XML\-Dokument validiert.  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 Im folgenden Codebeispiel wird das oben genannte Schema der <xref:System.Xml.Schema.XmlSchemaSet> <xref:System.Xml.XmlReaderSettings.Schemas%2A>\-Eigenschaft des <xref:System.Xml.XmlReaderSettings>\-Objekts hinzugefügt.  Das <xref:System.Xml.XmlReaderSettings>\-Objekt wird als Parameter an die <xref:System.Xml.XmlReader.Create%2A>\-Methode des <xref:System.Xml.XmlReader>\-Objekts übergeben, das das oben genannte XML\-Dokument validiert.  
  
 Die <xref:System.Xml.XmlReaderSettings.ValidationType%2A>\-Eigenschaft des <xref:System.Xml.XmlReaderSettings>\-Objekts wird auf `Schema` festgelegt, um die Validierung des XML\-Dokuments durch die <xref:System.Xml.XmlReader.Create%2A>\-Methode des <xref:System.Xml.XmlReader>\-Objekts zu erzwingen.  Dem <xref:System.Xml.XmlReaderSettings>\-Objekt wird ein <xref:System.Xml.Schema.ValidationEventHandler> hinzugefügt, der alle <xref:System.Xml.Schema.XmlSeverityType>\- oder <xref:System.Xml.Schema.XmlSeverityType>\-Ereignisse behandelt, die von während der Validierung des XML\-Dokuments und des Schemas gefundenen Fehlern ausgelöst werden.  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## Siehe auch  
 ["XmlSchemaSet" zur Kompilierung von Schemata](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)   
 [Arbeiten mit XML\-Schemata](../../../../docs/standard/data/xml/working-with-xml-schemas.md)