---
title: Verarbeiten von XML-Daten im Arbeitsspeicher
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec4ccbff095071b279e07cee6a1aab3ca830423f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="processing-xml-data-in-memory"></a>Verarbeiten von XML-Daten im Arbeitsspeicher
Microsoft .NET Framework enthält drei Modelle für die Verarbeitung von XML-Daten: die <xref:System.Xml.XmlDocument> -Klasse, die <xref:System.Xml.XPath.XPathDocument> -Klasse, und [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).  
  
 Die <xref:System.Xml.XmlDocument>-Klasse implementiert die W3C-Empfehlungen "Document Object Model Level 1" und "Document Object Model (DOM) Level 2 Core Specification". DOM ist eine Strukturdarstellung eines XML-Dokuments im Arbeitsspeicher (Cache). Mit dem <xref:System.Xml.XmlDocument> und seinen verwandten Klassen können Sie XML-Dokumente erstellen, Daten laden und auf diese zugreifen, Daten ändern und Änderungen speichern.  
  
 Die <xref:System.Xml.XPath.XPathDocument>-Klasse ist ein schreibgeschützter Datenspeicher im Arbeitsspeicher, der auf dem XPath-Datenmodell basiert. Die <xref:System.Xml.XPath.XPathNavigator>-Klasse bietet Optionen zur Bearbeitung und zum Navigieren mit einem Cursormodell in XML-Dokumenten, die in der schreibgeschützten <xref:System.Xml.XPath.XPathDocument>-Klasse oder in der <xref:System.Xml.XmlDocument>-Klasse enthalten sind.  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) ist das neue Modell in .NET Framework 3.5 zum Verarbeiten von XML-Daten. Es ist ein in-Memory-Modell, die nutzt [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d). LINQ erweitert die Sprachsyntax von C# und Visual Basic um neue Abfragefunktionen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verarbeiten von XML-Daten mithilfe des DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 Erläutert die Verwendung des <xref:System.Xml.XmlDocument> und seiner verwandten Klassen zur Verarbeitung von XML-Daten.  
  
 [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Erläutert die Verwendung der Klassen <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> und <xref:System.Xml.XPath.XPathNavigator> zur Verarbeitung von XML-Daten.  
  
 [Verarbeiten von XML-Daten mithilfe von LINQ to XML](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 Enthält eine kurze Übersicht über LINQ to XML sowie Links zur LINQ to XML-Dokumentation.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [XML-Dokumente und -Daten](../../../../docs/standard/data/xml/index.md)
