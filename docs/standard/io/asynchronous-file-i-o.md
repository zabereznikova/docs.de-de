---
title: Asynchrone Datei-E/A
description: Informationen zu asynchronen E/A-Dateivorgängen in .NET. Informationen zu asynchronen Methoden zur Vereinfachung von asynchronen Vorgängen, z. B. ReadAsync und WriteAsync
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, synchronous streams
- asynchronous I/O
- synchronous I/O
- streams, asynchronous streams
- I/O [.NET], asynchronous I/O
- Stream class, synchronous I/O
- data streams, asynchronous streams
- Stream class, asynchronous I/O
- multiple I/O requests
- data streams, synchronous streams
ms.assetid: dbdd55e7-d6b9-4f9e-8abb-ab0edd4457f7
ms.openlocfilehash: a148e6e13ec0ee4ee469a0630f150199c5a3af13
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188600"
---
# <a name="asynchronous-file-io"></a><span data-ttu-id="a33bf-104">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="a33bf-104">Asynchronous File I/O</span></span>

<span data-ttu-id="a33bf-105">Mithilfe von asynchronen Vorgängen können Sie ressourcenintensive E/A-Vorgänge auszuführen, ohne den Hauptthread zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="a33bf-105">Asynchronous operations enable you to perform resource-intensive I/O operations without blocking the main thread.</span></span> <span data-ttu-id="a33bf-106">Diese Überlegungen zur Leistung sind insbesondere in einer Windows 8.x Store-App oder Desktop-App wichtig, bei der ein zeitaufwendiger Streamingvorgang den UI-Thread blockieren kann und es dann den Anschein hat, dass Ihre App nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a33bf-106">This performance consideration is particularly important in a Windows 8.x Store app or desktop app where a time-consuming stream operation can block the UI thread and make your app appear as if it is not working.</span></span>

<span data-ttu-id="a33bf-107">Ab .NET Framework 4.5 enthalten die E/A-Typen asynchrone Methoden, um asynchrone Vorgänge zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a33bf-107">Starting with .NET Framework 4.5, the I/O types include async methods to simplify asynchronous operations.</span></span> <span data-ttu-id="a33bf-108">Eine asynchrone Methode enthält `Async` in ihrem Namen, z. B. <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>und <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="a33bf-108">An async method contains `Async` in its name, such as <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>, and <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span></span> <span data-ttu-id="a33bf-109">Diese asynchronen Methoden werden für Streamklassen wie <xref:System.IO.Stream>, <xref:System.IO.FileStream>und <xref:System.IO.MemoryStream>sowie für Klassen implementiert, die für das Lesen und das Schreiben in Streams verwendet werden, z. B. <xref:System.IO.TextReader> und <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="a33bf-109">These async methods are implemented on stream classes, such as <xref:System.IO.Stream>, <xref:System.IO.FileStream>, and <xref:System.IO.MemoryStream>, and on classes that are used for reading from or writing to streams, such <xref:System.IO.TextReader> and <xref:System.IO.TextWriter>.</span></span>

<span data-ttu-id="a33bf-110">In .NET Framework 4 und vorherigen Versionen müssen Sie Methoden wie <xref:System.IO.Stream.BeginRead%2A> und <xref:System.IO.Stream.EndRead%2A> verwenden, um asynchrone E/A-Vorgänge zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a33bf-110">In .NET Framework 4 and earlier versions, you have to use methods such as <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> to implement asynchronous I/O operations.</span></span> <span data-ttu-id="a33bf-111">Diese Methoden sind in aktuellen .NET-Versionen zwar weiterhin verfügbar, um Legacycode zu unterstützen, aber Sie können mithilfe der asynchronen Methoden leichter asynchrone E/A-Vorgänge implementieren.</span><span class="sxs-lookup"><span data-stu-id="a33bf-111">These methods are still available in current .NET versions to support legacy code; however, the async methods help you implement asynchronous I/O operations more easily.</span></span>

<span data-ttu-id="a33bf-112">C# und Visual Basic verfügen jeweils über zwei Schlüsselwörter für asynchrone Programmierung:</span><span class="sxs-lookup"><span data-stu-id="a33bf-112">C# and Visual Basic each have two keywords for asynchronous programming:</span></span>

- <span data-ttu-id="a33bf-113">Der`Async` -Modifizierer (Visual Basic) bzw. `async` -Modifizierer (C#), der verwendet wird, um eine Methode zu kennzeichnen, die einen asynchronen Vorgang enthält.</span><span class="sxs-lookup"><span data-stu-id="a33bf-113">`Async` (Visual Basic) or `async` (C#) modifier, which is used to mark a method that contains an asynchronous operation.</span></span>

- <span data-ttu-id="a33bf-114">Der`Await` -Operator (Visual Basic) bzw. `await` -Operator (C#), der auf das Ergebnis einer asynchronen Methode angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a33bf-114">`Await` (Visual Basic) or `await` (C#) operator, which is applied to the result of an async method.</span></span>

<span data-ttu-id="a33bf-115">Um asynchrone E/A-Vorgänge zu implementieren, verwenden Sie diese Schlüsselwörter in Verbindung mit den asynchronen Methoden, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a33bf-115">To implement asynchronous I/O operations, use these keywords in conjunction with the async methods, as shown in the following examples.</span></span> <span data-ttu-id="a33bf-116">Weitere Informationen finden Sie unter [Asynchrone Programmierung mit Async und Await (C#)](../../csharp/programming-guide/concepts/async/index.md) oder [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="a33bf-116">For more information, see [Asynchronous programming with async and await (C#)](../../csharp/programming-guide/concepts/async/index.md) or [Asynchronous Programming with Async and Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="a33bf-117">Das folgende Beispiel zeigt, wie mithilfe von zwei <xref:System.IO.FileStream> -Objekten Dateien asynchron aus einem Verzeichnis in ein anderes kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="a33bf-117">The following example demonstrates how to use two <xref:System.IO.FileStream> objects to copy files asynchronously from one directory to another.</span></span> <span data-ttu-id="a33bf-118">Beachten Sie, dass der <xref:System.Web.UI.WebControls.Button.Click> -Ereignishandler für das <xref:System.Windows.Controls.Button> -Steuerelement mit dem `async` -Modifizierer markiert wird, da er eine asynchrone Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="a33bf-118">Notice that the <xref:System.Web.UI.WebControls.Button.Click> event handler for the <xref:System.Windows.Controls.Button> control is marked with the `async` modifier because it calls an asynchronous method.</span></span>

[!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
[!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]

<span data-ttu-id="a33bf-119">Das folgende Beispiel ähnelt dem vorherigen, allerdings werden <xref:System.IO.StreamReader> - und <xref:System.IO.StreamWriter> -Objekte verwendet, um den Inhalt einer Textdatei asynchron zu lesen und zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a33bf-119">The next example is similar to the previous one but uses <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> objects to read and write the contents of a text file asynchronously.</span></span>

[!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
[!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]

<span data-ttu-id="a33bf-120">Das folgende Beispiel zeigt die CodeBehind-Datei und die XAML-Datei, die verwendet werden, um eine Datei als <xref:System.IO.Stream> in einer Windows 8.x Store-App zu öffnen und ihren Inhalt unter Verwendung einer Instanz der <xref:System.IO.StreamReader>-Klasse zu lesen.</span><span class="sxs-lookup"><span data-stu-id="a33bf-120">The next example shows the code-behind file and the XAML file that are used to open a file as a <xref:System.IO.Stream> in a Windows 8.x Store app, and read its contents by using an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="a33bf-121">Im Beispiel werden asynchrone Methoden verwendet, um die Datei als Stream zu öffnen und ihren Inhalt zu lesen.</span><span class="sxs-lookup"><span data-stu-id="a33bf-121">It uses asynchronous methods to open the file as a stream and to read its contents.</span></span>

[!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
[!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]

[!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="a33bf-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a33bf-122">See also</span></span>

- <xref:System.IO.Stream>
- [<span data-ttu-id="a33bf-123">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="a33bf-123">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="a33bf-124">Asynchrone Programmierung mit Async und Await (C#)</span><span class="sxs-lookup"><span data-stu-id="a33bf-124">Asynchronous programming with async and await (C#)</span></span>](../../csharp/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="a33bf-125">Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a33bf-125">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
