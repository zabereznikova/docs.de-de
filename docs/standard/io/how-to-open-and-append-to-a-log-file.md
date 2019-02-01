---
title: 'Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 351daa2a13c4a8c4b1551ce74d2eaa6d032f1f17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622730"
---
# <a name="how-to-open-and-append-to-a-log-file"></a>Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei
<xref:System.IO.StreamWriter> und <xref:System.IO.StreamReader> schreiben Zeichen in Streams und lesen Zeichen daraus. Im folgenden Codebeispiel werden die `log.txt`-Datei für die Eingabe geöffnet bzw. die Datei erstellt, falls sie noch nicht vorhanden ist, und Informationen an das Ende der Datei angefügt. Der Inhalt der Datei wird dann zur Anzeige in die Standardausgabe geschrieben. Alternativ zu diesem Beispiel könnten die Informationen als einzelne Zeichenfolge oder Zeichenfolgenarray gespeichert werden, und mit der <xref:System.IO.File.WriteAllText%2A>- bzw. <xref:System.IO.File.WriteAllLines%2A>-Methode könnte die gleiche Funktionalität erzielt werden.  
  
> [!NOTE]
>  Visual Basic-Benutzer können die von der <xref:Microsoft.VisualBasic.Logging.Log>- oder <xref:Microsoft.VisualBasic.FileIO.FileSystem>-Klasse bereitgestellten Methoden und Eigenschaften zum Erstellen von oder Schreiben in Protokolldateien verwenden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StreamWriter>
- <xref:System.IO.StreamReader>
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- [Vorgehensweise: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [Vorgehensweise: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [Vorgehensweise: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
- [Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
