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
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2018
ms.locfileid: "47232278"
---
# <a name="composing-streams"></a><span data-ttu-id="6fb27-102">Erstellen von Streams</span><span class="sxs-lookup"><span data-stu-id="6fb27-102">Composing Streams</span></span>
<span data-ttu-id="6fb27-103">Ein Sicherungsspeicher ist ein Speichermedium, wie etwa ein Datenträger oder Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="6fb27-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="6fb27-104">Jeder einzelne Sicherungsspeicher implementiert seinen eigenen Datenstrom als Implementierung der <xref:System.IO.Stream>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6fb27-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="6fb27-105">Jeder Datenstromtyp liest und schreibt Bytes in einen bzw. aus einem angegebenen Sicherungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="6fb27-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="6fb27-106">Datenströme, die eine Verbindung mit Sicherungsspeichern herstellen, werden als Basisdatenströme bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6fb27-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="6fb27-107">Basisdatenströme umfassen Konstruktoren mit den erforderlichen Parametern, um eine Verbindung zwischen dem Datenstrom und dem Sicherungsspeicher herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6fb27-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="6fb27-108">Beispielsweise weist <xref:System.IO.FileStream> Konstruktoren auf, die einen Pfadparameter angeben, der u.a. wiederum die Freigabe der Datei für Prozesse angibt.</span><span class="sxs-lookup"><span data-stu-id="6fb27-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="6fb27-109">Der Entwurf der <xref:System.IO>-Klassen ermöglicht ein einfacheres Erstellen von Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="6fb27-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="6fb27-110">Basisdatenströme können an mindestens einen Pass-Through-Datenstrom angefügt werden, der die von Ihnen gewünschte Funktionalität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6fb27-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="6fb27-111">Ein Reader oder Writer kann an das Ende der Kette angefügt werden, damit die bevorzugten Typen mühelos gelesen oder geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="6fb27-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="6fb27-112">Im folgenden Codebeispiel wird ein **FileStream** um die vorhandene Datei `MyFile.txt` erstellt, um `MyFile.txt` zu puffern.</span><span class="sxs-lookup"><span data-stu-id="6fb27-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="6fb27-113">(Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.) Als Nächstes wird ein <xref:System.IO.StreamReader> zum Lesen von Zeichen aus dem **FileStream** erstellt, der als Konstruktorargument an den **StreamReader** übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="6fb27-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="6fb27-114"><xref:System.IO.StreamReader.ReadLine%2A> liest, bis <xref:System.IO.StreamReader.Peek%2A> keine Zeichen mehr findet.</span><span class="sxs-lookup"><span data-stu-id="6fb27-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="6fb27-115">Im folgenden Codebeispiel wird ein **FileStream** um die vorhandene Datei `MyFile.txt` erstellt, um `MyFile.txt` zu puffern.</span><span class="sxs-lookup"><span data-stu-id="6fb27-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="6fb27-116">(Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.) Als Nächstes wird ein **BinaryReader** zum Lesen von Bytes aus dem **FileStream** erstellt, der als Konstruktorargument an den **BinaryReader** übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="6fb27-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="6fb27-117"><xref:System.IO.BinaryReader.ReadByte%2A> liest, bis <xref:System.IO.BinaryReader.PeekChar%2A> keine Bytes mehr findet.</span><span class="sxs-lookup"><span data-stu-id="6fb27-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="6fb27-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fb27-118">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
