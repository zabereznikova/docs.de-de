---
title: Erstellen von Streams
ms.date: 01/21/2019
ms.technology: dotnet-standard
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
ms.openlocfilehash: 93295c1d70f510ef563abc3a191d6690b1174fa8
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188574"
---
# <a name="compose-streams"></a><span data-ttu-id="21c4b-102">Erstellen von Streams</span><span class="sxs-lookup"><span data-stu-id="21c4b-102">Compose streams</span></span>
<span data-ttu-id="21c4b-103">Ein *Sicherungsspeicher* ist ein Speichermedium, wie etwa ein Datenträger oder Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="21c4b-103">A *backing store* is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="21c4b-104">Jeder einzelne Sicherungsspeicher implementiert seinen eigenen Datenstrom als Implementierung der <xref:System.IO.Stream>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="21c4b-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span>

<span data-ttu-id="21c4b-105">Jeder Datenstromtyp liest und schreibt Bytes in einen bzw. aus einem angegebenen Sicherungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="21c4b-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="21c4b-106">Datenströme, die eine Verbindung mit Sicherungsspeichern herstellen, werden als *Basisdatenströme* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="21c4b-106">Streams that connect to backing stores are called *base streams* .</span></span> <span data-ttu-id="21c4b-107">Basisdatenströme umfassen Konstruktoren mit den erforderlichen Parametern, um eine Verbindung zwischen dem Datenstrom und dem Sicherungsspeicher herzustellen.</span><span class="sxs-lookup"><span data-stu-id="21c4b-107">Base streams have constructors with the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="21c4b-108">Beispielsweise weist <xref:System.IO.FileStream> Konstruktoren auf, die einen Pfadparameter angeben, der wiederum die Freigabe der Datei für Prozesse angibt.</span><span class="sxs-lookup"><span data-stu-id="21c4b-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes.</span></span>  

<span data-ttu-id="21c4b-109">Der Entwurf der <xref:System.IO>-Klassen ermöglicht ein einfacheres Erstellen von Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="21c4b-109">The design of the <xref:System.IO> classes provides simplified stream composition.</span></span> <span data-ttu-id="21c4b-110">Sie können Basisdatenströme an mindestens einen Pass-Through-Datenstrom anfügen, der die von Ihnen gewünschte Funktionalität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="21c4b-110">You can attach base streams to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="21c4b-111">Sie können einen Reader oder Writer an das Ende der Kette anfügen, damit die bevorzugten Typen mühelos gelesen oder geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="21c4b-111">You can attach a reader or writer to the end of the chain, so the preferred types can be read or written easily.</span></span>  

<span data-ttu-id="21c4b-112">In den folgenden Codebeispielen wird ein **FileStream** um die vorhandene Datei *MyFile.txt* erstellt, um *MyFile.txt* zu puffern.</span><span class="sxs-lookup"><span data-stu-id="21c4b-112">The following code examples create a **FileStream** around the existing *MyFile.txt* in order to buffer *MyFile.txt* .</span></span> <span data-ttu-id="21c4b-113">Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.</span><span class="sxs-lookup"><span data-stu-id="21c4b-113">Note that **FileStreams** are buffered by default.</span></span>

>[!IMPORTANT]
><span data-ttu-id="21c4b-114">In den Beispielen wird angenommen, dass eine Datei mit dem Namen *MyFile.txt* bereits in demselben Ordner vorhanden ist, in dem sich auch die App befindet.</span><span class="sxs-lookup"><span data-stu-id="21c4b-114">The examples assume that a file named *MyFile.txt* already exists in the same folder as the app.</span></span>  

## <a name="example-use-streamreader"></a><span data-ttu-id="21c4b-115">Beispiel: Verwenden von StreamReader</span><span class="sxs-lookup"><span data-stu-id="21c4b-115">Example: Use StreamReader</span></span>
<span data-ttu-id="21c4b-116">In dem folgenden Beispiel wird ein <xref:System.IO.StreamReader> zum Lesen von Zeichen aus dem **FileStream** erstellt, der als Konstruktorargument an den **StreamReader** übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="21c4b-116">The following example creates a <xref:System.IO.StreamReader> to read characters from the **FileStream** , which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="21c4b-117">Anschließend liest <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>, bis <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> keine Zeichen mehr findet.</span><span class="sxs-lookup"><span data-stu-id="21c4b-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> then reads until <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> finds no more characters.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a><span data-ttu-id="21c4b-118">Beispiel: Verwenden von BinaryReader</span><span class="sxs-lookup"><span data-stu-id="21c4b-118">Example: Use BinaryReader</span></span>
<span data-ttu-id="21c4b-119">In dem folgenden Beispiel wird ein <xref:System.IO.BinaryReader> zum Lesen von Bytes aus dem **FileStream** erstellt, der als Konstruktorargument an den **BinaryReader** übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="21c4b-119">The following example creates a <xref:System.IO.BinaryReader> to read bytes from the **FileStream** , which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="21c4b-120">Anschließend liest <xref:System.IO.BinaryReader.ReadByte%2A>, bis <xref:System.IO.BinaryReader.PeekChar%2A> keine Bytes mehr findet.</span><span class="sxs-lookup"><span data-stu-id="21c4b-120"><xref:System.IO.BinaryReader.ReadByte%2A> then reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="21c4b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21c4b-121">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
