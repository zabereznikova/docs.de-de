---
title: 'Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 572e34b1cd4813fad35e6afaf2ec3d0d9dac470a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)
Sie können erstellen [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) und füllen Sie sie mit dem Inhalt aus einer externen Quelle, z. B. eine Datei, eine Zeichenfolge oder einen Stream mithilfe mehrerer Methoden. Diese Methoden werden in den folgenden Beispielen dargestellt.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Beim Laden von XML aus einer Datei  
  
-   Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einer Datei, die Verwendung der `Load` Methode. Diese Methode kann einen Dateipfad, Textstream oder XML-Stream als Eingabe verwenden.  
  
     Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XDocument.Load%28System.String%29> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einer Textdatei.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>Beim Laden von XML aus einer Zeichenfolge  
  
-   Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einer Zeichenfolge können Sie die `Parse` Methode.  
  
     Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einer Zeichenfolge.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>Beim Laden von XML aus einem stream  
  
-   Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einem Stream, können Sie die `Load` Methode oder die <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> Methode.  
  
 Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XNode.ReadFrom%2A> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einem XML-Datenstrom.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
