---
title: "XML-Verarbeitungsoptionen | Microsoft Docs"
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
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# XML-Verarbeitungsoptionen
Eine Liste der Microsoft\-Technologien zur Verarbeitung von XML\-Daten finden Sie in den folgenden Tabellen.  
  
## .NET Framework\-Optionen  
  
|**Option**|**Verarbeitungstyp**|**Beschreibung**|  
|----------------|--------------------------|----------------------|  
|[LINQ to XML](../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md) <br /> \(<xref:System.Xml.Linq>\-Namespace\)|Im Arbeitsspeicher|-   Basiert auf der Language Integrated Query \(LINQ\)\-Technologie in .NET Framework.<br />-   Erzielt eine Abfrageleistung, die mit der SQL\-Leistung für Objekte, relationale Daten und XML\-Daten vergleichbar ist.<br />-   Stellt Funktionen für die intuitive Erstellung und Transformation von Dokumenten bereit.<br />-   Verwenden Sie diese Option beim Schreiben von neuem Code.|  
|<xref:System.Xml.XmlReader?displayProperty=fullName>|Streambasiert|-   Stellt einen schnellen, nicht zwischengespeicherten Vorwärtszugriff auf XML\-Daten bereit.<br />-   Sie können Objekte mithilfe der <xref:System.Xml.XmlReader.Create%2A?displayProperty=fullName>\-Methode erstellen und die für das Objekt zu aktivierenden Funktionen mithilfe der <xref:System.Xml.XmlReaderSettings>\-Klasse angeben.|  
|<xref:System.Xml.XmlWriter?displayProperty=fullName>|Streambasiert|-   Stellt eine schnelle, nicht zwischengespeicherte Vorwärtsgenerierung von XML\-Daten bereit.<br />-   Sie können Objekte mithilfe der <xref:System.Xml.XmlWriter.Create%2A?displayProperty=fullName>\-Methode erstellen und die für das Objekt zu aktivierenden Funktionen mithilfe der <xref:System.Xml.XmlWriterSettings>\-Klasse angeben.|  
|<xref:System.Xml.XmlDocument?displayProperty=fullName>|Im Arbeitsspeicher|-   Implementiert die W3C\-Empfehlungen [Document Object Model \(DOM\) Level 1 Core](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) und [DOM Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/).<br />-   Zum Erstellen, Einfügen, Entfernen und Ändern von Knoten können Sie die Methoden und Eigenschaften verwenden, die auf dem vertrauten DOM\-Modell basieren.<br />-   Verwenden Sie diese Option zum Ändern vorhandenen Codes, der W3C DOM verwendet.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=fullName>|Im Arbeitsspeicher|-   Bietet über ein Cursormodell verschiedene Bearbeitungsoptionen und Navigationsfunktionen.<br />-   Die XML\-Dokumente können in einem <xref:System.Xml.XPath.XPathDocument>\-Objekt oder in einem <xref:System.Xml.XmlDocument>\-Objekt enthalten sein.<br />-   Gewährleistet exzellente Leistung für die schreibgeschützte XML\-Verarbeitung.<br />-   Verwenden Sie diese Option, wenn Sie vorhandenen Code mit XPath\-Abfragen oder XSLT\-Transformationen ändern.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|Im Arbeitsspeicher|-   Stellt Optionen zum Transformieren von XML\-Daten mithilfe von XSL\-Transformationen bereit.<br />-   Über [XSLT\-Compiler \(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md) können Sie auf vorkompilierte Transformationen in Ihrer App verweisen.|  
  
## Win32\- und COM\-basierte Optionen  
  
|**Option**|**Beschreibung**|  
|----------------|----------------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)|-   Ein schneller, sicherer XML\-Parser, der ohne Zwischenspeicherung in Vorwärtsrichtung arbeitet und mit dem Sie leistungsfähige XML\-Apps erstellen können.<br />-   Unterstützt jede Sprache, die Dynamic Link Librarys \(DLLs\) verwenden kann; wir empfehlen C\+\+.|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)|-   Eine COM\-basierte Technologie für die XML\-Verarbeitung im Windows\-Betriebssystem.<br />-   Stellt eine systemeigene DOM\-Implementierung mit Unterstützung für XPath und XSLT bereit.<br />-   Enthält den ereignisbasierten Parser SAX2.|  
  
## Siehe auch  
 [Verarbeiten von XML\-Daten mithilfe des DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)   
 [Verarbeiten von XML\-Daten mithilfe des XPath\-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [XSLT\-Compiler \(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)