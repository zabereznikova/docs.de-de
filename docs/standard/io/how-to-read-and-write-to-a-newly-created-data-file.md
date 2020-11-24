---
title: 'Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei'
description: Erfahren Sie, wie Sie mithilfe der Klassen System.IO.BinaryReader und System.IO.BinaryWriter in einer neu erstellten Datendatei in .NET lesen und schreiben.
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET], reading data
- I/O [.NET], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
ms.openlocfilehash: 940d720edfde93f8707a4fd7040e5dd3618a2680
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830713"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei

Die <xref:System.IO.BinaryWriter?displayProperty=nameWithType>-Klasse und die <xref:System.IO.BinaryReader?displayProperty=nameWithType>-Klasse werden zum Schreiben und Lesen von Daten, jedoch nicht von Zeichenfolgen, verwendet. Im folgenden Beispiel wird gezeigt, wie ein leerer Dateistream erstellt wird und Daten darin geschrieben und daraus gelesen werden.

In dem Beispiel wird im aktuellen Verzeichnis eine Datendatei mit dem Namen *Test.data* erstellt. Auch die zugeordneten <xref:System.IO.BinaryWriter>- und <xref:System.IO.BinaryReader>-Objekte werden erstellt, und das <xref:System.IO.BinaryWriter>-Objekt wird zum Schreiben der ganzen Zahlen 0 bis 10 in die Datei *Test.data* verwendet, wodurch der Dateizeiger am Ende der Datei verbleibt. Das <xref:System.IO.BinaryReader>-Objekt setzt dann den Dateizeiger auf seinen Ursprung zurück und liest den angegebenen Inhalt aus.  
  
> [!NOTE]
> Wenn sich *Test.data* bereits im aktuellen Verzeichnis befindet, wird eine <xref:System.IO.IOException>-Ausnahme ausgelöst. Verwenden Sie die Dateimodusoption <xref:System.IO.FileMode.Create?displayProperty=nameWithType> statt <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType>, um immer eine neue Datei zu erstellen, ohne eine Ausnahme auszulösen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [How to: Auflisten von Verzeichnissen und Dateien](how-to-enumerate-directories-and-files.md)  
- [How to: Öffnen und Anfügen an eine Protokolldatei](how-to-open-and-append-to-a-log-file.md)  
- [How to: Lesen von Text aus einer Datei](how-to-read-text-from-a-file.md)  
- [How to: Schreiben von Text in eine Datei](how-to-write-text-to-a-file.md)  
- [How to: Lesen von Zeichen aus einer Zeichenfolge](how-to-read-characters-from-a-string.md)  
- [How to: Schreiben von Zeichen in eine Zeichenfolge](how-to-write-characters-to-a-string.md)  
- [Datei- und Stream-E/A](index.md)
