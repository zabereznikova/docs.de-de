---
title: Verwenden der XslCompiledTransform-Klasse
ms.date: 03/30/2017
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: f2eae6f10cc2adf4628a0c2626617ef9a027c598
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821761"
---
# <a name="using-the-xslcompiledtransform-class"></a>Verwenden der XslCompiledTransform-Klasse
Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ist der XSLT-Prozessor in .NET Framework. Diese Klasse wird zum Kompilieren von Stylesheets und zum Ausführen von XSLT-Transformationen verwendet.  
  
> [!NOTE]
> Obwohl die Gesamtleistung der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse besser ist als die der <xref:System.Xml.Xsl.XslTransform>-Klasse, ist die Leistung der <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse möglicherweise langsamer als die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode der <xref:System.Xml.Xsl.XslTransform>-Klasse, wenn sie zum ersten Mal für eine Transformation aufgerufen wird. Dies liegt daran, dass die XSLT-Datei zunächst kompiliert werden muss, bevor sie geladen wird. Weitere Informationen finden Sie im folgenden Blogbeitrag: [XslCompiledTransform Slower than XslTransform? (Ist XslCompiledTransform langsamer als XslTransform?)](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Eingaben für die XslCompiledTransform-Klasse](inputs-to-the-xslcompiledtransform-class.md)  
 Beschreibt die verfügbaren XSLT-Eingabeoptionen.  
  
 [Ausgabeoptionen für die XslCompiledTransform-Klasse](output-options-on-the-xslcompiledtransform-class.md)  
 Beschreibt die verfügbaren XSLT-Ausgabeoptionen.  
  
 [Auflösen von externen Ressourcen während der XSLT-Verarbeitung](resolving-external-resources-during-xslt-processing.md)  
 Erläutert die Verwendung der <xref:System.Xml.XmlResolver>-Klasse beim Auflösen externer Ressourcen.  
  
 [Erweitern von XSLT-Stylesheets](extending-xslt-style-sheets.md)  
 Erläutert die Unterstützung von XSLT-Erweiterungen.  
  
|||  
|-|-|  
|[Wiederherstellbare XSLT-Fehler](recoverable-xslt-errors.md)|Listet die freigegebenen Verhaltensweisen auf, die gemäß der W3C-Empfehlung zu XSL-Transformationen (XSLT), Version 1.0, zugelassen sind, und beschreibt, wie diese Verhaltensweisen von der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse behandelt werden.|  
|[How to: Transformieren eines Knotenfragments](how-to-transform-a-node-fragment.md)|Beschreibt, wie ein Knotenfragment transformiert wird.|  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md)  
 Erläutert die Migration von Code von der <xref:System.Xml.Xsl.XslTransform>-Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
