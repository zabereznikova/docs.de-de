---
title: "How to: Load XML from a File, String, or Stream (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML [Visual Basic], loading"
  - "LINQ to XML [Visual Basic], loading XML from files"
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Load XML from a File, String, or Stream (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) erstellen und sie mit dem Inhalt aus einer externen Quelle wie beispielsweise einer Datei, einer Zeichenfolge oder einem Stream unter Verwendung von unterschiedlichen Methoden auffüllen.  Diese Methoden sind in den folgenden Beispielen dargestellt.  
  
 [!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### So laden Sie XML aus einer Datei  
  
-   Um ein XML\-Literal wie beispielsweise ein <xref:System.Xml.Linq.XElement>\-Objekt oder ein <xref:System.Xml.Linq.XDocument>\-Objekt aus einer Datei aufzufüllen, verwenden Sie die `Load`\-Methode.  Diese Methode kann einen Dateipfad, einen Textstream oder einen XML\-Stream als Eingabe verwenden.  
  
     Im folgenden Codebeispiel ist dargestellt, wie mithilfe der <xref:System.Xml.Linq.XDocument.Load%28System.String%29>\-Methode ein <xref:System.Xml.Linq.XDocument>\-Objekt mit XML aus einer Textdatei aufgefüllt wird.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### So laden Sie XML aus einer Zeichenfolge  
  
-   Um ein XML\-Literal wie beispielsweise ein <xref:System.Xml.Linq.XElement>\-Objekt oder ein <xref:System.Xml.Linq.XDocument>\-Objekt aus einer Zeichenfolge aufzufüllen, verwenden Sie die `Parse`\-Methode.  
  
     Im folgenden Codebeispiel ist dargestellt, wie mithilfe der <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>\-Methode ein <xref:System.Xml.Linq.XDocument>\-Objekt mit XML aus einer Zeichenfolge aufgefüllt wird.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### So laden Sie XML aus einem Stream  
  
-   Um ein XML\-Literal wie beispielsweise ein <xref:System.Xml.Linq.XElement>\-Objekt oder ein <xref:System.Xml.Linq.XDocument>\-Objekt aus einem Stream aufzufüllen, verwenden Sie die `Load`\-Methode oder die <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>\-Methode.  
  
 Im folgenden Codebeispiel ist dargestellt, wie mithilfe der <xref:System.Xml.Linq.XNode.ReadFrom%2A>\-Methode ein <xref:System.Xml.Linq.XDocument>\-Objekt mit XML aus einem XML\-Stream aufgefüllt wird.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## Siehe auch  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>   
 [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)