---
title: Verwenden der XslCompiledTransform-Klasse
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce9a06c14141bb658eb665e643d8da27e18dd94f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590368"
---
# <a name="using-the-xslcompiledtransform-class"></a>Verwenden der XslCompiledTransform-Klasse
Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ist der XSLT-Prozessor in .NET Framework. Diese Klasse wird zum Kompilieren von Stylesheets und zum Ausführen von XSLT-Transformationen verwendet.  
  
> [!NOTE]
>  Obwohl die Gesamtleistung der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse besser ist als die der <xref:System.Xml.Xsl.XslTransform>-Klasse, ist die Leistung der <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse möglicherweise langsamer als die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslTransform>-Klasse, wenn sie zum ersten Mal für eine Transformation aufgerufen wird. Dies liegt daran, dass die XSLT-Datei zunächst kompiliert werden muss, bevor sie geladen wird. Weitere Informationen finden Sie im folgenden Blogbeitrag: [XslCompiledTransform Slower than XslTransform? (Ist XslCompiledTransform langsamer als XslTransform?)](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Eingaben für die XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 Beschreibt die verfügbaren XSLT-Eingabeoptionen.  
  
 [Ausgabeoptionen für die XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 Beschreibt die verfügbaren XSLT-Ausgabeoptionen.  
  
 [Auflösen von externen Ressourcen während der XSLT-Verarbeitung](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 Erläutert die Verwendung der <xref:System.Xml.XmlResolver>-Klasse beim Auflösen externer Ressourcen.  
  
 [Erweitern von XSLT-Stylesheets](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 Erläutert die Unterstützung von XSLT-Erweiterungen.  
  
|||  
|-|-|  
|[Wiederherstellbare XSLT-Fehler](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|Listet die freigegebenen Verhaltensweisen auf, die gemäß der W3C-Empfehlung zu XSL-Transformationen (XSLT), Version 1.0, zugelassen sind, und beschreibt, wie diese Verhaltensweisen von der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse behandelt werden.|  
|[Vorgehensweise: Transformieren eines Knotenfragments](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Beschreibt, wie ein Knotenfragment transformiert wird.|  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Erläutert die Migration von Code von der <xref:System.Xml.Xsl.XslTransform>-Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
