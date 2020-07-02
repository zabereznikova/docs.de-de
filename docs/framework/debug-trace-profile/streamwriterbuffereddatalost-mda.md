---
title: streamWriterBufferedDataLost-MDA
description: Überprüfen Sie den streamschreibbuffereddatalost Managed Debug Assistant (MDA), der aktiviert werden kann, wenn ein StreamWriter nicht die letzten 1 – 4 KB an Daten in eine Datei schreibt.
ms.date: 03/30/2017
helpviewer_keywords:
- StreamWriter class, data buffering problems
- managed debugging assistants (MDAs), StreamWriter data buffering
- buffers, StreamWriter problems
- MDAs (managed debugging assistants), StreamWriter data buffering
- StreamWriter buffered data lost
- data buffering problems
- streamWriterBufferedDataLost MDA
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
ms.openlocfilehash: 0c10ea6bb9dc0aaafa2ac1798696579af7592895
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803481"
---
# <a name="streamwriterbuffereddatalost-mda"></a><span data-ttu-id="de1ee-103">streamWriterBufferedDataLost-MDA</span><span class="sxs-lookup"><span data-stu-id="de1ee-103">streamWriterBufferedDataLost MDA</span></span>
<span data-ttu-id="de1ee-104">Der `streamWriterBufferedDataLost`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine <xref:System.IO.StreamWriter> geschrieben wird, aber die <xref:System.IO.StreamWriter.Flush%2A>- oder <xref:System.IO.StreamWriter.Close%2A>-Methode wird anschließend nicht aufgerufen, bevor die Instanz der <xref:System.IO.StreamWriter> zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="de1ee-104">The `streamWriterBufferedDataLost` managed debugging assistant (MDA) is activated when a <xref:System.IO.StreamWriter> is written to, but the <xref:System.IO.StreamWriter.Flush%2A> or <xref:System.IO.StreamWriter.Close%2A> method is not subsequently called before the instance of the <xref:System.IO.StreamWriter> is destroyed.</span></span> <span data-ttu-id="de1ee-105">Wenn dieser MDA aktiviert ist, überprüft die Common Language Runtime, ob gepufferte Daten immer noch in <xref:System.IO.StreamWriter> vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="de1ee-105">When this MDA is enabled, the runtime determines whether any buffered data still exists within the <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="de1ee-106">Wenn die gepufferten Daten vorhanden sind, wird der MDA aktiviert.</span><span class="sxs-lookup"><span data-stu-id="de1ee-106">If buffered data does exist, the MDA is activated.</span></span> <span data-ttu-id="de1ee-107">Ein Aufruf der <xref:System.GC.Collect%2A>- und <xref:System.GC.WaitForPendingFinalizers%2A>-Methoden kann erzwingen, dass Finalizer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="de1ee-107">Calling the <xref:System.GC.Collect%2A> and <xref:System.GC.WaitForPendingFinalizers%2A> methods can force finalizers to run.</span></span> <span data-ttu-id="de1ee-108">Finalizer werden andernfalls zu scheinbar willkürlichen Zeiten und beim Beenden des Prozesses möglicherweise gar nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="de1ee-108">Finalizers will otherwise run at seemingly arbitrary times, and possibly not at all on process exit.</span></span> <span data-ttu-id="de1ee-109">Wenn Finalizer explizit mit diesem aktiven MDA ausgeführt werden, wird diese Art von Problemen zuverlässiger reproduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="de1ee-109">Explicitly running finalizers with this MDA enabled will help to more reliably reproduce this type of problem.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="de1ee-110">Symptome</span><span class="sxs-lookup"><span data-stu-id="de1ee-110">Symptoms</span></span>  
 <span data-ttu-id="de1ee-111">Ein <xref:System.IO.StreamWriter> schreibt die letzten 1 bis 4 KB Daten nicht in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="de1ee-111">A <xref:System.IO.StreamWriter> does not write the last 1–4 KB of data to a file.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="de1ee-112">Ursache</span><span class="sxs-lookup"><span data-stu-id="de1ee-112">Cause</span></span>  
 <span data-ttu-id="de1ee-113">Die <xref:System.IO.StreamWriter> puffert Daten intern. Dies erfordert, dass die <xref:System.IO.StreamWriter.Close%2A>- oder <xref:System.IO.StreamWriter.Flush%2A>-Methode aufgerufen wird, um die gepufferten Daten in den zugrunde liegenden Datenspeicher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="de1ee-113">The <xref:System.IO.StreamWriter> buffers data internally, which requires that the <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> method be called to write the buffered data to the underlying data store.</span></span> <span data-ttu-id="de1ee-114">Wenn <xref:System.IO.StreamWriter.Close%2A> oder <xref:System.IO.StreamWriter.Flush%2A> nicht richtig aufgerufen werden, können gepufferte Daten in der <xref:System.IO.StreamWriter>-Instanz nicht wie erwartet geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="de1ee-114">If <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> is not appropriately called, data buffered in the <xref:System.IO.StreamWriter> instance might not be written as expected.</span></span>  
  
 <span data-ttu-id="de1ee-115">Das folgende Beispiel zeigt schlecht geschriebenen Code, den dieser MDA abfangen sollte.</span><span class="sxs-lookup"><span data-stu-id="de1ee-115">The following is an example of poorly written code that this MDA should catch.</span></span>  
  
```csharp  
// Poorly written code.  
void Write()
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 <span data-ttu-id="de1ee-116">Der vorangehende Code wird diesen MDA zuverlässiger aktivieren, wenn eine Garbage Collection ausgelöst und dann angehalten wurde, bis die Finalizer beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="de1ee-116">The preceding code will activate this MDA more reliably if a garbage collection is triggered and then suspended until finalizers have finished.</span></span> <span data-ttu-id="de1ee-117">Um diese Art von Problemen aufzufinden, können Sie den folgenden Code am Ende der vorherigen Methode in einem Debugbuild hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="de1ee-117">To track down this type of problem, you can add the following code to the end of the preceding method in a debug build.</span></span> <span data-ttu-id="de1ee-118">Dies hilft dabei, den MDA zuverlässig zu aktivieren, aber natürlich wird die Ursache des Problems somit nicht behoben.</span><span class="sxs-lookup"><span data-stu-id="de1ee-118">This will help to reliably activate the MDA, but of course it does not fix the cause of the problem.</span></span>  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a><span data-ttu-id="de1ee-119">Lösung</span><span class="sxs-lookup"><span data-stu-id="de1ee-119">Resolution</span></span>  
 <span data-ttu-id="de1ee-120">Stellen Sie sicher, dass Sie <xref:System.IO.StreamWriter.Close%2A> oder <xref:System.IO.StreamWriter.Flush%2A> der <xref:System.IO.StreamWriter> oder eines beliebigen Codeblocks abrufen, der eine <xref:System.IO.StreamWriter>-Instanz enthält, bevor Sie eine Anwendung schließen.</span><span class="sxs-lookup"><span data-stu-id="de1ee-120">Make sure you call <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> before closing an application or any code block that has an instance of a <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="de1ee-121">Eine der besten Mechanismen, um dies zu erreichen, ist das Erstellen der Instanz mithilfe des `using`-C#-Blocks (`Using` in Visual Basic), was sicherstellt, dass die <xref:System.IO.StreamWriter.Dispose%2A>-Methode für den Writer aufgerufen wurde, wodurch die Instanz ordnungsgemäß geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="de1ee-121">One of the best mechanisms for achieving this is creating the instance with a C# `using` block (`Using` in Visual Basic), which will ensure the <xref:System.IO.StreamWriter.Dispose%2A> method for the writer is invoked, resulting in the instance being correctly closed.</span></span>  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))
{  
    sw.WriteLine("Data");  
}  
```  
  
 <span data-ttu-id="de1ee-122">Der folgende Code zeigt dieselbe Projektmappe mithilfe von `try/finally` anstelle von `using` an.</span><span class="sxs-lookup"><span data-stu-id="de1ee-122">The following code shows the same solution, using `try/finally` instead of `using`.</span></span>  
  
```csharp
StreamWriter sw;  
try
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 <span data-ttu-id="de1ee-123">Wenn keine dieser Lösungen verwendet werden kann (z.B. wenn sich ein <xref:System.IO.StreamWriter> in einer statischen Variablen befindet und Sie den Code am Ende der Lebenszeit nicht problemlos ausführen können), sollte der Aufruf von <xref:System.IO.StreamWriter.Flush%2A> auf <xref:System.IO.StreamWriter> nach der letzten Verwendung oder die Einstellung der <xref:System.IO.StreamWriter.AutoFlush%2A>-Eigenschaft auf `true` vor der ersten Verwendung dieses Problem vermeiden.</span><span class="sxs-lookup"><span data-stu-id="de1ee-123">If neither of these solutions can be used (for example, if a <xref:System.IO.StreamWriter> is stored in a static variable and you cannot easily run code at the end of its lifetime), then calling <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> after its last use or setting the <xref:System.IO.StreamWriter.AutoFlush%2A> property to `true` before its first use should avoid this problem.</span></span>  
  
```csharp
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="de1ee-124">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="de1ee-124">Effect on the Runtime</span></span>  
 <span data-ttu-id="de1ee-125">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="de1ee-125">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="de1ee-126">Output</span><span class="sxs-lookup"><span data-stu-id="de1ee-126">Output</span></span>  
 <span data-ttu-id="de1ee-127">Eine Meldung, die angibt, dass diese Überschreitung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="de1ee-127">A message indicating that this violation occurred.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="de1ee-128">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="de1ee-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de1ee-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de1ee-129">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="de1ee-130">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="de1ee-130">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
