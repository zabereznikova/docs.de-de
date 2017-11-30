---
title: XPathDocument-Eingaben in XslTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 80708dfa60636bbb038c3a86e336709339d2ac55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xpathdocument-input-to-xsltransform"></a>XPathDocument-Eingaben in XslTransform
Das <xref:System.Xml.XPath.XPathDocument> ist ein schreibgeschützter Zwischenspeicher für die Verarbeitung von Dokumenten mit <xref:System.Xml.Xsl.XslTransform>. Seine Struktur ähnelt der des XML-Dokumentobjektmodells (Document Object Model – DOM), es ist jedoch ideal geeignet für die XSLT-Verarbeitung (Extensible Stylesheet Language for Transformations) und das XPath-Datenmodell (XML Path Language) unter Verwendung der XPath-Optimierungsfunktionen für den <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
>  Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Finden Sie unter [mithilfe der Klasse "XslCompiledTransform"](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) für Weitere Informationen.  
  
 m folgenden Codebeispiel wird ein <xref:System.Xml.XPath.XPathDocument> als Eingabe für eine Transformation erstellt.  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XslTransform-Klasse implementiert die XSLT-Prozessor](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
