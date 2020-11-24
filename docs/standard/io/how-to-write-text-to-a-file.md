---
title: 'Vorgehensweise: Schreiben von Text in eine Datei'
description: Lernen Sie Methoden kennen, um Text in eine Datei für eine .NET-App zu schreiben. Verwenden Sie Methoden der StreamWriter- oder File-Klassen, um Text synchron oder asynchron zu schreiben.
ms.date: 01/04/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
ms.openlocfilehash: bd9abc2aac4b02f71e41f71e518a76b2477420da
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829712"
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="8c100-104">Vorgehensweise: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="8c100-104">How to: Write text to a file</span></span>

<span data-ttu-id="8c100-105">In diesem Artikel werden verschiedene Vorgehensweisen zum Schreiben von Text in eine Datei für eine .NET-Anwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8c100-105">This topic shows different ways to write text to a file for a .NET app.</span></span>

<span data-ttu-id="8c100-106">Die folgenden Klassen und Methoden werden in der Regel zum Schreiben von Text in eine Datei verwendet:</span><span class="sxs-lookup"><span data-stu-id="8c100-106">The following classes and methods are typically used to write text to a file:</span></span>  
  
- <span data-ttu-id="8c100-107"><xref:System.IO.StreamWriter> enthält Methoden zum synchronen (<xref:System.IO.StreamWriter.Write%2A> und <xref:System.IO.TextWriter.WriteLine%2A>) oder asynchronen (<xref:System.IO.StreamWriter.WriteAsync%2A> und <xref:System.IO.StreamWriter.WriteLineAsync%2A>) Schreiben in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="8c100-107"><xref:System.IO.StreamWriter> contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> and <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
- <span data-ttu-id="8c100-108"><xref:System.IO.File> stellt statische Methoden zum Schreiben von Text in eine Datei (z. B. <xref:System.IO.File.WriteAllLines%2A> und <xref:System.IO.File.WriteAllText%2A>) oder zum Anfügen von Text an eine Datei (z. B. <xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> und <xref:System.IO.File.AppendText%2A>) bereit.</span><span class="sxs-lookup"><span data-stu-id="8c100-108"><xref:System.IO.File> provides static methods to write text to a file, such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file, such as <xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A>, and <xref:System.IO.File.AppendText%2A>.</span></span>  
  
- <span data-ttu-id="8c100-109"><xref:System.IO.Path> wird für Zeichenfolgen verwendet, die Informationen zu Datei- oder Verzeichnispfaden enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c100-109"><xref:System.IO.Path> is for strings that have file or directory path information.</span></span> <span data-ttu-id="8c100-110">Diese Klasse enthält die <xref:System.IO.Path.Combine%2A>-Methode und ab .NET Core 2.1 die Methoden <xref:System.IO.Path.Join%2A> und <xref:System.IO.Path.TryJoin%2A>, mit denen die Verkettung von Zeichenfolgen zum Erstellen eines Datei- oder Verzeichnispfads ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="8c100-110">It contains the <xref:System.IO.Path.Combine%2A> method and, in .NET Core 2.1 and later, the <xref:System.IO.Path.Join%2A> and <xref:System.IO.Path.TryJoin%2A> methods, which allow concatenation of strings to build a file or directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="8c100-111">In den folgenden Beispielen wird nur das Mindeste des erforderlichen Codes veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8c100-111">The following examples show only the minimum amount of code needed.</span></span> <span data-ttu-id="8c100-112">Reale Anwendungen umfassen im Allgemeinen eine robustere Fehlerüberprüfung und Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="8c100-112">A real-world app usually provides more robust error checking and exception handling.</span></span>  
  
## <a name="example-synchronously-write-text-with-streamwriter"></a><span data-ttu-id="8c100-113">Beispiel: Synchrones Schreiben von Text mit StreamWriter</span><span class="sxs-lookup"><span data-stu-id="8c100-113">Example: Synchronously write text with StreamWriter</span></span>

<span data-ttu-id="8c100-114">Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.IO.StreamWriter>-Klasse verwenden, um Text zeilenweise synchron in eine neue Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8c100-114">The following example shows how to use the <xref:System.IO.StreamWriter> class to synchronously write text to a new file one line at a time.</span></span> <span data-ttu-id="8c100-115">Da das <xref:System.IO.StreamWriter>-Objekt in einer `using`-Anweisung deklariert und instanziiert ist, wird die <xref:System.IO.StreamWriter.Dispose%2A>-Methode aufgerufen, die den Datenstrom automatisch leert und beendet.</span><span class="sxs-lookup"><span data-stu-id="8c100-115">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked, which automatically flushes and closes the stream.</span></span>  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/write.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/write.vb)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="example-synchronously-append-text-with-streamwriter"></a><span data-ttu-id="8c100-116">Beispiel: Synchrones Anfügen von Text mit StreamWriter</span><span class="sxs-lookup"><span data-stu-id="8c100-116">Example: Synchronously append text with StreamWriter</span></span>

<span data-ttu-id="8c100-117">Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.IO.StreamWriter>-Klasse verwenden, um Text synchron an die Textdatei anzufügen, die im ersten Beispiel erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8c100-117">The following example shows how to use the <xref:System.IO.StreamWriter> class to synchronously append text to the text file created in the first example.</span></span>

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/append.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/append.vb)]  

## <a name="example-asynchronously-write-text-with-streamwriter"></a><span data-ttu-id="8c100-118">Beispiel: Asynchrones Schreiben von Text mit StreamWriter</span><span class="sxs-lookup"><span data-stu-id="8c100-118">Example: Asynchronously write text with StreamWriter</span></span>

<span data-ttu-id="8c100-119">Das folgende Beispiel zeigt, wie Sie Text mithilfe der <xref:System.IO.StreamWriter> -Klasse asynchron in eine neue Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="8c100-119">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="8c100-120">Der Methodenaufruf muss sich innerhalb einer `async`-Methode befinden, um die <xref:System.IO.StreamWriter.WriteAsync%2A>-Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8c100-120">To invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call must be within an `async` method.</span></span> <span data-ttu-id="8c100-121">Für das C#-Beispiel ist C# 7.1 oder höher erforderlich, da der Programmeinstiegspunkt den `async`-Modifizierer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c100-121">The C# example requires C# 7.1 or later, which adds support for the `async` modifier on the program entry point.</span></span>

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/async.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/async.vb)]  

## <a name="example-write-and-append-text-with-the-file-class"></a><span data-ttu-id="8c100-122">Beispiel: Schreiben und Anfügen von Text mit der File-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c100-122">Example: Write and append text with the File class</span></span>

<span data-ttu-id="8c100-123">Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.File> -Klasse Text in eine neue Datei schreiben und neue Textzeilen an diese Datei anfügen.</span><span class="sxs-lookup"><span data-stu-id="8c100-123">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="8c100-124">Durch die Methoden <xref:System.IO.File.WriteAllText%2A> und <xref:System.IO.File.AppendAllLines%2A> wird die Datei automatisch geöffnet und geschlossen.</span><span class="sxs-lookup"><span data-stu-id="8c100-124">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="8c100-125">Wenn der für die <xref:System.IO.File.WriteAllText%2A> -Methode angegebene Pfad bereits vorhanden ist, wird die Datei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c100-125">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file is overwritten.</span></span>  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/file.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/file.vb)]  

## <a name="see-also"></a><span data-ttu-id="8c100-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c100-126">See also</span></span>

- <xref:System.IO.StreamWriter>
- <xref:System.IO.Path>
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8c100-127">How to: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="8c100-127">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)
- [<span data-ttu-id="8c100-128">How to: Lesen von bzw. Schreiben in eine neu erstellte Datendatei</span><span class="sxs-lookup"><span data-stu-id="8c100-128">How to: Read and write to a newly-created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)
- [<span data-ttu-id="8c100-129">How to: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="8c100-129">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)
- [<span data-ttu-id="8c100-130">How to: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="8c100-130">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)
- [<span data-ttu-id="8c100-131">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="8c100-131">File and stream I/O</span></span>](index.md)
