---
title: 'Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7a2a0513a066ae8ea8a70f7a5ae340ab29de7d25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330962"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)

Sie können [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) erstellen und mit den Inhalten aus einer externen Quelle, z. b. einer Datei, einer Zeichenfolge oder einem Stream, mithilfe verschiedener Methoden auffüllen. Diese Methoden sind in den folgenden Beispielen dargestellt.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>So laden Sie XML aus einer Datei

Verwenden Sie zum Auffüllen eines XML-Literals, z. b. eines <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekts aus einer Datei, die `Load`-Methode. Diese Methode kann einen Dateipfad, einen Textstream oder einen XML-Stream als Eingabe verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XDocument.Load%28System.String%29>-Methode verwendet wird, um ein <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einer Textdatei aufzufüllen.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>So laden Sie XML aus einer Zeichenfolge

Zum Auffüllen eines XML-Literals (z. b. eines <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekts aus einer Zeichenfolge) können Sie die `Parse`-Methode verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType>-Methode verwendet wird, um ein <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einer Zeichenfolge aufzufüllen.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>So laden Sie XML aus einem Stream

Zum Auffüllen eines XML-Literals (z. b. eines <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekts aus einem Stream) können Sie die `Load`-Methode oder die <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>-Methode verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode verwendet wird, um ein <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einem XML-Stream aufzufüllen.

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
