---
title: 'Gewusst wie: Lesen aus einer Textdatei'
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
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6fbf9c910847986af1c02b5848c81266009e2e07
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="b002f-102">Gewusst wie: Lesen aus einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="b002f-102">How to: Read Text from a File</span></span>
<span data-ttu-id="b002f-103">In den folgenden Beispielen wird das synchrone und asynchrone Lesen aus einer Textdatei mithilfe von .NET für Desktop-Apps veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b002f-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="b002f-104">In beiden Beispielen geben Sie beim Erstellen der Instanz der <xref:System.IO.StreamReader>-Klasse einen absoluten oder relativen Pfad zur Datei an.</span><span class="sxs-lookup"><span data-stu-id="b002f-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="b002f-105">In den folgenden Beispielen wird angenommen, dass sich eine Datei mit dem Namen "TestFile.txt" im gleichen Ordner wie die Anwendung befindet.</span><span class="sxs-lookup"><span data-stu-id="b002f-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="b002f-106">Diese Codebeispiele gelten nicht für die Entwicklung von Windows Store-Apps, da die Windows-Runtime verschiedene Streamtypen für Lese- und Schreibvorgänge für Dateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b002f-106">These code examples do not apply developing for Windows Store Apps because the Windows Runtime provides different streams types reading and writing to files.</span></span> <span data-ttu-id="b002f-107">Ein Beispiel für das Lesen von Text aus einer Datei im Kontext einer Windows Store-App finden Sie unter [Schnellstart: Lesen und Schreiben einer Datei](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).</span><span class="sxs-lookup"><span data-stu-id="b002f-107">For an example that shows how to read text from a file within the context of a Windows Store app, see [Quickstart: Reading and writing files](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).</span></span> <span data-ttu-id="b002f-108">Weitere Beispiele zum Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams finden Sie unter [Gewusst wie: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="b002f-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b002f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b002f-109">Example</span></span>  
 <span data-ttu-id="b002f-110">Das erste Beispiel veranschaulicht einen synchronen Lesevorgang in einer Konsolenanwendung an.</span><span class="sxs-lookup"><span data-stu-id="b002f-110">The first example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="b002f-111">In diesem Beispiel wird die Textdatei mit einem Streamreader geöffnet, der Inhalt wird in eine Zeichenfolge kopiert, und die Zeichenfolge wird in der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b002f-111">In this example, the text file is opened using a stream reader, the contents are copied to a string and string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="b002f-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b002f-112">Example</span></span>  
 <span data-ttu-id="b002f-113">Das zweite Beispiel veranschaulicht einen asynchronen Lesevorgang in einer Windows Presentation Foundation (WPF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b002f-113">The second example shows an asynchronous read operation within a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="b002f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b002f-114">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="b002f-115">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="b002f-115">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="b002f-116">NIB: Gewusst wie: Erstellen einer Verzeichnisauflistung</span><span class="sxs-lookup"><span data-stu-id="b002f-116">NIB: How to: Create a Directory Listing</span></span>](http://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="b002f-117">Schnellstart: Lesen und Schreiben einer Datei</span><span class="sxs-lookup"><span data-stu-id="b002f-117">Quickstart: Reading and writing files</span></span>](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [<span data-ttu-id="b002f-118">Gewusst wie: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams</span><span class="sxs-lookup"><span data-stu-id="b002f-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [<span data-ttu-id="b002f-119">Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei</span><span class="sxs-lookup"><span data-stu-id="b002f-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="b002f-120">Gewusst wie: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="b002f-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="b002f-121">Gewusst wie: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="b002f-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="b002f-122">Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b002f-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="b002f-123">Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b002f-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="b002f-124">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="b002f-124">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
