---
title: 'Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7f2a961ebb7ecd4fc0512e141b4a437be87bec0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392287"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)

Sie können [XML-Literale](../../../language-reference/xml-literals/index.md) erstellen und mit den Inhalten aus einer externen Quelle, z. b. einer Datei, einer Zeichenfolge oder einem Stream, mithilfe verschiedener Methoden auffüllen. Diese Methoden sind in den folgenden Beispielen dargestellt.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>So laden Sie XML aus einer Datei

Verwenden Sie die-Methode zum Auffüllen eines XML-Literals, z. b. eines- <xref:System.Xml.Linq.XElement> Objekts oder eines- <xref:System.Xml.Linq.XDocument> Objekts aus einer Datei `Load` Diese Methode kann einen Dateipfad, einen Textstream oder einen XML-Stream als Eingabe verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die-Methode verwendet wird <xref:System.Xml.Linq.XDocument.Load%28System.String%29> , um ein- <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einer Textdatei aufzufüllen.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>So laden Sie XML aus einer Zeichenfolge

Zum Auffüllen eines XML-Literals (z. b. ein- <xref:System.Xml.Linq.XElement> oder- <xref:System.Xml.Linq.XDocument> Objekt aus einer Zeichenfolge) können Sie die- `Parse` Methode verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die-Methode verwendet wird <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> , um ein- <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einer Zeichenfolge aufzufüllen.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>So laden Sie XML aus einem Stream

Zum Auffüllen eines XML-Literals (z. b. ein- <xref:System.Xml.Linq.XElement> oder- <xref:System.Xml.Linq.XDocument> Objekt aus einem Stream) können Sie die- `Load` Methode oder die- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> Methode verwenden.

Im folgenden Codebeispiel wird gezeigt, wie die-Methode verwendet wird <xref:System.Xml.Linq.XNode.ReadFrom%2A> , um ein- <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einem XML-Stream aufzufüllen.

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [XML-Literale](../../../language-reference/xml-literals/index.md)
- [XML](index.md)
- [Bearbeiten von XML in Visual Basic](manipulating-xml.md)
