---
title: "XPathDocument-Eingaben in &quot;XslTransform&quot; | Microsoft Docs"
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
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# XPathDocument-Eingaben in &quot;XslTransform&quot;
Das <xref:System.Xml.XPath.XPathDocument> ist ein schreibgeschützter Zwischenspeicher für die Verarbeitung von Dokumenten mit <xref:System.Xml.Xsl.XslTransform>.  Seine Struktur ähnelt der des XML\-Dokumentobjektmodells \(Document Object Model – DOM\), es ist jedoch ideal geeignet für die XSLT\-Verarbeitung \(Extensible Stylesheet Language for Transformations\) und das XPath\-Datenmodell \(XML Path Language\) unter Verwendung der XPath\-Optimierungsfunktionen für den <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
>  Die <xref:System.Xml.Xsl.XslTransform>\-Klasse ist in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] veraltet.  Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>\-Klasse können Sie XSLT\-Transformationen \(Extensible Stylesheet Language for Transformations\) vornehmen.  Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform\-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform\-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
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
  
## Siehe auch  
 [Implementierung des XSLT\-Prozessors durch die XslTransform\-Klasse](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)