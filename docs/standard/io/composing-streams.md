---
title: Erstellen von Streams
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
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75800210a52620c5b08a01c5f8fa888bf40843fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="composing-streams"></a>Erstellen von Streams
Einem Speichermedium, z. B. ein Datenträger oder Arbeitsspeicher als ein Sicherungsspeicher verwendet. Jeder einzelne Sicherungsspeicher implementiert seinen eigenen Stream als Implementierung der <xref:System.IO.Stream> Klasse. Jeder Streamtyp liest und schreibt Bytes in bzw. aus einer angegebenen Sicherungsspeicher. Streams, die das Herstellen einer Verbindung mit Sicherungsspeicher werden Basisstreams bezeichnet. Basisstreams haben Konstruktoren, die zur Verbindung mit des Sicherungsspeichers des Streams erforderlichen Parameter haben. Beispielsweise <xref:System.IO.FileStream> Konstruktoren, die einen Path-Parameter, der angibt angeben, wie die Datei von Prozessen usw. gemeinsam genutzt werden, hat.  
  
 Das Design der <xref:System.IO> Klassen bietet vereinfachten Aufbau von Streams. Basisstreams können an mindestens einen Pass-Through-Streams angefügt werden, die die Funktionalität bereitstellen, die Sie möchten. Reader oder Writer kann am Ende der Kette angefügt werden, damit die bevorzugte Typen lesen oder einfach geschrieben werden können.  
  
 Das folgende Codebeispiel erstellt eine **FileStream** um den vorhandenen `MyFile.txt` zu Puffern `MyFile.txt`. (Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.) Als Nächstes wird ein <xref:System.IO.StreamReader> wird erstellt, um das Lesen von Zeichen aus der **FileStream**, der übergeben wird, um die **StreamReader** als Konstruktorargument. <xref:System.IO.StreamReader.ReadLine%2A>liest bis <xref:System.IO.StreamReader.Peek%2A> findet keine weiteren Zeichen.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 Das folgende Codebeispiel erstellt eine **FileStream** um den vorhandenen `MyFile.txt` zu Puffern `MyFile.txt`. (Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.) Als Nächstes wird ein **BinaryReader** wird erstellt, um das Lesen von Bytes aus der **FileStream**, der übergeben wird, um die **BinaryReader** als Konstruktorargument. <xref:System.IO.BinaryReader.ReadByte%2A>liest bis <xref:System.IO.BinaryReader.PeekChar%2A> findet keine weitere Bytes.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
