---
title: 'Gewusst wie: Schreiben von Text in eine Datei'
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
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea0ff0d79762ba47214217a261a325aad9f5eaf6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="70e84-102">Gewusst wie: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="70e84-102">How to: Write Text to a File</span></span>
<span data-ttu-id="70e84-103">Dieses Thema veranschaulicht verschiedene Arten, wie Sie Text in eine Datei für .NET Framework-Anwendungen oder [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -Apps schreiben können.</span><span class="sxs-lookup"><span data-stu-id="70e84-103">This topic shows different ways you can write text to a file for .NET Framework applications or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="70e84-104">Die folgenden Klassen und Methoden werden in der Regel zum Schreiben von Text in eine Datei verwendet:</span><span class="sxs-lookup"><span data-stu-id="70e84-104">The following classes and methods are typically used to write text to a file:</span></span>  
  
-   <span data-ttu-id="70e84-105"><xref:System.IO.StreamWriter> enthält Methoden zum synchronen (<xref:System.IO.StreamWriter.Write%2A> oder <xref:System.IO.TextWriter.WriteLine%2A>) oder asynchronen (<xref:System.IO.StreamWriter.WriteAsync%2A> und <xref:System.IO.StreamWriter.WriteLineAsync%2A>) Schreiben in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="70e84-105"><xref:System.IO.StreamWriter> - it contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> or <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
-   <span data-ttu-id="70e84-106"><xref:System.IO.File> wird für .NET Framework-Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="70e84-106"><xref:System.IO.File> – to be used with .NET Framework applications.</span></span> <span data-ttu-id="70e84-107">Sie stellt statische Methoden zum Schreiben von Text in eine Datei ( <xref:System.IO.File.WriteAllLines%2A> und <xref:System.IO.File.WriteAllText%2A>) oder zum Anfügen von Text an eine Datei (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> oder <xref:System.IO.File.AppendText%2A>) bereit.</span><span class="sxs-lookup"><span data-stu-id="70e84-107">It provides static methods to write text to a file such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> or <xref:System.IO.File.AppendText%2A>).</span></span>  
  
-   <span data-ttu-id="70e84-108">[FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) wird mit [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -Apps verwendet.</span><span class="sxs-lookup"><span data-stu-id="70e84-108">[FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) - to be used with [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="70e84-109">Sie enthält asynchrone Methoden zum Schreiben von Text in eine Datei ([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) oder [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)) bzw. zum Anfügen von Text an eine Datei ([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) oder [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)).</span><span class="sxs-lookup"><span data-stu-id="70e84-109">It contains asynchronous methods to write text to a file ([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) or [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)) or to append text to a file ([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) or [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)).</span></span>  
  
 <span data-ttu-id="70e84-110">Die Beispiele sind einfach gehalten, um nicht von der ausgeführten Aufgabe abzulenken.</span><span class="sxs-lookup"><span data-stu-id="70e84-110">The samples have been kept simple in order to focus on the task being performed.</span></span> <span data-ttu-id="70e84-111">Aus diesem Grund wird in den Beispielen, falls überhaupt, nur eine geringe Fehlerüberprüfung und Ausnahmebehandlung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="70e84-111">For this reason, the samples perform minimal error checking and exception handling, if any.</span></span> <span data-ttu-id="70e84-112">Reale Anwendungen umfassen im Allgemeinen eine robustere Fehlerüberprüfung und Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="70e84-112">A real-world application generally provides more robust error checking and exception handling.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70e84-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70e84-113">Example</span></span>  
 <span data-ttu-id="70e84-114">Im folgenden Beispiel wird gezeigt, wie Sie Text mithilfe der <xref:System.IO.StreamWriter> -Klasse zeilenweise in eine neue Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="70e84-114">The following example shows how to synchronously write text to a new file using the <xref:System.IO.StreamWriter> class, one line at a time.</span></span> <span data-ttu-id="70e84-115">Die neue Textdatei wird im Ordner "Eigene Dateien" des Benutzers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="70e84-115">The new text file is saved to the user's My Documents folder.</span></span> <span data-ttu-id="70e84-116">Da das <xref:System.IO.StreamWriter> -Objekt in einer `using` -Anweisung deklariert und instanziiert wird, wird die <xref:System.IO.StreamWriter.Dispose%2A> -Methode zum automatischen Leeren und Schließen des Datenstroms aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="70e84-116">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked which automatically flushes and closes the stream.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  
  
## <a name="example"></a><span data-ttu-id="70e84-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70e84-117">Example</span></span>  
 <span data-ttu-id="70e84-118">Das folgende Beispiel zeigt, wie Text mithilfe der <xref:System.IO.StreamWriter> -Klasse an eine vorhandene Datei angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="70e84-118">The following example shows how to append text to an existing file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="70e84-119">Dabei wird die Textdatei aus dem vorherigen Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="70e84-119">It uses the same text file from the previous example.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]     
  
## <a name="example"></a><span data-ttu-id="70e84-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70e84-120">Example</span></span>  
 <span data-ttu-id="70e84-121">Das folgende Beispiel zeigt, wie Sie Text mithilfe der <xref:System.IO.StreamWriter> -Klasse asynchron in eine neue Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="70e84-121">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="70e84-122">Zum Aufrufen der <xref:System.IO.StreamWriter.WriteAsync%2A> -Methode muss sich der Methodenaufruf innerhalb einer `async` -Methode befinden.</span><span class="sxs-lookup"><span data-stu-id="70e84-122">In order to invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call needs to be within an `async` method.</span></span> <span data-ttu-id="70e84-123">Die neue Textdatei wird im Ordner "Eigene Dateien" des Benutzers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="70e84-123">The new text file is saved to the user's My Documents folder.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## <a name="example"></a><span data-ttu-id="70e84-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70e84-124">Example</span></span>  
 <span data-ttu-id="70e84-125">Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.File> -Klasse Text in eine neue Datei schreiben und neue Textzeilen an diese Datei anfügen.</span><span class="sxs-lookup"><span data-stu-id="70e84-125">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="70e84-126">Durch die Methoden <xref:System.IO.File.WriteAllText%2A> und <xref:System.IO.File.AppendAllLines%2A> wird die Datei automatisch geöffnet und geschlossen.</span><span class="sxs-lookup"><span data-stu-id="70e84-126">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="70e84-127">Wenn der für die <xref:System.IO.File.WriteAllText%2A> -Methode angegebene Pfad bereits vorhanden ist, wird die Datei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="70e84-127">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file will be overwritten.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## <a name="example"></a><span data-ttu-id="70e84-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70e84-128">Example</span></span>  
 <span data-ttu-id="70e84-129">Im folgenden Beispiel wird veranschaulicht, wie Benutzereingaben asynchron in eine Textdatei in einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -App geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="70e84-129">The following example shows how to asynchronously write user input to a text file in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span> <span data-ttu-id="70e84-130">Aus Sicherheitsgründen muss in der Regel ein [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] FileOpenPicker [-Steuerelement verwendet werden, wenn eine Datei von einer](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx) -App geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="70e84-130">Because of security considerations, opening a file from a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app typically requires the use of a [FileOpenPicker](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx) control.</span></span> <span data-ttu-id="70e84-131">In diesem Beispiel wird `FileOpenPicker` nach Textdateien gefiltert.</span><span class="sxs-lookup"><span data-stu-id="70e84-131">In this example, the `FileOpenPicker` is filtered to show text files.</span></span>  
  
```xaml  
<Page  
    x:Class="OpenFileWindowsStore.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:OpenFileWindowsStore"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Button Content="save text to a file" HorizontalAlignment="Left" Margin="103,417,0,0" VerticalAlignment="Top"   
                Width="329" Height="86" FontSize="35" Click="Button_Click"/>  
        <TextBox Name="UserInputTextBox"  FontSize="18" HorizontalAlignment="Left" Margin="106,146,0,0"   
                 TextWrapping="Wrap" Text="Write some text here, and select a file to write it to." VerticalAlignment="Top"   
                 Height="201" Width="558" AcceptsReturn="True"/>  
        <TextBlock Name="StatusTextBox" HorizontalAlignment="Left" Margin="106,570,0,147" TextWrapping="Wrap" Text="Status:"   
                   VerticalAlignment="Center" Height="51" Width="1074" FontSize="18" />  
    </Grid>  
</Page>  
```  
  
 [!code-csharp[OpenFileWindowsStore#Code](../../../samples/snippets/csharp/VS_Snippets_CLR/openfilewindowsstore/cs/mainpage.xaml.cs#code)]
 [!code-vb[OpenFileWindowsStore#Code](../../../samples/snippets/visualbasic/VS_Snippets_CLR/openfilewindowsstore/vb/mainpage.xaml.vb#code)]  
  
## <a name="see-also"></a><span data-ttu-id="70e84-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70e84-132">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="70e84-133">Gewusst wie: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="70e84-133">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="70e84-134">Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei</span><span class="sxs-lookup"><span data-stu-id="70e84-134">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="70e84-135">Gewusst wie: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="70e84-135">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="70e84-136">Gewusst wie: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="70e84-136">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="70e84-137">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="70e84-137">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
