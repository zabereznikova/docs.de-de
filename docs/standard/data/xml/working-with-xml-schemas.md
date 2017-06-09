---
title: "Arbeiten mit XML-Schemata | Microsoft Docs"
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
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Arbeiten mit XML-Schemata
Um die Struktur eines XML\-Dokuments sowie dessen Elementbeziehungen, Datentypen und Inhaltseinschränkungen anzugeben, verwenden Sie eine DTD \(Document Type Definition\) oder ein XSD\-Schema \(XML Schema Definition Language\).  Obwohl ein XML\-Dokument als wohlgeformt angesehen wird, wenn es alle syntaktischen Anforderungen erfüllt, die in der W3C\-Empfehlung \(World Wide Web Consortium\) "Extensible Markup Language \(XML\) 1.0" definiert sind, ist es nur dann gültig, wenn es sowohl wohlgeformt ist als auch den Einschränkungen der DTD oder des Schemas entspricht.  Das heißt, dass alle gültigen XML\-Dokumente wohlgeformt sind, jedoch nicht alle wohlgeformten XML\-Dokumente gültig sein müssen.  
  
 Weitere Informationen zu XML finden Sie unter der [W3C XML 1.0 Empfehlung](http://go.microsoft.com/fwlink/?linkid=7269).  Weitere Informationen zum XML\-Schema finden Sie in den Empfehlungen [W3C XML Schema Teil 1: Strukturen Empfehlung](http://go.microsoft.com/fwlink/?linkid=48881) und im [W3C XML Schema Teil 2: Datentypen](http://go.microsoft.com/fwlink/?linkid=17392).  
  
## In diesem Abschnitt  
 [XML\-Schemaobjektmodell \(SOM\)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 In diesem Abschnitt wird das Schema Object Model \(SOM\) im <xref:System.Xml.Schema?displayProperty=fullName>\-Namespace beschrieben, das eine Reihe von Klassen zur Verfügung stellt, mit denen Sie ein XSD\-Schema aus einer Datei lesen oder programmgesteuert im Speicher ein Schema erstellen können.  
  
 ["XmlSchemaSet" zur Kompilierung von Schemata](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 In diesem Abschnitt wird die <xref:System.Xml.Schema.XmlSchemaSet>\-Klasse beschrieben, die als Cache fungiert, in dem XSD\-Schemata gespeichert und validiert werden können.  
  
 [Pushbasierte Validierung mit "XmlSchemaValidator"](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 In diesem Abschnitt wird die <xref:System.Xml.Schema.XmlSchemaValidator>\-Klasse beschrieben, die eine effiziente leistungsstarke Methode zum Validieren von XML\-Daten anhand von XSD\-Schemata in einem Push\-Verfahren bereitstellt.  
  
 [Herleiten eines XML\-Schemas](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 In diesem Abschnitt wird das Verwenden der <xref:System.Xml.Schema.XmlSchemaInference>\-Klasse zum Herleiten eines XSD\-Schemas aus der Struktur eines XML\-Dokuments beschrieben.  
  
## Referenz  
 <xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader>  
  
## Verwandte Abschnitte  
 [Validieren eines XML\-Dokuments im Dokumentobjektmodell](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 In diesem Abschnitt wird das Validieren von XML im DOM \(Document Object Model\) beschrieben.  Sie können das XML beim Laden in das DOM validieren, oder Sie validieren ein zuvor nicht validiertes XML\-Dokument im DOM.  
  
 [Schema\-Validierung mithilfe von "XPathNavigator"](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 In diesem Abschnitt wird das Validieren von XML beschrieben, das mithilfe der <xref:System.Xml.XPath.XPathNavigator>\-Klasse durchsucht und bearbeitet wurde.