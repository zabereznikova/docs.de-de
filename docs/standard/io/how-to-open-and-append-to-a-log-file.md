---
title: "Gewusst wie: Öffnen und Anfügen an eine Protokolldatei"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60c31339231405a1cbbb98dae37d36ad3c3709c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-open-and-append-to-a-log-file"></a>Gewusst wie: Öffnen und Anfügen an eine Protokolldatei
<xref:System.IO.StreamWriter>und <xref:System.IO.StreamReader> Zeichen zu schreiben und Lesen von Zeichen aus Streams. Im folgenden Codebeispiel Beispiel öffnet der `log.txt` Datei für die Eingabe oder die Datei erstellt, falls diese noch nicht vorhanden, und Informationen an das Ende der Datei fügt. Der Inhalt der Datei werden in die Standardausgabe für die Anzeige geschrieben. Als Alternative zu diesem Beispiel kann als eine einzelne Zeichenfolge oder ein Array von Zeichenfolgen, die Informationen gespeichert werden und die <xref:System.IO.File.WriteAllText%2A> oder <xref:System.IO.File.WriteAllLines%2A> Methode kann verwendet werden, um die gleiche Funktionalität zu erzielen.  
  
> [!NOTE]
>  Visual Basic-Benutzer können die Methoden und Eigenschaften, die von bereitgestellte verwenden die <xref:Microsoft.VisualBasic.Logging.Log> Klasse oder <xref:Microsoft.VisualBasic.FileIO.FileSystem> Klasse zum Erstellen von oder Schreiben in Protokolldateien.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [Gewusst wie: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [Gewusst wie: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [Gewusst wie: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
