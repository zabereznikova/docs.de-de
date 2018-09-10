---
title: 'Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei'
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
ms.openlocfilehash: 65c56a11531f705b7e047e435ec575969d39a616
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44187675"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei
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
- [Gewusst wie: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Gewusst wie: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Gewusst wie: Lesen von Text aus einer Datei](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Gewusst wie: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
