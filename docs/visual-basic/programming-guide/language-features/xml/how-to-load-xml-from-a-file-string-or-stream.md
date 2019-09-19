---
title: 'Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: ba88ae19abc216a318d6c2069ab0846d5db8a346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054167"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)

Sie können [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) erstellen und mit den Inhalten aus einer externen Quelle, z. b. einer Datei, einer Zeichenfolge oder einem Stream, mithilfe verschiedener Methoden auffüllen. Diese Methoden sind in den folgenden Beispielen dargestellt.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>So laden Sie XML aus einer Datei

Verwenden Sie die <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> -MethodezumAuffülleneinesXML-Literals,z.b.eines-Objektsodereines-`Load` Objekts aus einer Datei Diese Methode kann einen Dateipfad, einen Textstream oder einen XML-Stream als Eingabe verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XDocument.Load%28System.String%29> -Methode verwendet wird, <xref:System.Xml.Linq.XDocument> um ein-Objekt mit XML aus einer Textdatei aufzufüllen.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>So laden Sie XML aus einer Zeichenfolge

Zum Auffüllen eines XML-Literals (z <xref:System.Xml.Linq.XElement> . <xref:System.Xml.Linq.XDocument> b. ein-oder-Objekt aus einer `Parse` Zeichenfolge) können Sie die-Methode verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> -Methode verwendet wird, <xref:System.Xml.Linq.XDocument> um ein-Objekt mit XML aus einer Zeichenfolge aufzufüllen.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>So laden Sie XML aus einem Stream

Zum Auffüllen eines XML-Literals (z <xref:System.Xml.Linq.XElement> . <xref:System.Xml.Linq.XDocument> b. ein-oder-Objekt aus einem `Load` Stream) können <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> Sie die-Methode oder die-Methode verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XNode.ReadFrom%2A> -Methode verwendet wird, <xref:System.Xml.Linq.XDocument> um ein-Objekt mit XML aus einem XML-Stream aufzufüllen.

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
