---
title: XML-Verarbeitungsoptionen
description: Hier erfahren Sie mehr über die Optionen für die XML-Verarbeitung, z. B. LINQ to XML, XmlReader, XmlWriter, XmlDocument, XPathNavigator, XslCompiledTransform, XmlLite und MSXML.
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
ms.openlocfilehash: c41b3dd99264b9043c5914b84bbb76ac02b317ac
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767766"
---
# <a name="xml-processing-options"></a>XML-Verarbeitungsoptionen
Eine Liste der Microsoft-Technologien zur Verarbeitung von XML-Daten finden Sie in den folgenden Tabellen.  
  
## <a name="net-framework-options"></a>.NET Framework-Optionen  
  
|**Option**|**Verarbeitungstyp**|**Beschreibung**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) <br/> [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) <br />(<xref:System.Xml.Linq>-Namespace)|Im Arbeitsspeicher|-   Basiert auf der Language Integrated Query (LINQ)-Technologie in .NET Framework.<br />-   Erzielt eine Abfrageleistung, die mit der SQL-Leistung für Objekte, relationale Daten und XML-Daten vergleichbar ist.<br />‒   Stellt Funktionen für die intuitive Erstellung und Transformation von Dokumenten bereit.<br />-   Verwenden Sie diese Option beim Schreiben von neuem Code.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|Streambasiert|-   Stellt eine schnelle, vorwärts gerichtete Methode für den Zugriff auf XML-Daten ohne Zwischenspeicherung bereit.<br />-   Sie können Objekte mithilfe der <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType>-Methode erstellen und die für das Objekt zu aktivierenden Funktionen mithilfe der <xref:System.Xml.XmlReaderSettings>-Klasse angeben.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|Streambasiert|-   Stellt eine schnelle, vorwärts gerichtete Methode zum Generieren von XML-Daten ohne Zwischenspeicherung bereit.<br />-   Sie können Objekte mithilfe der <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType>-Methode erstellen und die für das Objekt zu aktivierenden Funktionen mithilfe der <xref:System.Xml.XmlWriterSettings>-Klasse angeben.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|Im Arbeitsspeicher|-   Implementiert die W3C-Empfehlungen [Document Object Model (DOM) Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) und [DOM Level 2 Core](https://www.w3.org/TR/DOM-Level-2-Core/).<br />-   Zum Erstellen, Einfügen, Entfernen und Ändern von Knoten können Sie die Methoden und Eigenschaften verwenden, die auf dem vertrauten DOM-Modell basieren.<br />-   Verwenden Sie diese Option zum Ändern vorhandenen Codes, der W3C DOM verwendet.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|Im Arbeitsspeicher|-   Bietet über ein Cursormodell verschiedene Bearbeitungsoptionen und Navigationsfunktionen.<br />-   Die XML-Dokumente können in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder in einem <xref:System.Xml.XmlDocument>-Objekt enthalten sein.<br />-   Gewährleistet exzellente Leistung für die schreibgeschützte XML-Verarbeitung.<br />-   Verwenden Sie diese Option, wenn Sie vorhandenen Code mit XPath-Abfragen oder XSLT-Transformationen ändern.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|Im Arbeitsspeicher|-   Stellt Optionen zum Transformieren von XML-Daten mithilfe von XSL-Transformationen bereit.<br />-   Über [XSLT Compiler (xsltc.exe)](xslt-compiler-xsltc-exe.md) können Sie auf vorkompilierte Transformationen in Ihrer App verweisen.|  
  
## <a name="win32-and-com-based-options"></a>Win32- und COM-basierte Optionen  
  
|**Option**|**Beschreibung**|  
|----------------|---------------------|  
|[XmlLite](https://docs.microsoft.com/previous-versions/windows/desktop/ms752872(v=vs.85))|-   Ein schneller, sicherer XML-Parser, der eine vorwärts gerichtete Methode zum Generieren von leistungsfähigen XML-Apps ohne Zwischenspeicherung verwendet.<br />-   Unterstützt jede Sprache, die Dynamic Link Librarys (DLLs) verwenden kann; wir empfehlen C++.|  
|[MSXML](https://docs.microsoft.com/previous-versions/windows/desktop/ms763742(v=vs.85))|-   Eine COM-basierte Technologie für die XML-Verarbeitung im Windows-Betriebssystem.<br />-   Stellt eine native DOM-Implementierung mit Unterstützung für XPath und XSLT bereit.<br />-    Enthält den ereignisbasierten Parser SAX2.|  
  
## <a name="see-also"></a>Siehe auch

- [Verarbeiten von XML-Daten mithilfe des DOM](process-xml-data-using-the-dom-model.md)
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [XSLT-Compiler („xsltc.exe“)](xslt-compiler-xsltc-exe.md)
