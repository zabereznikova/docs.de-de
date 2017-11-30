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
# <a name="composing-streams"></a><span data-ttu-id="6b4fa-102">Erstellen von Streams</span><span class="sxs-lookup"><span data-stu-id="6b4fa-102">Composing Streams</span></span>
<span data-ttu-id="6b4fa-103">Einem Speichermedium, z. B. ein Datenträger oder Arbeitsspeicher als ein Sicherungsspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="6b4fa-104">Jeder einzelne Sicherungsspeicher implementiert seinen eigenen Stream als Implementierung der <xref:System.IO.Stream> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="6b4fa-105">Jeder Streamtyp liest und schreibt Bytes in bzw. aus einer angegebenen Sicherungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="6b4fa-106">Streams, die das Herstellen einer Verbindung mit Sicherungsspeicher werden Basisstreams bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="6b4fa-107">Basisstreams haben Konstruktoren, die zur Verbindung mit des Sicherungsspeichers des Streams erforderlichen Parameter haben.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="6b4fa-108">Beispielsweise <xref:System.IO.FileStream> Konstruktoren, die einen Path-Parameter, der angibt angeben, wie die Datei von Prozessen usw. gemeinsam genutzt werden, hat.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="6b4fa-109">Das Design der <xref:System.IO> Klassen bietet vereinfachten Aufbau von Streams.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="6b4fa-110">Basisstreams können an mindestens einen Pass-Through-Streams angefügt werden, die die Funktionalität bereitstellen, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="6b4fa-111">Reader oder Writer kann am Ende der Kette angefügt werden, damit die bevorzugte Typen lesen oder einfach geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="6b4fa-112">Das folgende Codebeispiel erstellt eine **FileStream** um den vorhandenen `MyFile.txt` zu Puffern `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="6b4fa-113">(Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.) Als Nächstes wird ein <xref:System.IO.StreamReader> wird erstellt, um das Lesen von Zeichen aus der **FileStream**, der übergeben wird, um die **StreamReader** als Konstruktorargument.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="6b4fa-114"><xref:System.IO.StreamReader.ReadLine%2A>liest bis <xref:System.IO.StreamReader.Peek%2A> findet keine weiteren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="6b4fa-115">Das folgende Codebeispiel erstellt eine **FileStream** um den vorhandenen `MyFile.txt` zu Puffern `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="6b4fa-116">(Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.) Als Nächstes wird ein **BinaryReader** wird erstellt, um das Lesen von Bytes aus der **FileStream**, der übergeben wird, um die **BinaryReader** als Konstruktorargument.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="6b4fa-117"><xref:System.IO.BinaryReader.ReadByte%2A>liest bis <xref:System.IO.BinaryReader.PeekChar%2A> findet keine weitere Bytes.</span><span class="sxs-lookup"><span data-stu-id="6b4fa-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="6b4fa-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b4fa-118">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
