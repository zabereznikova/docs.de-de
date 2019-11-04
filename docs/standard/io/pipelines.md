---
title: 'E/A-Pipelines: .NET'
description: Erfahren Sie, wie Sie E/A-Pipelines in .NET effizient verwenden und Probleme im Code vermeiden können.
ms.date: 10/01/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: 54b5f97aca131f52b9b5d9f54d7fa5ec00ba3d5b
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423678"
---
# <a name="systemiopipelines-in-net"></a><span data-ttu-id="76e73-103">System.IO.Pipelines in .NET</span><span class="sxs-lookup"><span data-stu-id="76e73-103">System.IO.Pipelines in .NET</span></span>

<span data-ttu-id="76e73-104"><xref:System.IO.Pipelines> ist eine neue Bibliothek, die entwickelt wurde, um die Ausführung von Hochleistungs-E/A in .NET zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="76e73-104"><xref:System.IO.Pipelines> is a new library that is designed to make it easier to do high-performance I/O in .NET.</span></span> <span data-ttu-id="76e73-105">Dabei handelt es sich um eine Bibliothek für .NET Standard, die für alle .NET-Implementierungen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="76e73-105">It’s a library targeting .NET Standard that works on all .NET implementations.</span></span>

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a><span data-ttu-id="76e73-106">Von System.IO.Pipelines gelöste Probleme</span><span class="sxs-lookup"><span data-stu-id="76e73-106">What problem does System.IO.Pipelines solve</span></span>

<!-- corner case doesn't MT (machine translate)   -->
<span data-ttu-id="76e73-107">Apps, die Streamingdaten analysieren, bestehen aus Codebausteinen, die über viele spezialisierte und ungewöhnliche Codeflows verfügen.</span><span class="sxs-lookup"><span data-stu-id="76e73-107">Apps that parse streaming data are composed of boilerplate code having many specialized and unusual code flows.</span></span> <span data-ttu-id="76e73-108">Die Codebausteine und der Sonderfallcode sind komplex und schwer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="76e73-108">The boilerplate and special case code is complex and difficult to maintain.</span></span>

<span data-ttu-id="76e73-109">`System.IO.Pipelines` soll Folgendes ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="76e73-109">`System.IO.Pipelines` was architected to:</span></span>

* <span data-ttu-id="76e73-110">Hochleistungsanalyse von Streamingdaten.</span><span class="sxs-lookup"><span data-stu-id="76e73-110">Have high performance parsing streaming data.</span></span>
* <span data-ttu-id="76e73-111">Verringern der Komplexität von Code.</span><span class="sxs-lookup"><span data-stu-id="76e73-111">Reduce code complexity.</span></span>

<span data-ttu-id="76e73-112">Der folgende Code ist typisch für einen TCP-Server, der durch Zeilen getrennte Nachrichten (getrennt durch `'\n'`) von einem Client empfängt:</span><span class="sxs-lookup"><span data-stu-id="76e73-112">The following code is typical for a TCP server that receives line-delimited messages (delimited by `'\n'`) from a client:</span></span>

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

<span data-ttu-id="76e73-113">Der vorstehende Code weist mehrere Probleme auf:</span><span class="sxs-lookup"><span data-stu-id="76e73-113">The preceding code has several problems:</span></span>

* <span data-ttu-id="76e73-114">Die gesamte Nachricht (Zeilenende) wird möglicherweise nicht in einem einzigen Aufruf von `ReadAsync` empfangen.</span><span class="sxs-lookup"><span data-stu-id="76e73-114">The entire message (end of line) might not be received in a single call to `ReadAsync`.</span></span>
* <span data-ttu-id="76e73-115">Das Ergebnis von `stream.ReadAsync` wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="76e73-115">It's ignoring the result of `stream.ReadAsync`.</span></span> <span data-ttu-id="76e73-116">`stream.ReadAsync` gibt zurück, wie viele Daten gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="76e73-116">`stream.ReadAsync` returns how much data was read.</span></span>
* <span data-ttu-id="76e73-117">Der Fall, in dem mehrere Zeilen in einem einzigen Aufruf von `ReadAsync` gelesen werden, wird nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="76e73-117">It doesn't handle the case where multiple lines are read in a single `ReadAsync` call.</span></span>
* <span data-ttu-id="76e73-118">Es wird bei jedem Lesevorgang ein `byte`-Array zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="76e73-118">It allocates a `byte` array with each read.</span></span>

<span data-ttu-id="76e73-119">Um die oben beschriebenen Probleme zu beheben, sind die folgenden Änderungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="76e73-119">To fix the preceding problems, the following changes are required:</span></span>

* <span data-ttu-id="76e73-120">Puffern der eingehenden Daten, bis eine neue Zeile gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-120">Buffer the incoming data until a new line is found.</span></span>
* <span data-ttu-id="76e73-121">Analysieren aller zurückgegebenen Zeilen im Puffer.</span><span class="sxs-lookup"><span data-stu-id="76e73-121">Parse all the lines returned in the buffer.</span></span>
* <span data-ttu-id="76e73-122">Es ist möglich, dass die Zeile größer als 1 KB (1.024 Bytes) ist.</span><span class="sxs-lookup"><span data-stu-id="76e73-122">It's possible that the line is bigger than 1 KB (1024 bytes).</span></span> <span data-ttu-id="76e73-123">Der Code muss die Größe des Eingabepuffers ändern, bis das Trennzeichen gefunden wird, damit die gesamte Zeile in den Puffer passt.</span><span class="sxs-lookup"><span data-stu-id="76e73-123">The code needs to resize the input buffer until the delimiter is found in order to fit the complete line inside the buffer.</span></span>

  * <span data-ttu-id="76e73-124">Wenn die Größe des Puffers geändert wird, werden mehr Pufferkopien erstellt, weil in der Eingabe längere Zeilen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="76e73-124">If the buffer is resized, more buffer copies are made as longer lines appear in the input.</span></span>
  * <span data-ttu-id="76e73-125">Um unnötigen Speicherplatz zu sparen, komprimieren Sie den Puffer, der zum Lesen von Zeilen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-125">To reduce wasted space, compact the buffer used for reading lines.</span></span>

* <span data-ttu-id="76e73-126">Verwenden Sie ggf. Pufferpools, um zu vermeiden, dass wiederholt Speicher zugeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-126">Consider using buffer pooling to avoid allocating memory repeatedly.</span></span>
* <span data-ttu-id="76e73-127">Der folgende Code behandelt einige dieser Probleme:</span><span class="sxs-lookup"><span data-stu-id="76e73-127">The following code addresses some of these problems:</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs?name=snippet)]

<span data-ttu-id="76e73-128">Der oben gezeigte Code ist komplex und behandelt nicht alle identifizierten Probleme.</span><span class="sxs-lookup"><span data-stu-id="76e73-128">The previous code is complex and doesn't address all the problems identified.</span></span> <span data-ttu-id="76e73-129">Hochleistungsnetzwerke bedeuten in der Regel das Schreiben von sehr komplexem Code, um die Leistung zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="76e73-129">High-performance networking usually means writing very complex code to maximize performance.</span></span> <span data-ttu-id="76e73-130">`System.IO.Pipelines` wurde entworfen, um das Schreiben dieser Art von Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="76e73-130">`System.IO.Pipelines` was designed to make writing this type of code easier.</span></span>

## <a name="pipe"></a><span data-ttu-id="76e73-131">Pipe</span><span class="sxs-lookup"><span data-stu-id="76e73-131">Pipe</span></span>

<span data-ttu-id="76e73-132">Die <xref:System.IO.Pipelines.Pipe>-Klasse kann verwendet werden, um ein `PipeWriter/PipeReader`-Paar zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="76e73-132">The <xref:System.IO.Pipelines.Pipe> class can be used to create a `PipeWriter/PipeReader` pair.</span></span> <span data-ttu-id="76e73-133">Alle Daten, die in `PipeWriter` geschrieben werden, sind in `PipeReader` verfügbar:</span><span class="sxs-lookup"><span data-stu-id="76e73-133">All data written into the `PipeWriter` is available in the `PipeReader`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet2)]

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a><span data-ttu-id="76e73-134">Grundlegende Verwendung von Pipe</span><span class="sxs-lookup"><span data-stu-id="76e73-134">Pipe basic usage</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet)]

<span data-ttu-id="76e73-135">Es gibt zwei Schleifen:</span><span class="sxs-lookup"><span data-stu-id="76e73-135">There are two loops:</span></span>

* <span data-ttu-id="76e73-136">`FillPipeAsync` liest aus `Socket` und schreibt in `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="76e73-136">`FillPipeAsync` reads from the `Socket` and writes to the `PipeWriter`.</span></span>
* <span data-ttu-id="76e73-137">`ReadPipeAsync` liest aus `PipeReader` und analysiert eingehende Zeilen.</span><span class="sxs-lookup"><span data-stu-id="76e73-137">`ReadPipeAsync` reads from the `PipeReader` and parses incoming lines.</span></span>

<span data-ttu-id="76e73-138">Es sind keine expliziten Puffer zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="76e73-138">There are no explicit buffers allocated.</span></span> <span data-ttu-id="76e73-139">Die gesamte Pufferverwaltung wird an die `PipeReader`- und `PipeWriter`-Implementierungen delegiert.</span><span class="sxs-lookup"><span data-stu-id="76e73-139">All buffer management is delegated to the `PipeReader` and `PipeWriter` implementations.</span></span> <span data-ttu-id="76e73-140">Durch die Delegierung der Pufferverwaltung ist es für Daten verarbeitenden Code einfacher, sich ausschließlich auf die Geschäftslogik zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="76e73-140">Delegating buffer management makes it easier for consuming code to focus solely on the business logic.</span></span>

<span data-ttu-id="76e73-141">In der ersten Schleife geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="76e73-141">In the first loop:</span></span>

* <span data-ttu-id="76e73-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> wird aufgerufen, um Speicher vom zugrunde liegenden Writer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="76e73-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> is called to get memory from the underlying writer.</span></span>
* <span data-ttu-id="76e73-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> wird aufgerufen, um `PipeWriter` mitzuteilen, wie viele Daten in den Puffer geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="76e73-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> is called to tell the `PipeWriter` how much data was written to the buffer.</span></span>
* <span data-ttu-id="76e73-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> wird aufgerufen, um die Daten für `PipeReader` verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="76e73-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> is called to make the data available to the `PipeReader`.</span></span>

<span data-ttu-id="76e73-145">In der zweiten Schleife verarbeitet `PipeReader` die von `PipeWriter` geschriebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="76e73-145">In the second loop, the `PipeReader` consumes the buffers written by `PipeWriter`.</span></span> <span data-ttu-id="76e73-146">Die Puffer stammen aus dem Socket.</span><span class="sxs-lookup"><span data-stu-id="76e73-146">The buffers come from the socket.</span></span> <span data-ttu-id="76e73-147">Für den Aufruf von `PipeReader.ReadAsync` gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="76e73-147">The call to `PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="76e73-148">Er gibt ein <xref:System.IO.Pipelines.ReadResult> zurück, das zwei wichtige Informationen enthält:</span><span class="sxs-lookup"><span data-stu-id="76e73-148">Returns a <xref:System.IO.Pipelines.ReadResult> that contains two important pieces of information:</span></span>

  * <span data-ttu-id="76e73-149">Die gelesenen Daten in Form von `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="76e73-149">The data that was read in the form of `ReadOnlySequence<byte>`.</span></span>
  * <span data-ttu-id="76e73-150">Einen boolescher Wert `IsCompleted`, der angibt, ob das Ende der Daten (EOF) erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="76e73-150">A boolean `IsCompleted` that indicates if the end of data (EOF) has been reached.</span></span>

<span data-ttu-id="76e73-151">Nachdem das Zeilenende-Trennzeichen (EOL) gefunden und die Zeile analysiert wurde, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="76e73-151">After finding the end of line (EOL) delimiter and parsing the line:</span></span>

* <span data-ttu-id="76e73-152">Die Logik verarbeitet den Puffer, um die Daten zu überspringen, die bereits verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="76e73-152">The logic processes the buffer to skip what's already processed.</span></span>
* <span data-ttu-id="76e73-153">`PipeReader.AdvanceTo` wird aufgerufen, um `PipeReader` mitzuteilen, wie viele Daten verarbeitet und untersucht wurden.</span><span class="sxs-lookup"><span data-stu-id="76e73-153">`PipeReader.AdvanceTo` is called to tell the `PipeReader` how much data has been consumed and examined.</span></span>

<span data-ttu-id="76e73-154">Die Reader- und Writerschleifen werden durch den Aufruf von `Complete` beendet.</span><span class="sxs-lookup"><span data-stu-id="76e73-154">The reader and writer loops end by calling `Complete`.</span></span> <span data-ttu-id="76e73-155">`Complete` ermöglicht der zugrunde liegenden Pipe, den zugeordneten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="76e73-155">`Complete` lets the underlying Pipe release the memory it allocated.</span></span>

### <a name="backpressure-and-flow-control"></a><span data-ttu-id="76e73-156">Rückstau und Flusssteuerung</span><span class="sxs-lookup"><span data-stu-id="76e73-156">Backpressure and flow control</span></span>

<span data-ttu-id="76e73-157">Im Idealfall arbeiten die Lese- und Analysevorgänge zusammen:</span><span class="sxs-lookup"><span data-stu-id="76e73-157">Ideally, reading and parsing work together:</span></span>

* <span data-ttu-id="76e73-158">Der schreibende Thread nutzt Daten aus dem Netzwerk und speichert sie in Puffern.</span><span class="sxs-lookup"><span data-stu-id="76e73-158">The writing thread consumes data from the network and puts it in buffers.</span></span>
* <span data-ttu-id="76e73-159">Der analysierende Thread ist für das Erstellen der entsprechenden Datenstrukturen verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="76e73-159">The parsing thread is responsible for constructing the appropriate data structures.</span></span>

<span data-ttu-id="76e73-160">In der Regel nimmt die Analyse mehr Zeit als das Kopieren von Datenblöcken aus dem Netzwerk in Anspruch:</span><span class="sxs-lookup"><span data-stu-id="76e73-160">Typically, parsing takes more time than just copying blocks of data from the network:</span></span>

* <span data-ttu-id="76e73-161">Der lesende Thread überholt den analysierenden Thread.</span><span class="sxs-lookup"><span data-stu-id="76e73-161">The reading thread gets ahead of the parsing thread.</span></span>
* <span data-ttu-id="76e73-162">Der lesende Thread muss entweder langsamer werden oder mehr Speicher zuteilen, um die Daten für den analysierenden Thread zu speichern.</span><span class="sxs-lookup"><span data-stu-id="76e73-162">The reading thread has to either slow down or allocate more memory to store the data for the parsing thread.</span></span>

<span data-ttu-id="76e73-163">Für optimale Leistung ist ein Gleichgewicht zwischen häufigen Pausen und der Zuteilung von mehr Speicherplatz vorhanden.</span><span class="sxs-lookup"><span data-stu-id="76e73-163">For optimal performance, there's a balance between frequent pauses and allocating more memory.</span></span>

<span data-ttu-id="76e73-164">Zum Beheben des oben beschriebenen Problems hat `Pipe` zwei Einstellungen, um den Datenfluss zu steuern:</span><span class="sxs-lookup"><span data-stu-id="76e73-164">To solve the preceding problem, the `Pipe` has two settings to control the flow of data:</span></span>

* <span data-ttu-id="76e73-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Bestimmt, wie viele Daten gepuffert werden sollen, bevor für Aufrufe von <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> eine Pause eingelegt wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Determines how much data should be buffered before calls to <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> pause.</span></span>
* <span data-ttu-id="76e73-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Bestimmt, wie viele Daten der Reader untersuchen muss, bevor die Aufrufe von `PipeWriter.FlushAsync` fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Determines how much data the reader has to observe before calls to `PipeWriter.FlushAsync` resume.</span></span>

![Abbildung mit ResumeWriterThreshold und PauseWriterThreshold](./media/pipelines/resume-pause.png)

<span data-ttu-id="76e73-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="76e73-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="76e73-169">Gibt ein unvollständiges `ValueTask<FlushResult>` zurück, wenn die Datenmenge in `Pipe` `PauseWriterThreshold` erreicht.</span><span class="sxs-lookup"><span data-stu-id="76e73-169">Returns an incomplete `ValueTask<FlushResult>` when the amount of data in the `Pipe` crosses `PauseWriterThreshold`.</span></span>
* <span data-ttu-id="76e73-170">Schließt `ValueTask<FlushResult>` ab, wenn der Wert kleiner als `ResumeWriterThreshold` wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-170">Completes `ValueTask<FlushResult>` when it becomes lower than `ResumeWriterThreshold`.</span></span>

<span data-ttu-id="76e73-171">Es werden zwei Werte verwendet, um einen schnellen Zyklus zu verhindern, der bei Verwendung nur eines Werts auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="76e73-171">Two values are used to prevent rapid cycling, which can occur if one value is used.</span></span>

### <a name="examples"></a><span data-ttu-id="76e73-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="76e73-172">Examples</span></span>

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a><span data-ttu-id="76e73-173">PipeScheduler</span><span class="sxs-lookup"><span data-stu-id="76e73-173">PipeScheduler</span></span>

<span data-ttu-id="76e73-174">In der Regel wird der asynchrone Code bei Verwendung von `async` und `await` entweder für einen <xref:System.Threading.Tasks.TaskScheduler> oder den aktuellen <xref:System.Threading.SynchronizationContext> fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="76e73-174">Typically when using `async` and `await`, asynchronous code resumes on either on a <xref:System.Threading.Tasks.TaskScheduler> or on the current  <xref:System.Threading.SynchronizationContext>.</span></span>

<span data-ttu-id="76e73-175">Wenn E/A-Vorgänge durchgeführt werden, ist es wichtig, genau zu steuern, wo die E/A-Vorgänge durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-175">When doing I/O, it's important to have fine-grained control over where the I/O is performed.</span></span> <span data-ttu-id="76e73-176">Diese Steuerung ermöglicht die effektive Nutzung von CPU-Caches.</span><span class="sxs-lookup"><span data-stu-id="76e73-176">This control allows taking advantage of CPU caches effectively.</span></span> <span data-ttu-id="76e73-177">Effiziente Zwischenspeicherung ist für Hochleistungs-Apps wie Webserver von entscheidender Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="76e73-177">Efficient caching is critical for high-performance apps like web servers.</span></span> <span data-ttu-id="76e73-178"><xref:System.IO.Pipelines.PipeScheduler> bietet die Kontrolle darüber, wo asynchrone Rückrufe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-178"><xref:System.IO.Pipelines.PipeScheduler> provides control over where asynchronous callbacks run.</span></span> <span data-ttu-id="76e73-179">Standardmäßig:</span><span class="sxs-lookup"><span data-stu-id="76e73-179">By default:</span></span>

* <span data-ttu-id="76e73-180">Der aktuelle <xref:System.Threading.SynchronizationContext> wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="76e73-180">The current <xref:System.Threading.SynchronizationContext> is used.</span></span>
* <span data-ttu-id="76e73-181">Wenn kein `SynchronizationContext` vorhanden ist, wird der Threadpool verwendet, um Rückrufe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="76e73-181">If there's no `SynchronizationContext`, it uses the thread pool to run callbacks.</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Program.cs?name=snippet)]

<span data-ttu-id="76e73-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) ist die <xref:System.IO.Pipelines.PipeScheduler>-Implementierung, die Rückrufe des Threadpools der Warteschlange hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="76e73-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) is the <xref:System.IO.Pipelines.PipeScheduler> implementation that queues callbacks to the thread pool.</span></span> <span data-ttu-id="76e73-183">`PipeScheduler.ThreadPool` ist die Standardeinstellung und in der Regel die beste Wahl.</span><span class="sxs-lookup"><span data-stu-id="76e73-183">`PipeScheduler.ThreadPool` is the default and generally the best choice.</span></span> <span data-ttu-id="76e73-184">[Pipescheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) kann unbeabsichtigte Folgen verursachen, z.B. Deadlocks.</span><span class="sxs-lookup"><span data-stu-id="76e73-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) can cause unintended consequences such as deadlocks.</span></span>

### <a name="pipe-reset"></a><span data-ttu-id="76e73-185">Pipezurücksetzung</span><span class="sxs-lookup"><span data-stu-id="76e73-185">Pipe reset</span></span>

<span data-ttu-id="76e73-186">Es ist häufig effizient, das `Pipe`-Objekt wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="76e73-186">It's frequently efficient to reuse the `Pipe` object.</span></span> <span data-ttu-id="76e73-187">Zum Zurücksetzen der Pipe rufen Sie <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> auf, wenn `PipeReader` sowie `PipeWriter` abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="76e73-187">To reset the pipe, call <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> when both the `PipeReader` and `PipeWriter` are complete.</span></span>

## <a name="pipereader"></a><span data-ttu-id="76e73-188">PipeReader</span><span class="sxs-lookup"><span data-stu-id="76e73-188">PipeReader</span></span>

<span data-ttu-id="76e73-189"><xref:System.IO.Pipelines.PipeReader> verwaltet den Arbeitsspeicher im Auftrag des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="76e73-189"><xref:System.IO.Pipelines.PipeReader> manages memory on the caller's behalf.</span></span> <span data-ttu-id="76e73-190">Rufen Sie **immer** <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> auf, nachdem <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType> aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="76e73-190">**Always** call <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> after calling <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="76e73-191">Dadurch kann `PipeReader` erkennen, wenn der Aufrufer Vorgänge im Arbeitsspeicher abgeschlossen hat, damit sie nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="76e73-191">This lets the `PipeReader` know when the caller is done with the memory so that it can be tracked.</span></span> <span data-ttu-id="76e73-192">Das von `PipeReader.ReadAsync` zurückgegebene `ReadOnlySequence<byte>`-Element ist nur bis zum Aufruf von `PipeReader.AdvanceTo` gültig.</span><span class="sxs-lookup"><span data-stu-id="76e73-192">The `ReadOnlySequence<byte>` returned from `PipeReader.ReadAsync` is only valid until the call the `PipeReader.AdvanceTo`.</span></span> <span data-ttu-id="76e73-193">Es ist unzulässig, `ReadOnlySequence<byte>` nach dem Aufruf von `PipeReader.AdvanceTo` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="76e73-193">It's illegal to use `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo`.</span></span>

<span data-ttu-id="76e73-194">`PipeReader.AdvanceTo` nimmt zwei <xref:System.SequencePosition>-Argumente an.</span><span class="sxs-lookup"><span data-stu-id="76e73-194">`PipeReader.AdvanceTo` takes two <xref:System.SequencePosition> arguments:</span></span>

* <span data-ttu-id="76e73-195">Das erste Argument bestimmt, wie viel Arbeitsspeicher verbraucht wurde.</span><span class="sxs-lookup"><span data-stu-id="76e73-195">The first argument determines how much memory was consumed.</span></span>
* <span data-ttu-id="76e73-196">Das zweite Argument bestimmt, in welchem Umfang der Puffer untersucht wurde.</span><span class="sxs-lookup"><span data-stu-id="76e73-196">The second argument determines how much of the buffer was observed.</span></span>

<span data-ttu-id="76e73-197">Das Markieren von Daten als verarbeitet bedeutet, dass die Pipe den Arbeitsspeicher an den zugrunde liegenden Pufferpool zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="76e73-197">Marking data as consumed means that the pipe can return the memory to the underlying buffer pool.</span></span> <span data-ttu-id="76e73-198">Durch das Markieren von Daten als untersucht wird gesteuert, welche Aktion der nächste Aufruf von `PipeReader.ReadAsync` ausführt.</span><span class="sxs-lookup"><span data-stu-id="76e73-198">Marking data as observed controls what the next call to `PipeReader.ReadAsync` does.</span></span> <span data-ttu-id="76e73-199">Wenn alle Daten als untersucht markiert sind, bedeutet dies, dass der nächste Aufruf von `PipeReader.ReadAsync` erst dann eine Rückgabe liefert, wenn weitere Daten in die Pipe geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-199">Marking everything as observed means that the next call to `PipeReader.ReadAsync` won't return until there's more data written to the pipe.</span></span> <span data-ttu-id="76e73-200">Jeder andere Wert führt dazu, dass der nächste Aufruf von `PipeReader.ReadAsync` sofort die untersuchten *und* die nicht untersuchten Daten zurückgibt. Es handelt sich jedoch um bereits verarbeitete Daten.</span><span class="sxs-lookup"><span data-stu-id="76e73-200">Any other value will make the next call to `PipeReader.ReadAsync` return immediately with the observed *and* unobserved data, but data that has already been consumed.</span></span>

### <a name="read-streaming-data-scenarios"></a><span data-ttu-id="76e73-201">Szenarien für das Lesen von Streamingdaten</span><span class="sxs-lookup"><span data-stu-id="76e73-201">Read streaming data scenarios</span></span>

<span data-ttu-id="76e73-202">Beim Versuch, Streamingdaten zu lesen, gibt es einige typische Muster:</span><span class="sxs-lookup"><span data-stu-id="76e73-202">There are a couple of typical patterns that emerge when trying to read streaming data:</span></span>

* <span data-ttu-id="76e73-203">Analysieren einer einzelnen Nachricht in einem angegebenen Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="76e73-203">Given a stream of data, parse a single message.</span></span>
* <span data-ttu-id="76e73-204">Analysieren aller Nachrichten in einem angegebenen Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="76e73-204">Given a stream of data, parse all available messages.</span></span>

<span data-ttu-id="76e73-205">In den folgenden Beispielen wird die `TryParseMessage`-Methode zum Analysieren von Nachrichten aus `ReadOnlySequence<byte>` verwendet.</span><span class="sxs-lookup"><span data-stu-id="76e73-205">The following examples use the `TryParseMessage` method for parsing messages from a `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="76e73-206">`TryParseMessage` analysiert eine einzelne Nachricht und aktualisiert den Eingabepuffer, um die analysierte Nachricht aus dem Puffer zu kürzen.</span><span class="sxs-lookup"><span data-stu-id="76e73-206">`TryParseMessage` parses a single message and update the input buffer to trim the parsed message from the buffer.</span></span> <span data-ttu-id="76e73-207">`TryParseMessage` ist nicht Bestandteil von .NET, sondern eine vom Benutzer erstellte Methode, die in den folgenden Abschnitten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-207">`TryParseMessage` is not part of .NET, it's a user written method used in the following sections.</span></span>

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a><span data-ttu-id="76e73-208">Lesen einer einzelnen Nachricht</span><span class="sxs-lookup"><span data-stu-id="76e73-208">Read a single message</span></span>

<span data-ttu-id="76e73-209">Der folgende Code liest eine einzelne Nachricht aus `PipeReader` und gibt sie an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="76e73-209">The following code reads a single message from a `PipeReader` and returns it to the caller.</span></span>

[!code-csharp[ReadSingleMsg](~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs?name=snippet)]

<span data-ttu-id="76e73-210">Der vorangehende Code:</span><span class="sxs-lookup"><span data-stu-id="76e73-210">The preceding code:</span></span>

* <span data-ttu-id="76e73-211">Analysiert eine einzelne Nachricht.</span><span class="sxs-lookup"><span data-stu-id="76e73-211">Parses a single message.</span></span>
* <span data-ttu-id="76e73-212">Aktualisiert die verarbeitete `SequencePosition` und die untersuchte `SequencePosition`, um auf den Anfang des gekürzten Eingabepuffers zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="76e73-212">Updates the consumed `SequencePosition` and examined `SequencePosition` to point to the start of the trimmed input buffer.</span></span>

<span data-ttu-id="76e73-213">Die beiden `SequencePosition`-Argumente werden aktualisiert, weil `TryParseMessage` die analysierte Nachricht aus dem Eingabepuffer entfernt.</span><span class="sxs-lookup"><span data-stu-id="76e73-213">The two `SequencePosition` arguments are updated because `TryParseMessage` removes the parsed message from the input buffer.</span></span> <span data-ttu-id="76e73-214">Wenn eine einzelne Nachricht aus dem Puffer analysiert wird, sollte die untersuchte Position im Allgemeinen eine der folgenden Positionen sein:</span><span class="sxs-lookup"><span data-stu-id="76e73-214">Generally, when parsing a single message from the buffer, the examined position should be one of the following:</span></span>

* <span data-ttu-id="76e73-215">Das Ende der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="76e73-215">The end of the message.</span></span>
* <span data-ttu-id="76e73-216">Das Ende des empfangenen Puffers, wenn keine Nachricht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="76e73-216">The end of the received buffer if no message was found.</span></span>

<span data-ttu-id="76e73-217">Das Szenario mit einer einzelnen Nachricht weist das größte Fehlerpotenzial auf.</span><span class="sxs-lookup"><span data-stu-id="76e73-217">The single message case has the most potential for errors.</span></span> <span data-ttu-id="76e73-218">Wenn Sie die falschen Werte an *examined* (untersucht) übergeben, kann dies zu einer Ausnahme des Typs „Nicht genügend Arbeitsspeicher“ oder einer Endlosschleife führen.</span><span class="sxs-lookup"><span data-stu-id="76e73-218">Passing the wrong values to *examined* can result in an out of memory exception or an infinite loop.</span></span> <span data-ttu-id="76e73-219">Weitere Informationen finden Sie im Abschnitt [Allgemeine PipeReader-Probleme](#gotchas) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="76e73-219">For more information, see the [PipeReader common problems](#gotchas) section in this article.</span></span>

### <a name="reading-multiple-messages"></a><span data-ttu-id="76e73-220">Lesen mehrerer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="76e73-220">Reading multiple messages</span></span>

<span data-ttu-id="76e73-221">Der folgende Code liest alle Nachrichten aus einem `PipeReader` und ruft für jede Nachricht `ProcessMessageAsync` auf.</span><span class="sxs-lookup"><span data-stu-id="76e73-221">The following code reads all messages from a `PipeReader` and calls `ProcessMessageAsync` on each.</span></span>

[!code-csharp[MyConnection1](~/samples/snippets/csharp/pipelines/MyConnection1.cs?name=snippet)]

### <a name="cancellation"></a><span data-ttu-id="76e73-222">Abbruch</span><span class="sxs-lookup"><span data-stu-id="76e73-222">Cancellation</span></span>

<span data-ttu-id="76e73-223">`PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="76e73-223">`PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="76e73-224">Unterstützt das Übergeben eines <xref:System.Threading.CancellationToken>-Elements.</span><span class="sxs-lookup"><span data-stu-id="76e73-224">Supports passing a <xref:System.Threading.CancellationToken>.</span></span>
* <span data-ttu-id="76e73-225">Löst eine <xref:System.OperationCanceledException> aus, wenn `CancellationToken` abgebrochen wird, während ein Lesevorgang aussteht.</span><span class="sxs-lookup"><span data-stu-id="76e73-225">Throws an <xref:System.OperationCanceledException> if the `CancellationToken` is canceled while there's a read pending.</span></span>
* <span data-ttu-id="76e73-226">Unterstützt die Möglichkeit, den aktuellen Lesevorgang über <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType> abzubrechen, wodurch das Auslösen einer Ausnahme vermieden wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-226">Supports a way to cancel the current read operation via <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, which avoids raising an exception.</span></span> <span data-ttu-id="76e73-227">Das Aufrufen von `PipeReader.CancelPendingRead` bewirkt, dass der aktuelle oder nächste Aufruf von `PipeReader.ReadAsync` ein <xref:System.IO.Pipelines.ReadResult> zurückgibt, wobei `IsCanceled` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="76e73-227">Calling `PipeReader.CancelPendingRead` causes the current or next call to `PipeReader.ReadAsync` to return a <xref:System.IO.Pipelines.ReadResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="76e73-228">Dies kann nützlich sein, um die vorhandene Leseschleife auf nicht destruktive Weise und ohne Auslösen einer Ausnahme anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="76e73-228">This can be useful for halting the existing read loop in a non-destructive and non-exceptional way.</span></span>

[!code-csharp[MyConnection](~/samples/snippets/csharp/pipelines/MyConnection.cs?name=snippet)]

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a><span data-ttu-id="76e73-229">Allgemeine PipeReader-Probleme</span><span class="sxs-lookup"><span data-stu-id="76e73-229">PipeReader common problems</span></span>

* <span data-ttu-id="76e73-230">Wenn die falschen Werte an `consumed` oder `examined` übergeben werden, können bereits gelesene Daten erneut gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-230">Passing the wrong values to `consumed` or `examined` may result in reading already read data.</span></span>
* <span data-ttu-id="76e73-231">Wenn Sie `buffer.End` als untersucht übergeben, kann dies zu folgenden Ergebnissen führen:</span><span class="sxs-lookup"><span data-stu-id="76e73-231">Passing `buffer.End` as examined may result in:</span></span>

  * <span data-ttu-id="76e73-232">Angehaltene Daten.</span><span class="sxs-lookup"><span data-stu-id="76e73-232">Stalled data</span></span>
  * <span data-ttu-id="76e73-233">Möglicherweise wird eine Ausnahme aufgrund von nicht genügend Arbeitsspeicher (Out of Memory, OOM) ausgelöst, wenn keine Daten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-233">Possibly an eventual Out of Memory (OOM) exception if data isn't consumed.</span></span> <span data-ttu-id="76e73-234">Beispielsweise `PipeReader.AdvanceTo(position, buffer.End)`, wenn jeweils eine einzelne Nachricht aus dem Puffer verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-234">For example, `PipeReader.AdvanceTo(position, buffer.End)` when processing a single message at a time from the buffer.</span></span>

* <span data-ttu-id="76e73-235">Wenn die falschen Werte an `consumed` oder `examined` übergeben werden, kann dies zu einer Endlosschleife führen.</span><span class="sxs-lookup"><span data-stu-id="76e73-235">Passing the wrong values to `consumed` or `examined` may result in an infinite loop.</span></span> <span data-ttu-id="76e73-236">`PipeReader.AdvanceTo(buffer.Start)`, wenn sich `buffer.Start` nicht geändert hat, bewirkt beispielsweise, dass der nächste Aufruf von `PipeReader.ReadAsync` sofort vor dem Eintreffen neuer Daten zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-236">For example, `PipeReader.AdvanceTo(buffer.Start)` if `buffer.Start` hasn't changed will cause the next call to `PipeReader.ReadAsync` to return immediately before new data arrives.</span></span>
* <span data-ttu-id="76e73-237">Wenn die falschen Werte an `consumed` oder `examined` übergeben werden, kann dies zu einer Endlospufferung führen (möglicherweise OOM).</span><span class="sxs-lookup"><span data-stu-id="76e73-237">Passing the wrong values to `consumed` or `examined` may result in infinite buffering (eventual OOM).</span></span>
* <span data-ttu-id="76e73-238">Wenn Sie `ReadOnlySequence<byte>` nach dem Aufruf von `PipeReader.AdvanceTo` verwenden, kann dies zu einer Beschädigung des Arbeitsspeichers führen (Verwendung nach dem Freigeben).</span><span class="sxs-lookup"><span data-stu-id="76e73-238">Using the `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo` may result in memory corruption (use after free).</span></span>
* <span data-ttu-id="76e73-239">Wenn `PipeReader.Complete/CompleteAsync` nicht aufgerufen wird, kann dies zu einem Arbeitsspeicherverlust führen.</span><span class="sxs-lookup"><span data-stu-id="76e73-239">Failing to call `PipeReader.Complete/CompleteAsync` may result in a memory leak.</span></span>
* <span data-ttu-id="76e73-240">Das Überprüfen von <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> und das Beenden der Leselogik vor dem Verarbeiten der Pufferergebnisse führt zu Datenverlusten.</span><span class="sxs-lookup"><span data-stu-id="76e73-240">Checking <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> and exiting the reading logic before processing the buffer results in data loss.</span></span> <span data-ttu-id="76e73-241">Die Beendigungsbedingung der Schleife sollte auf `ReadResult.Buffer.IsEmpty` und `ReadResult.IsCompleted` basieren.</span><span class="sxs-lookup"><span data-stu-id="76e73-241">The loop exit condition should be based on `ReadResult.Buffer.IsEmpty` and `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="76e73-242">Wenn dieser Vorgang nicht ordnungsgemäß erfolgt, kann dies zu einer Endlosschleife führen.</span><span class="sxs-lookup"><span data-stu-id="76e73-242">Doing this incorrectly could result in an infinite loop.</span></span>

#### <a name="problematic-code"></a><span data-ttu-id="76e73-243">Problematischer Code</span><span class="sxs-lookup"><span data-stu-id="76e73-243">Problematic code</span></span>

<span data-ttu-id="76e73-244">❌ **Datenverlust**</span><span class="sxs-lookup"><span data-stu-id="76e73-244">❌ **Data loss**</span></span>

<span data-ttu-id="76e73-245">`ReadResult` kann das finale Datensegment zurückgeben, wenn `IsCompleted` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="76e73-245">The `ReadResult` can return the final segment of data when `IsCompleted` is set to `true`.</span></span> <span data-ttu-id="76e73-246">Das Nichtlesen dieser Daten vor dem Beenden der Leseschleife führt zu Datenverlusten.</span><span class="sxs-lookup"><span data-stu-id="76e73-246">Not reading that data before exiting the read loop will result in data loss.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#1](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="76e73-247">❌ **Endlosschleife**</span><span class="sxs-lookup"><span data-stu-id="76e73-247">❌ **Infinite loop**</span></span>

<span data-ttu-id="76e73-248">Die folgende Logik kann zu einer Endlosschleife führen, wenn `Result.IsCompleted` `true` ist, im Puffer aber niemals eine vollständige Nachricht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="76e73-248">The following logic may result in an infinite loop if the `Result.IsCompleted` is `true` but there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#2](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet2)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="76e73-249">Im Folgenden finden Sie einen weiteren Codeausschnitt mit dem gleichen Problem.</span><span class="sxs-lookup"><span data-stu-id="76e73-249">Here's another piece of code with the same problem.</span></span> <span data-ttu-id="76e73-250">Der Code überprüft, ob ein nicht leerer Puffer vorhanden ist, bevor `ReadResult.IsCompleted` überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-250">It's checking for a non-empty buffer before checking `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="76e73-251">Da dies in einer `else if`-Anweisung stattfindet, ist das Ergebnis eine Endlosschleife, wenn im Puffer niemals eine vollständige Nachricht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="76e73-251">Because it's in an `else if`, it will loop forever if there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#3](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet3)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="76e73-252">❌ **App reagiert unerwarteterweise nicht mehr**</span><span class="sxs-lookup"><span data-stu-id="76e73-252">❌ **Unexpected Hang**</span></span>

<span data-ttu-id="76e73-253">Der Aufruf von `PipeReader.AdvanceTo` mit `buffer.End` an der `examined`-Position ohne Bedingungen kann beim Analysieren einer einzelnen Nachricht dazu führen, dass die App nicht mehr reagiert.</span><span class="sxs-lookup"><span data-stu-id="76e73-253">Unconditionally calling `PipeReader.AdvanceTo` with `buffer.End` in the `examined` position may result in hangs when parsing a single message.</span></span> <span data-ttu-id="76e73-254">Der nächste Aufruf von `PipeReader.AdvanceTo` liefert erst eine Rückgabe, wenn:</span><span class="sxs-lookup"><span data-stu-id="76e73-254">The next call to `PipeReader.AdvanceTo` won't return until:</span></span>

* <span data-ttu-id="76e73-255">Weitere Daten in die Pipe geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-255">There's more data written to the pipe.</span></span>
* <span data-ttu-id="76e73-256">Und die neuen Daten zuvor nicht untersucht wurden.</span><span class="sxs-lookup"><span data-stu-id="76e73-256">And the new data wasn't previously examined.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#4](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet4)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="76e73-257">❌ **Nicht genügend Arbeitsspeicher (Out of Memory, OOM)**</span><span class="sxs-lookup"><span data-stu-id="76e73-257">❌ **Out of Memory (OOM)**</span></span>

<span data-ttu-id="76e73-258">Mit den folgenden Bedingungen behält der folgende Code die Pufferung bei, bis eine <xref:System.OutOfMemoryException> auftritt:</span><span class="sxs-lookup"><span data-stu-id="76e73-258">With the following conditions, the following code keeps buffering until an <xref:System.OutOfMemoryException> occurs:</span></span>

* <span data-ttu-id="76e73-259">Es gibt keine maximale Nachrichtengröße.</span><span class="sxs-lookup"><span data-stu-id="76e73-259">There's no maximum message size.</span></span>
* <span data-ttu-id="76e73-260">Die von `PipeReader` zurückgegebenen Daten bilden keine vollständige Nachricht.</span><span class="sxs-lookup"><span data-stu-id="76e73-260">The data returned from the `PipeReader` doesn't make a complete message.</span></span> <span data-ttu-id="76e73-261">Beispielsweise ergibt sich keine vollständige Nachricht, weil die andere Seite eine große Nachricht schreibt (z.B. eine Nachricht mit 4 GB).</span><span class="sxs-lookup"><span data-stu-id="76e73-261">For example, it doesn't make a complete message because the other side is writing a large message (For example, a 4-GB message).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#5](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet5)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="76e73-262">❌ **Speicherbeschädigung**</span><span class="sxs-lookup"><span data-stu-id="76e73-262">❌ **Memory Corruption**</span></span>

<span data-ttu-id="76e73-263">Beim Schreiben von Hilfsprogrammen, die den Puffer lesen, sollte jede zurückgegebene Nutzlast kopiert werden, bevor `Advance` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="76e73-263">When writing helpers that read the buffer, any returned payload should be copied before calling `Advance`.</span></span> <span data-ttu-id="76e73-264">Im folgenden Beispiel wird der Arbeitsspeicher zurückgegeben, der von `Pipe` verworfen wurde. Er kann für den nächsten Vorgang (Lese-/Schreibzugriff) wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-264">The following example will return memory that the `Pipe` has discarded and may reuse it for the next operation (read/write).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#Message](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippetMessage)]

[!code-csharp[DoNotUse#6](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet6)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a><span data-ttu-id="76e73-265">PipeWriter</span><span class="sxs-lookup"><span data-stu-id="76e73-265">PipeWriter</span></span>

<span data-ttu-id="76e73-266"><xref:System.IO.Pipelines.PipeWriter> verwaltet Puffer zum Schreiben im Auftrag des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="76e73-266">The <xref:System.IO.Pipelines.PipeWriter> manages buffers for writing on the caller's behalf.</span></span> <span data-ttu-id="76e73-267">`PipeWriter` implementiert [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span><span class="sxs-lookup"><span data-stu-id="76e73-267">`PipeWriter` implements [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span></span> <span data-ttu-id="76e73-268">`IBufferWriter<byte>` ermöglicht es, Zugriff auf Puffer zu erhalten, um Schreibvorgänge ohne zusätzliche Pufferkopien auszuführen.</span><span class="sxs-lookup"><span data-stu-id="76e73-268">`IBufferWriter<byte>` makes it possible to get access to buffers to perform writes without additional buffer copies.</span></span>

[!code-csharp[MyPipeWriter](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet)]

<span data-ttu-id="76e73-269">Der vorherige Code:</span><span class="sxs-lookup"><span data-stu-id="76e73-269">The previous code:</span></span>

* <span data-ttu-id="76e73-270">Fordert einen Puffer mit mindestens 5 Bytes von `PipeWriter` unter Verwendung von <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> an.</span><span class="sxs-lookup"><span data-stu-id="76e73-270">Requests a buffer of at least 5 bytes from the `PipeWriter` using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span></span>
* <span data-ttu-id="76e73-271">Schreibt Bytes für die ASCII-Zeichenfolge `"Hello"` in das zurückgegebene `Memory<byte>`-Element.</span><span class="sxs-lookup"><span data-stu-id="76e73-271">Writes bytes for the ASCII string `"Hello"` to the returned `Memory<byte>`.</span></span>
* <span data-ttu-id="76e73-272">Ruft <xref:System.IO.Pipelines.PipeWriter.Advance%2A> auf, um anzugeben, wie viele Bytes in den Puffer geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="76e73-272">Calls <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to indicate how many bytes were written to the buffer.</span></span>
* <span data-ttu-id="76e73-273">Leert das `PipeWriter`-Element, das die Bytes an das zugrunde liegende Gerät sendet.</span><span class="sxs-lookup"><span data-stu-id="76e73-273">Flushes the `PipeWriter`, which sends the bytes to the underlying device.</span></span>

<span data-ttu-id="76e73-274">Die vorherige Methode zum Schreiben verwendet die Puffer, die von `PipeWriter` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-274">The previous method of writing uses the buffers provided by the `PipeWriter`.</span></span> <span data-ttu-id="76e73-275">Alternativ geht <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType> folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="76e73-275">Alternatively, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="76e73-276">Kopiert den vorhandenen Puffer in `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="76e73-276">Copies the existing buffer to the `PipeWriter`.</span></span>
* <span data-ttu-id="76e73-277">Ruft `GetSpan`, `Advance` nach Bedarf auf und ruft dann <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="76e73-277">Calls `GetSpan`, `Advance` as appropriate and calls <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span></span>

[!code-csharp[MyPipeWriter#2](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet2)]

### <a name="cancellation"></a><span data-ttu-id="76e73-278">Abbruch</span><span class="sxs-lookup"><span data-stu-id="76e73-278">Cancellation</span></span>

<span data-ttu-id="76e73-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> unterstützt das Übergeben eines <xref:System.Threading.CancellationToken>-Elements.</span><span class="sxs-lookup"><span data-stu-id="76e73-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supports passing a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="76e73-280">Das Übergeben eines `CancellationToken` führt zu einer `OperationCanceledException`, wenn das Token abgebrochen wird, während ein Leerungsvorgang aussteht.</span><span class="sxs-lookup"><span data-stu-id="76e73-280">Passing a `CancellationToken` results in an `OperationCanceledException` if the token is canceled while there's a flush pending.</span></span> <span data-ttu-id="76e73-281">`PipeWriter.FlushAsync` unterstützt die Möglichkeit, den aktuellen Leerungsvorgang über <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> abzubrechen, ohne eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="76e73-281">`PipeWriter.FlushAsync` supports a way to cancel the current flush operation via <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> without raising an exception.</span></span> <span data-ttu-id="76e73-282">Der Aufruf von `PipeWriter.CancelPendingFlush` bewirkt, dass der aktuelle oder nächste Aufruf von `PipeWriter.FlushAsync` oder `PipeWriter.WriteAsync` ein <xref:System.IO.Pipelines.FlushResult> zurückgibt, wobei `IsCanceled` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="76e73-282">Calling `PipeWriter.CancelPendingFlush` causes the current or next call to `PipeWriter.FlushAsync` or `PipeWriter.WriteAsync` to return a <xref:System.IO.Pipelines.FlushResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="76e73-283">Dies kann nützlich sein, um die sich ergebende Leerung auf nicht destruktive Weise und ohne Auslösen einer Ausnahme anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="76e73-283">This can be useful for halting the yielding flush in a non-destructive and non-exceptional way.</span></span>

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a><span data-ttu-id="76e73-284">Allgemeine PipeWriter-Probleme</span><span class="sxs-lookup"><span data-stu-id="76e73-284">PipeWriter common problems</span></span>

* <span data-ttu-id="76e73-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> und <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> geben einen Puffer mit mindestens der angeforderten Menge an Arbeitsspeicher zurück.</span><span class="sxs-lookup"><span data-stu-id="76e73-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> and <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="76e73-286">Gehen Sie **nicht** von genauen Puffergrößen aus.</span><span class="sxs-lookup"><span data-stu-id="76e73-286">**Don't** assume exact buffer sizes.</span></span>
* <span data-ttu-id="76e73-287">Es gibt keine Garantie, dass aufeinanderfolgende Aufrufe denselben Puffer oder dieselbe Puffergröße zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="76e73-287">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
* <span data-ttu-id="76e73-288">Nach dem Aufrufen von <xref:System.IO.Pipelines.PipeWriter.Advance%2A> muss ein neuer Puffer angefordert werden, um das Schreiben weiterer Daten fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="76e73-288">A new buffer must be requested after calling <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to continue writing more data.</span></span> <span data-ttu-id="76e73-289">In den zuvor abgerufenen Puffer kann nicht geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-289">The previously acquired buffer can't be written to.</span></span>
* <span data-ttu-id="76e73-290">Das Aufrufen von `GetMemory` oder `GetSpan` ist während eines unvollständiger Aufrufs von `FlushAsync` nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="76e73-290">Calling `GetMemory` or `GetSpan` while there's an incomplete call to `FlushAsync` isn't safe.</span></span>
* <span data-ttu-id="76e73-291">Wenn Sie `Complete` oder `CompleteAsync` aufrufen, während nicht geleerte Daten vorhanden sind, kann dies zu einer Speicherbeschädigung führen.</span><span class="sxs-lookup"><span data-stu-id="76e73-291">Calling `Complete` or `CompleteAsync` while there's unflushed data can result in memory corruption.</span></span>

## <a name="iduplexpipe"></a><span data-ttu-id="76e73-292">IDuplexPipe</span><span class="sxs-lookup"><span data-stu-id="76e73-292">IDuplexPipe</span></span>

<span data-ttu-id="76e73-293"><xref:System.IO.Pipelines.IDuplexPipe> ist ein Vertrag für Typen, die sowohl Lese- als auch Schreibvorgänge unterstützen.</span><span class="sxs-lookup"><span data-stu-id="76e73-293">The <xref:System.IO.Pipelines.IDuplexPipe> is a contract for types that support both reading and writing.</span></span> <span data-ttu-id="76e73-294">Eine Netzwerkverbindung würde z.B. durch eine `IDuplexPipe` dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-294">For example, a network connection would be represented by an `IDuplexPipe`.</span></span>

 <span data-ttu-id="76e73-295">Im Gegensatz zum `Pipe`-Element, das einen `PipeReader` und einen `PipeWriter` enthält, stellt `IDuplexPipe` nur eine Seite einer vollständigen Duplexverbindung dar.</span><span class="sxs-lookup"><span data-stu-id="76e73-295">Unlike `Pipe` which contains a `PipeReader` and a `PipeWriter`, `IDuplexPipe` represents a single side of a full duplex connection.</span></span> <span data-ttu-id="76e73-296">Dies bedeutet, dass die in `PipeWriter` geschriebenen Informationen von `PipeReader` gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="76e73-296">That means what is written to the `PipeWriter` will not be read from the `PipeReader`.</span></span>

## <a name="streams"></a><span data-ttu-id="76e73-297">Streams</span><span class="sxs-lookup"><span data-stu-id="76e73-297">Streams</span></span>

<span data-ttu-id="76e73-298">Beim Lesen oder Schreiben von Streamdaten lesen Sie Daten in der Regel mithilfe eines Deserialisierers und schreiben Daten mit einem Serialisierer.</span><span class="sxs-lookup"><span data-stu-id="76e73-298">When reading or writing stream data, you typically read data using a de-serializer and write data using a serializer.</span></span> <span data-ttu-id="76e73-299">Die meisten dieser APIs zum Lesen und Schreiben eines Datenstrom verfügen über einen `Stream`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="76e73-299">Most of these read and write stream APIs have a `Stream` parameter.</span></span> <span data-ttu-id="76e73-300">Um die Integration in diese vorhandenen APIs zu vereinfachen, stellen `PipeReader` und `PipeWriter` ein <xref:System.IO.Pipelines.PipeReader.AsStream%2A>-Element zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="76e73-300">To make it easier to integrate with these existing APIs, `PipeReader` and `PipeWriter` expose an <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.</span></span>  <span data-ttu-id="76e73-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> gibt eine `Stream`-Implementierung um `PipeReader` oder `PipeWriter` zurück.</span><span class="sxs-lookup"><span data-stu-id="76e73-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> returns a `Stream` implementation around the `PipeReader` or `PipeWriter`.</span></span>
