---
title: XML-Verarbeitungsoptionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 18f8f9c76a1842517340eaa3f74b4778f869403e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-options"></a>XML-Verarbeitungsoptionen
Eine Liste der Microsoft-Technologien zur Verarbeitung von XML-Daten finden Sie in den folgenden Tabellen.  
  
## <a name="net-framework-options"></a>.NET Framework-Optionen  
  
|**Option**|**Verarbeitungstyp**|**Beschreibung**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) <br />(<xref:System.Xml.Linq>-Namespace)|Im Arbeitsspeicher|-Auf der Grundlage der Integrated Query (LINQ)-Technologie.<br />– Bietet Abfrageerlebnis, die für Objekte, relationale Daten und XML-Daten SQL ähnlich ist.<br />– Bietet für die intuitive Erstellung und Transformation von Dokumenten.<br />-Verwenden Sie diese Option aus, wenn Sie neuen Code schreiben.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|Streambasiert|– Bietet eine schnelle, nicht zwischengespeicherten, nur vorwärts Möglichkeit, den Zugriff auf XML-Daten.<br />– Sie können Objekte erstellen, indem Sie mit der <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> -Methode, und geben Sie den Satz von Features an, für das Objekt mithilfe von ermöglichen die <xref:System.Xml.XmlReaderSettings> Klasse.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|Streambasiert|– Bietet eine schnelle, nicht zwischengespeicherten, nur vorwärts Möglichkeit zum Generieren von XML-Daten.<br />– Sie können Objekte erstellen, indem Sie mit der <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> -Methode, und geben Sie den Satz von Features an, für das Objekt mithilfe von ermöglichen die <xref:System.Xml.XmlWriterSettings> Klasse.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|Im Arbeitsspeicher|-Implementiert die [W3C Document Objekt Model (DOM) Level 1 Core](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) und [DOM Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/) Empfehlungen.<br />– Sie können erstellen, einfügen, entfernen und Ändern von Knoten mithilfe von Methoden und Eigenschaften, die basierend auf dem vertrauten DOM-Modell.<br />-Verwenden Sie diese Option aus, wenn Sie vorhandenen Code ändern, der der W3C-DOM verwendet.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|Im Arbeitsspeicher|-Bietet verschiedene Bearbeitungsoptionen und Navigationsfunktionen, die mit einem Cursormodell.<br />-XML-Dokumenten enthalten sein können, einer <xref:System.Xml.XPath.XPathDocument> oder <xref:System.Xml.XmlDocument> Objekt.<br />– Bietet hervorragende Leistung für die schreibgeschützte Verarbeitung von XML.<br />-Verwenden Sie diese Option aus, wenn Sie vorhandenen Code mit XPath-Abfragen oder XSLT-Transformationen ändern.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|Im Arbeitsspeicher|– Bietet Optionen zum Transformieren von XML-Daten mithilfe von XSL-Transformationen.<br />– Der [XSLT-Compiler (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md) ermöglicht, die Sie verweisen vorkompiliert Transformationen in Ihrer app.|  
  
## <a name="win32-and-com-based-options"></a>Win32- und COM-basierte Optionen  
  
|**Option**|**Beschreibung**|  
|----------------|---------------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)|– Eine schnelle und sichere, ohne Zwischenspeicherung, vorwärts-XML-Parser, mit dem Sie leistungsstarke XML-apps erstellen.<br />-Funktioniert mit einer beliebigen Sprache, die dynamic Link Librarys (DLLs); verwenden können Es wird empfohlen, mithilfe von C++.|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)|-COM-basierte Technologie für die Verarbeitung von XML, das mit dem Windows-Betriebssystem enthalten ist.<br />– Bietet eine systemeigene Implementierung des DOM mit Unterstützung für XPath und XSLT.<br />-Enthält den ereignisbasierten Parser SAX2.|  
  
## <a name="see-also"></a>Siehe auch  
 [Verarbeiten von XML-Daten mithilfe des DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [XSLT-Compiler (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
