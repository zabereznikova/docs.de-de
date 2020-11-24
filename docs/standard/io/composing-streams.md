---
title: Erstellen von Streams
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
ms.openlocfilehash: c50a372ee3434fcd7f72ad707ca82c5c9ad8a5c8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823380"
---
# <a name="compose-streams"></a>Erstellen von Streams
Ein *Sicherungsspeicher* ist ein Speichermedium, wie etwa ein Datenträger oder Arbeitsspeicher. Jeder einzelne Sicherungsspeicher implementiert seinen eigenen Datenstrom als Implementierung der <xref:System.IO.Stream>-Klasse.

Jeder Datenstromtyp liest und schreibt Bytes in einen bzw. aus einem angegebenen Sicherungsspeicher. Datenströme, die eine Verbindung mit Sicherungsspeichern herstellen, werden als *Basisdatenströme* bezeichnet. Basisdatenströme umfassen Konstruktoren mit den erforderlichen Parametern, um eine Verbindung zwischen dem Datenstrom und dem Sicherungsspeicher herzustellen. Beispielsweise weist <xref:System.IO.FileStream> Konstruktoren auf, die einen Pfadparameter angeben, der wiederum die Freigabe der Datei für Prozesse angibt.  

Der Entwurf der <xref:System.IO>-Klassen ermöglicht ein einfacheres Erstellen von Datenströmen. Sie können Basisdatenströme an mindestens einen Pass-Through-Datenstrom anfügen, der die von Ihnen gewünschte Funktionalität bereitstellt. Sie können einen Reader oder Writer an das Ende der Kette anfügen, damit die bevorzugten Typen mühelos gelesen oder geschrieben werden können.  

In den folgenden Codebeispielen wird ein **FileStream** um die vorhandene Datei *MyFile.txt* erstellt, um *MyFile.txt* zu puffern. Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.

>[!IMPORTANT]
>In den Beispielen wird angenommen, dass eine Datei mit dem Namen *MyFile.txt* bereits in demselben Ordner vorhanden ist, in dem sich auch die App befindet.  

## <a name="example-use-streamreader"></a>Beispiel: Verwenden von StreamReader
In dem folgenden Beispiel wird ein <xref:System.IO.StreamReader> zum Lesen von Zeichen aus dem **FileStream** erstellt, der als Konstruktorargument an den **StreamReader** übergeben wird. Anschließend liest <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>, bis <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> keine Zeichen mehr findet.  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a>Beispiel: Verwenden von BinaryReader
In dem folgenden Beispiel wird ein <xref:System.IO.BinaryReader> zum Lesen von Bytes aus dem **FileStream** erstellt, der als Konstruktorargument an den **BinaryReader** übergeben wird. Anschließend liest <xref:System.IO.BinaryReader.ReadByte%2A>, bis <xref:System.IO.BinaryReader.PeekChar%2A> keine Bytes mehr findet.  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
