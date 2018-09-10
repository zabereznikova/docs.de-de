---
title: Erstellen von Streams
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e52b827f337892c33ec61b9affa1cc646a759c5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44182463"
---
# <a name="composing-streams"></a>Erstellen von Streams
Ein Sicherungsspeicher ist ein Speichermedium, wie etwa ein Datenträger oder Arbeitsspeicher. Jeder einzelne Sicherungsspeicher implementiert seinen eigenen Datenstrom als Implementierung der <xref:System.IO.Stream>-Klasse. Jeder Datenstromtyp liest und schreibt Bytes in einen bzw. aus einem angegebenen Sicherungsspeicher. Datenströme, die eine Verbindung mit Sicherungsspeichern herstellen, werden als Basisdatenströme bezeichnet. Basisdatenströme umfassen Konstruktoren mit den erforderlichen Parametern, um eine Verbindung zwischen dem Datenstrom und dem Sicherungsspeicher herzustellen. Beispielsweise weist <xref:System.IO.FileStream> Konstruktoren auf, die einen Pfadparameter angeben, der u.a. wiederum die Freigabe der Datei für Prozesse angibt.  
  
 Der Entwurf der <xref:System.IO>-Klassen ermöglicht ein einfacheres Erstellen von Datenströmen. Basisdatenströme können an mindestens einen Pass-Through-Datenstrom angefügt werden, der die von Ihnen gewünschte Funktionalität bereitstellt. Ein Reader oder Writer kann an das Ende der Kette angefügt werden, damit die bevorzugten Typen mühelos gelesen oder geschrieben werden können.  
  
 Im folgenden Codebeispiel wird ein **FileStream** um die vorhandene Datei `MyFile.txt` erstellt, um `MyFile.txt` zu puffern. (Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.) Als Nächstes wird ein <xref:System.IO.StreamReader> zum Lesen von Zeichen aus dem **FileStream** erstellt, der als Konstruktorargument an den **StreamReader** übergeben wird. <xref:System.IO.StreamReader.ReadLine%2A> liest, bis <xref:System.IO.StreamReader.Peek%2A> keine Zeichen mehr findet.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 Im folgenden Codebeispiel wird ein **FileStream** um die vorhandene Datei `MyFile.txt` erstellt, um `MyFile.txt` zu puffern. (Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.) Als Nächstes wird ein **BinaryReader** zum Lesen von Bytes aus dem **FileStream** erstellt, der als Konstruktorargument an den **BinaryReader** übergeben wird. <xref:System.IO.BinaryReader.ReadByte%2A> liest, bis <xref:System.IO.BinaryReader.PeekChar%2A> keine Bytes mehr findet.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
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
