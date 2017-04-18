---
title: 'Gewusst wie: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 242c8b79cbe1329b6f53e9fd4e5495d4a157e08c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)
Sie können erstellen [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) und füllen Sie sie mit dem Inhalt aus einer externen Quelle wie z. B. eine Datei, einer Zeichenfolge oder einem Stream mithilfe mehrerer Methoden. Diese Methoden werden in den folgenden Beispielen dargestellt.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Beim Laden von XML aus einer Datei  
  
-   Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekt aus einer Datei, mit der `Load` -Methode.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Diese Methode kann einen Dateipfad, Textstream oder XML-Stream als Eingabe verwenden.  
  
     Das folgende Codebeispiel zeigt die Verwendung der <xref:System.Xml.Linq.XDocument.Load%28System.String%29>-Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einer Textdatei.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%28System.String%29>  
  
     [!code-vb[VbXMLSamples&#43;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>Beim Laden von XML aus einer Zeichenfolge  
  
-   Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>-Objekt aus einer Zeichenfolge können Sie die `Parse` -Methode.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
     Das folgende Codebeispiel zeigt die Verwendung der <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>-Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einer Zeichenfolge.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>  
  
     [!code-vb[VbXMLSamples&#47;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>Beim Laden von XML aus einem stream  
  
-   Zum Auffüllen einer XML-literal wie ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekt aus einem Stream und können die `Load` Methode oder die <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>-Methode.</xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
 Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einem XML-Stream.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
 [!code-vb[VbXMLSamples&#46;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>   
 [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)

