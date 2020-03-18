---
title: Serialisieren in Dateien, TextWriters und XmlWriters
ms.date: 07/20/2015
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
ms.openlocfilehash: 20cb84a9f79ca8de3e86a996f18c388dc53340ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68868856"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Serialisieren in Dateien, TextWriters und XmlWriters

Sie können XML-Strukturen in eine <xref:System.IO.File>, in einen <xref:System.IO.TextWriter> oder in einen <xref:System.Xml.XmlWriter> serialisieren.

Mit der <xref:System.Xml.Linq.XDocument>-Methode können Sie jede XML-Komponente, auch <xref:System.Xml.Linq.XElement> und `ToString`, in eine Zeichenfolge serialisieren.

Wenn Sie beim Serialisieren in eine Zeichenfolge die Formatierung unterdrücken möchten, können Sie die <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>-Methode verwenden.

Das Standardverhalten beim Serialisieren in eine Datei besteht darin, dass das resultierende XML-Dokument formatiert (mit Einzügen versehen) wird. Wenn Sie das Dokument mit Einzügen versehen, wird der nicht signifikante Leerraum in der XML-Struktur nicht beibehalten. Wenn Sie eine Serialisierung mit Formatierung vornehmen möchten, verwenden Sie eine der Überladungen der folgenden Methoden, die <xref:System.Xml.Linq.SaveOptions> nicht als Argument akzeptieren.

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

Wenn Sie möchten, dass keine Einzüge vorgenommen werden und der nicht signifikante Leerraum in der XML-Struktur beibehalten wird, verwenden Sie eine der Überladungen der folgenden Methoden, die <xref:System.Xml.Linq.SaveOptions> als Argument akzeptieren:

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

Beispiele finden Sie im entsprechenden Referenzthema.

## <a name="see-also"></a>Weitere Informationen

- [Serializing XML Trees (C#) (Serialisieren von XML-Strukturen (C#))](serializing-to-files-textwriters-and-xmlwriters.md)
