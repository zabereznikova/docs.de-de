---
title: streamWriterBufferedDataLost-MDA
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
ms.openlocfilehash: 82940b40b302f4a928547f2e6a0c285727e13934
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216102"
---
# <a name="streamwriterbuffereddatalost-mda"></a><span data-ttu-id="a5aae-102">streamWriterBufferedDataLost-MDA</span><span class="sxs-lookup"><span data-stu-id="a5aae-102">streamWriterBufferedDataLost MDA</span></span>
<span data-ttu-id="a5aae-103">Der `streamWriterBufferedDataLost`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine <xref:System.IO.StreamWriter> geschrieben wird, aber die <xref:System.IO.StreamWriter.Flush%2A>- oder <xref:System.IO.StreamWriter.Close%2A>-Methode wird anschließend nicht aufgerufen, bevor die Instanz der <xref:System.IO.StreamWriter> zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="a5aae-103">The `streamWriterBufferedDataLost` managed debugging assistant (MDA) is activated when a <xref:System.IO.StreamWriter> is written to, but the <xref:System.IO.StreamWriter.Flush%2A> or <xref:System.IO.StreamWriter.Close%2A> method is not subsequently called before the instance of the <xref:System.IO.StreamWriter> is destroyed.</span></span> <span data-ttu-id="a5aae-104">Wenn dieser MDA aktiviert ist, überprüft die Common Language Runtime, ob gepufferte Daten immer noch in <xref:System.IO.StreamWriter> vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a5aae-104">When this MDA is enabled, the runtime determines whether any buffered data still exists within the <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="a5aae-105">Wenn die gepufferten Daten vorhanden sind, wird der MDA aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a5aae-105">If buffered data does exist, the MDA is activated.</span></span> <span data-ttu-id="a5aae-106">Ein Aufruf der <xref:System.GC.Collect%2A>- und <xref:System.GC.WaitForPendingFinalizers%2A>-Methoden kann erzwingen, dass Finalizer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a5aae-106">Calling the <xref:System.GC.Collect%2A> and <xref:System.GC.WaitForPendingFinalizers%2A> methods can force finalizers to run.</span></span> <span data-ttu-id="a5aae-107">Finalizer werden andernfalls zu scheinbar willkürlichen Zeiten und beim Beenden des Prozesses möglicherweise gar nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5aae-107">Finalizers will otherwise run at seemingly arbitrary times, and possibly not at all on process exit.</span></span> <span data-ttu-id="a5aae-108">Wenn Finalizer explizit mit diesem aktiven MDA ausgeführt werden, wird diese Art von Problemen zuverlässiger reproduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="a5aae-108">Explicitly running finalizers with this MDA enabled will help to more reliably reproduce this type of problem.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a5aae-109">Symptome</span><span class="sxs-lookup"><span data-stu-id="a5aae-109">Symptoms</span></span>  
 <span data-ttu-id="a5aae-110">Ein <xref:System.IO.StreamWriter> schreibt die letzten 1 bis 4 KB Daten nicht in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="a5aae-110">A <xref:System.IO.StreamWriter> does not write the last 1–4 KB of data to a file.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a5aae-111">Ursache</span><span class="sxs-lookup"><span data-stu-id="a5aae-111">Cause</span></span>  
 <span data-ttu-id="a5aae-112">Die <xref:System.IO.StreamWriter> puffert Daten intern. Dies erfordert, dass die <xref:System.IO.StreamWriter.Close%2A>- oder <xref:System.IO.StreamWriter.Flush%2A>-Methode aufgerufen wird, um die gepufferten Daten in den zugrunde liegenden Datenspeicher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a5aae-112">The <xref:System.IO.StreamWriter> buffers data internally, which requires that the <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> method be called to write the buffered data to the underlying data store.</span></span> <span data-ttu-id="a5aae-113">Wenn <xref:System.IO.StreamWriter.Close%2A> oder <xref:System.IO.StreamWriter.Flush%2A> nicht richtig aufgerufen werden, können gepufferte Daten in der <xref:System.IO.StreamWriter>-Instanz nicht wie erwartet geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a5aae-113">If <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> is not appropriately called, data buffered in the <xref:System.IO.StreamWriter> instance might not be written as expected.</span></span>  
  
 <span data-ttu-id="a5aae-114">Das folgende Beispiel zeigt schlecht geschriebenen Code, den dieser MDA abfangen sollte.</span><span class="sxs-lookup"><span data-stu-id="a5aae-114">The following is an example of poorly written code that this MDA should catch.</span></span>  
  
```csharp  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 <span data-ttu-id="a5aae-115">Der vorangehende Code wird diesen MDA zuverlässiger aktivieren, wenn eine Garbage Collection ausgelöst und dann angehalten wurde, bis die Finalizer beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a5aae-115">The preceding code will activate this MDA more reliably if a garbage collection is triggered and then suspended until finalizers have finished.</span></span> <span data-ttu-id="a5aae-116">Um diese Art von Problemen aufzufinden, können Sie den folgenden Code am Ende der vorherigen Methode in einem Debugbuild hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5aae-116">To track down this type of problem, you can add the following code to the end of the preceding method in a debug build.</span></span> <span data-ttu-id="a5aae-117">Dies hilft dabei, den MDA zuverlässig zu aktivieren, aber natürlich wird die Ursache des Problems somit nicht behoben.</span><span class="sxs-lookup"><span data-stu-id="a5aae-117">This will help to reliably activate the MDA, but of course it does not fix the cause of the problem.</span></span>  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a><span data-ttu-id="a5aae-118">Lösung</span><span class="sxs-lookup"><span data-stu-id="a5aae-118">Resolution</span></span>  
 <span data-ttu-id="a5aae-119">Stellen Sie sicher, dass Sie <xref:System.IO.StreamWriter.Close%2A> oder <xref:System.IO.StreamWriter.Flush%2A> der <xref:System.IO.StreamWriter> oder eines beliebigen Codeblocks abrufen, der eine <xref:System.IO.StreamWriter>-Instanz enthält, bevor Sie eine Anwendung schließen.</span><span class="sxs-lookup"><span data-stu-id="a5aae-119">Make sure you call <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> before closing an application or any code block that has an instance of a <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="a5aae-120">Eine der besten Mechanismen, um dies zu erreichen, ist das Erstellen der Instanz mithilfe des `using`-C#-Blocks (`Using` in Visual Basic), was sicherstellt, dass die <xref:System.IO.StreamWriter.Dispose%2A>-Methode für den Writer aufgerufen wurde, wodurch die Instanz ordnungsgemäß geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="a5aae-120">One of the best mechanisms for achieving this is creating the instance with a C# `using` block (`Using` in Visual Basic), which will ensure the <xref:System.IO.StreamWriter.Dispose%2A> method for the writer is invoked, resulting in the instance being correctly closed.</span></span>  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 <span data-ttu-id="a5aae-121">Der folgende Code zeigt dieselbe Projektmappe mithilfe von `try/finally` anstelle von `using` an.</span><span class="sxs-lookup"><span data-stu-id="a5aae-121">The following code shows the same solution, using `try/finally` instead of `using`.</span></span>  
  
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
  
 <span data-ttu-id="a5aae-122">Wenn keine dieser Lösungen verwendet werden kann (z.B. wenn sich ein <xref:System.IO.StreamWriter> in einer statischen Variablen befindet und Sie den Code am Ende der Lebenszeit nicht problemlos ausführen können), sollte der Aufruf von <xref:System.IO.StreamWriter.Flush%2A> auf <xref:System.IO.StreamWriter> nach der letzten Verwendung oder die Einstellung der <xref:System.IO.StreamWriter.AutoFlush%2A>-Eigenschaft auf `true` vor der ersten Verwendung dieses Problem vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a5aae-122">If neither of these solutions can be used (for example, if a <xref:System.IO.StreamWriter> is stored in a static variable and you cannot easily run code at the end of its lifetime), then calling <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> after its last use or setting the <xref:System.IO.StreamWriter.AutoFlush%2A> property to `true` before its first use should avoid this problem.</span></span>  
  
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
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a5aae-123">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a5aae-123">Effect on the Runtime</span></span>  
 <span data-ttu-id="a5aae-124">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a5aae-124">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a5aae-125">Output</span><span class="sxs-lookup"><span data-stu-id="a5aae-125">Output</span></span>  
 <span data-ttu-id="a5aae-126">Eine Meldung, die angibt, dass diese Überschreitung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a5aae-126">A message indicating that this violation occurred.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a5aae-127">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a5aae-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5aae-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5aae-128">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="a5aae-129">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="a5aae-129">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
