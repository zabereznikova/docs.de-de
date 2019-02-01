---
title: 'Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f51042564158cfd7924164ce2b1a0fcc9d2658d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562829"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei
Die <xref:System.IO.BinaryWriter>-Klasse und die <xref:System.IO.BinaryReader?displayProperty=nameWithType>-Klasse werden eher zum Schreiben und Lesen von Daten als von Zeichenfolgen verwendet. Im folgenden Beispiel wird gezeigt, wie Daten in einen neuen, leeren Dateistream mit dem Namen `Test.data` geschrieben und daraus gelesen werden. Nach dem Erstellen der Datendatei im aktuellen Verzeichnis werden die zugeordneten <xref:System.IO.BinaryWriter>- und <xref:System.IO.BinaryReader>-Objekte erstellt. Das <xref:System.IO.BinaryWriter>-Objekt wird zum Schreiben der ganzen Zahlen 0 bis 10 in `Test.data` verwendet, wodurch der Dateizeiger am Ende der Datei verbleibt. Nach dem Zurücksetzen des Dateizeigers auf seinen Ursprung liest das <xref:System.IO.BinaryReader>-Objekt den angegebenen Inhalt aus.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn sich `Test.data` bereits im aktuellen Verzeichnis befindet, wird eine <xref:System.IO.IOException>-Ausnahme ausgelöst. Verwenden Sie die Dateimodusoption <xref:System.IO.FileMode.Create?displayProperty=nameWithType>, wenn Sie den Dateistream initialisieren, um immer eine neue Datei zu erstellen, ohne eine Ausnahme auszulösen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryWriter>
- <xref:System.IO.FileStream>
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>
- <xref:System.IO.SeekOrigin>
- [Vorgehensweise: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [Vorgehensweise: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [Vorgehensweise: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
- [Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
