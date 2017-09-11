---
title: "Verwenden von Async für Dateizugriff (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 85f5fe17a012402c406eed972debd1f5889dd393
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="using-async-for-file-access-visual-basic"></a><span data-ttu-id="9f8cb-102">Using Async for File Access (Visual Basic) (Verwenden von Async für Dateizugriff (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9f8cb-102">Using Async for File Access (Visual Basic)</span></span>
<span data-ttu-id="9f8cb-103">Sie können die Async-Funktion verwenden, auf Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-103">You can use the Async feature to access files.</span></span> <span data-ttu-id="9f8cb-104">Mithilfe der Async-Funktion können Sie asynchrone Methoden aufrufen, ohne Rückrufe zu verwenden oder den Code über mehrere Methoden oder Lambdaausdrücke teilen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-104">By using the Async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="9f8cb-105">Um synchronen Code asynchron auszuführen, Sie nur eine asynchrone Methode anstelle einer synchronen Methode aufrufen und dem Code einige Schlüsselwörter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-105">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="9f8cb-106">Sie sollten die folgenden Gründe für die Datei Aufrufe Asynchronie hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9f8cb-106">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
-   <span data-ttu-id="9f8cb-107">Asynchronie können UI-Anwendungen besser, da der UI-Thread, der den Vorgang startet, andere Aufgaben durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-107">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="9f8cb-108">Wenn Code im UI-Thread ausgeführt werden muss, die viel Zeit (z. B. mehr als 50 Millisekunden), die Benutzeroberfläche reagiert möglicherweise nicht mehr, bis die e/a abgeschlossen ist, und im UI-Thread erneut verarbeiten Tastatur und Maus Eingabe- und andere Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-108">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
-   <span data-ttu-id="9f8cb-109">Asynchronie verbessert die Skalierbarkeit von ASP.NET und andere serverbasierte Anwendung, indem reduziert die Notwendigkeit für Threads.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-109">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="9f8cb-110">Wenn die Anwendung einen dedizierten Thread pro Antwort verwendet Tausend Anforderungen gleichzeitig verarbeitet werden werden, sind mehr als tausend Threads erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-110">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="9f8cb-111">Asynchrone Vorgänge müssen häufig einen Thread während der Wartezeit zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-111">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="9f8cb-112">Verwendung der vorhandene e/a-Abschlussthread kurz am Ende.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-112">They use the existing I/O completion thread briefly at the end.</span></span>  
  
-   <span data-ttu-id="9f8cb-113">Die Latenz von Dateien Zugriff kann nur noch sehr wenig aktuelle ausgelastet sein, aber die Wartezeit kann in Zukunft beträchtlich.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-113">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="9f8cb-114">Beispielsweise kann eine Datei auf einen Server verschoben werden, die auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-114">For example, a file may be moved to a server that's across the world.</span></span>  
  
-   <span data-ttu-id="9f8cb-115">Der zusätzliche Verwaltungsaufwand durch Verwendung der Async-Funktion klein ist.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-115">The added overhead of using the Async feature is small.</span></span>  
  
-   <span data-ttu-id="9f8cb-116">Asynchrone Aufgaben können problemlos parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-116">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="9f8cb-117">Ausführen der Beispiele</span><span class="sxs-lookup"><span data-stu-id="9f8cb-117">Running the Examples</span></span>  
 <span data-ttu-id="9f8cb-118">Zum Ausführen der Beispiele in diesem Thema erstellen Sie eine **WPF-Anwendung** oder **Windows Forms-Anwendung** und fügen Sie dann eine **Schaltfläche**.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-118">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="9f8cb-119">Die Schaltfläche `Click` Ereignis, fügen Sie einen Aufruf an die erste Methode in jedem Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-119">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="9f8cb-120">In den folgenden Beispielen gehören `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-120">In the following examples, include the following `Imports` statements.</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="9f8cb-121">Verwenden der FileStream-Klasse</span><span class="sxs-lookup"><span data-stu-id="9f8cb-121">Use of the FileStream Class</span></span>  
 <span data-ttu-id="9f8cb-122">In den Beispielen in diesem Thema die <xref:System.IO.FileStream>-Klasse, die Option verfügt, die bewirkt, dass asynchrone e/a auf der Betriebssystemebene auftreten.</xref:System.IO.FileStream></span><span class="sxs-lookup"><span data-stu-id="9f8cb-122">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="9f8cb-123">Mit dieser Option können Sie die Blockierung von einem Threadpool in vielen Fällen vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-123">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="9f8cb-124">Wenn Sie diese Option aktivieren, geben Sie die `useAsync=true` oder `options=FileOptions.Asynchronous` Argument im Konstruktoraufruf.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-124">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="9f8cb-125">Diese Option können Sie keine und <xref:System.IO.StreamReader> <xref:System.IO.StreamWriter>Öffnen sie direkt, indem Sie einen Dateipfad angeben</xref:System.IO.StreamWriter> </xref:System.IO.StreamReader></span><span class="sxs-lookup"><span data-stu-id="9f8cb-125">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="9f8cb-126">Allerdings können Sie diese Option verwenden, wenn Sie ihnen geben eine <xref:System.IO.Stream>, die <xref:System.IO.FileStream>Klasse geöffnet.</xref:System.IO.FileStream> </xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="9f8cb-126">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="9f8cb-127">Beachten Sie, dass asynchrone Aufrufe in Anwendungsbenutzeroberflächen schneller sind, selbst wenn ein ThreadPool-Thread blockiert wird, da während der Wartezeit nicht im UI-Thread blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-127">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="9f8cb-128">Schreiben von Text</span><span class="sxs-lookup"><span data-stu-id="9f8cb-128">Writing Text</span></span>  
 <span data-ttu-id="9f8cb-129">Das folgende Beispiel schreibt Text in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-129">The following example writes text to a file.</span></span> <span data-ttu-id="9f8cb-130">An jedem await-Anweisung, die Methode sofort beendet.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-130">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="9f8cb-131">Wenn die Datei-e/a abgeschlossen ist, wird die Methode bei der Anweisung, die die Await-Anweisung folgt fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-131">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="9f8cb-132">Beachten Sie, dass die Async-Modifizierer in der Definition der Methoden, die die Await-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-132">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
```vb  
Public Async Sub ProcessWrite()  
    Dim filePath = "temp2.txt"  
    Dim text = "Hello World" & ControlChars.CrLf  
  
    Await WriteTextAsync(filePath, text)  
End Sub  
  
Private Async Function WriteTextAsync(filePath As String, text As String) As Task  
    Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize:=4096, useAsync:=True)  
  
        Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
    End Using  
End Function  
```  
  
 <span data-ttu-id="9f8cb-133">Das ursprüngliche Beispiel wurde die Anweisung `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, also ein Zusammenschluss der beiden folgenden Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="9f8cb-133">The original example has the statement `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, which is a contraction of the following two statements:</span></span>  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 <span data-ttu-id="9f8cb-134">Die erste Anweisung eine Aufgabe zurück und bewirkt die dateiverarbeitung zu starten.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-134">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="9f8cb-135">Die zweite Anweisung mit der "await" bewirkt, dass die Methode sofort beendet und eine andere Aufgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-135">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="9f8cb-136">Wenn die Datei später Verarbeitung abgeschlossen ist, gibt die Ausführung an die Anweisung nach dem await-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-136">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="9f8cb-137">Weitere Informationen finden Sie unter [Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="9f8cb-137">For more information, see  [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="9f8cb-138">Lesen von Text</span><span class="sxs-lookup"><span data-stu-id="9f8cb-138">Reading Text</span></span>  
 <span data-ttu-id="9f8cb-139">Im folgenden Beispiel wird Text aus einer Datei gelesen.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-139">The following example reads text from a file.</span></span> <span data-ttu-id="9f8cb-140">Der Text wird gepuffert und in diesem Fall eine <xref:System.Text.StringBuilder>.</xref:System.Text.StringBuilder> abgelegt</span><span class="sxs-lookup"><span data-stu-id="9f8cb-140">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="9f8cb-141">Im Gegensatz zu im vorherigen Beispiel erzeugt die Auswertung der await-Ausdruck einen Wert.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-141">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="9f8cb-142">Die <xref:System.IO.Stream.ReadAsync%2A>-Methode gibt ein <xref:System.Threading.Tasks.Task> \< <xref:System.Int32>>, sodass die Auswertung der await-Anweisung erzeugt einen `Int32` Wert (`numRead`) nach Abschluss des Vorgangs.</xref:System.Int32> </xref:System.Threading.Tasks.Task> </xref:System.IO.Stream.ReadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="9f8cb-142">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="9f8cb-143">Weitere Informationen finden Sie unter [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="9f8cb-143">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
```vb  
Public Async Sub ProcessRead()  
    Dim filePath = "temp2.txt"  
  
    If File.Exists(filePath) = False Then  
        Debug.WriteLine("file not found: " & filePath)  
    Else  
        Try  
            Dim text As String = Await ReadTextAsync(filePath)  
            Debug.WriteLine(text)  
        Catch ex As Exception  
            Debug.WriteLine(ex.Message)  
        End Try  
    End If  
End Sub  
  
Private Async Function ReadTextAsync(filePath As String) As Task(Of String)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize:=4096, useAsync:=True)  
  
        Dim sb As New StringBuilder  
  
        Dim buffer As Byte() = New Byte(&H1000) {}  
        Dim numRead As Integer  
        numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        While numRead <> 0  
            Dim text As String = Encoding.Unicode.GetString(buffer, 0, numRead)  
            sb.Append(text)  
  
            numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        End While  
  
        Return sb.ToString  
    End Using  
End Function  
```  
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="9f8cb-144">Parallele asynchrone e/a</span><span class="sxs-lookup"><span data-stu-id="9f8cb-144">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="9f8cb-145">Das folgende Beispiel zeigt die parallelen Verarbeitung von 10 Textdateien schreiben.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-145">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="9f8cb-146">Für jede Datei die <xref:System.IO.Stream.WriteAsync%2A>-Methode gibt einen Task, der eine Liste von Aufgaben hinzugefügt wird.</xref:System.IO.Stream.WriteAsync%2A></span><span class="sxs-lookup"><span data-stu-id="9f8cb-146">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="9f8cb-147">Die `Await Task.WhenAll(tasks)` Anweisung wird die Methode beendet und nimmt innerhalb der Methode, wenn die dateiverarbeitung ist für alle Aufgaben abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-147">The `Await Task.WhenAll(tasks)` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="9f8cb-148">Das Beispiel schließt alle <xref:System.IO.FileStream>Instanzen in einer `Finally` blockieren, wenn die Aufgaben abgeschlossen sind.</xref:System.IO.FileStream></span><span class="sxs-lookup"><span data-stu-id="9f8cb-148">The example closes all <xref:System.IO.FileStream> instances in a `Finally` block after the tasks are complete.</span></span> <span data-ttu-id="9f8cb-149">Wenn alle `FileStream` wurde stattdessen erstellt eine `Imports` -Anweisung, die `FileStream` möglicherweise der verworfen werden, bevor der Task abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-149">If each `FileStream` was instead created in a `Imports` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="9f8cb-150">Beachten Sie, dass Leistungssteigerung fast vollständig von der parallelen Verarbeitung und nicht die asynchrone Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-150">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="9f8cb-151">Die Vorteile der Asynchronie sind, dass es mehreren Threads blockieren nicht, und es Thread der Benutzeroberfläche gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="9f8cb-151">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
```vb  
Public Async Sub ProcessWriteMult()  
    Dim folder = "tempfolder\"  
    Dim tasks As New List(Of Task)  
    Dim sourceStreams As New List(Of FileStream)  
  
    Try  
        For index = 1 To 10  
            Dim text = "In file " & index.ToString & ControlChars.CrLf  
  
            Dim fileName = "thefile" & index.ToString("00") & ".txt"  
            Dim filePath = folder & fileName  
  
            Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
            Dim sourceStream As New FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize:=4096, useAsync:=True)  
  
            Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
            sourceStreams.Add(sourceStream)  
  
            tasks.Add(theTask)  
        Next  
  
        Await Task.WhenAll(tasks)  
    Finally  
        For Each sourceStream As FileStream In sourceStreams  
            sourceStream.Close()  
        Next  
    End Try  
End Sub  
```  
  
 <span data-ttu-id="9f8cb-152">Bei Verwendung der <xref:System.IO.Stream.WriteAsync%2A>und <xref:System.IO.Stream.ReadAsync%2A>Methoden können Sie angeben, einen <xref:System.Threading.CancellationToken>, mit Mid-Streams Vorgang abbrechen.</xref:System.Threading.CancellationToken> </xref:System.IO.Stream.ReadAsync%2A> </xref:System.IO.Stream.WriteAsync%2A></span><span class="sxs-lookup"><span data-stu-id="9f8cb-152">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="9f8cb-153">Weitere Informationen finden Sie unter [Optimieren der asynchronen Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) und [Abbruch in verwalteten Threads](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).</span><span class="sxs-lookup"><span data-stu-id="9f8cb-153">For more information, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8cb-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f8cb-154">See Also</span></span>  
 <span data-ttu-id="9f8cb-155">[Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f8cb-155">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="9f8cb-156"> [Asynchrone Rückgabetypen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="9f8cb-156"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="9f8cb-157"> [Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)</span><span class="sxs-lookup"><span data-stu-id="9f8cb-157"> [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)</span></span>
