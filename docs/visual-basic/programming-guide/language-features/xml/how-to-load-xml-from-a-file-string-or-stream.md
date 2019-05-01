---
title: 'Vorgehensweise: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 2b9da2062068ef25c5df97ef19b1502999ea78ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052533"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Vorgehensweise: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream (Visual Basic)
Sie können erstellen [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) und füllen Sie sie mit dem Inhalt aus einer externen Quelle wie z. B. eine Datei, eine Zeichenfolge oder einem Stream mithilfe mehrerer Methoden. Diese Methoden werden in den folgenden Beispielen gezeigt.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Beim Laden von XML aus einer Datei  
  
- Zum Auffüllen eines XML-Literals, z. B. eine <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einer Datei, die Verwendung der `Load` Methode. Diese Methode kann ein Dateipfad, Textstream oder XML-Stream als Eingabe verwenden.  
  
     Das folgende Codebeispiel zeigt die Verwendung von der <xref:System.Xml.Linq.XDocument.Load%28System.String%29> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> Objekt mit der XML-Code aus einer Textdatei.  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a>Beim Laden von XML aus einer Zeichenfolge  
  
- Zum Auffüllen eines XML-Literals, z. B. eine <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einer Zeichenfolge, können Sie die `Parse` Methode.  
  
     Das folgende Codebeispiel zeigt die Verwendung von der <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> mit XML-Objekt, aus einer Zeichenfolge.  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a>Beim Laden von XML aus einem stream  
  
- Zum Auffüllen eines XML-Literals, z. B. eine <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einem Stream können Sie die `Load` Methode oder der <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> Methode.  
  
 Das folgende Codebeispiel zeigt die Verwendung von der <xref:System.Xml.Linq.XNode.ReadFrom%2A> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> Objekt mit der XML-Code aus einem XML-Stream.  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
