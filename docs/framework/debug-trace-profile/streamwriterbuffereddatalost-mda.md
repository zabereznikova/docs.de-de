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
ms.openlocfilehash: 18b2a5a95756ed125d26b2846c0b1ddc320463ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181744"
---
# <a name="streamwriterbuffereddatalost-mda"></a>streamWriterBufferedDataLost-MDA
Der `streamWriterBufferedDataLost`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine <xref:System.IO.StreamWriter> geschrieben wird, aber die <xref:System.IO.StreamWriter.Flush%2A>- oder <xref:System.IO.StreamWriter.Close%2A>-Methode wird anschließend nicht aufgerufen, bevor die Instanz der <xref:System.IO.StreamWriter> zerstört wird. Wenn dieser MDA aktiviert ist, überprüft die Common Language Runtime, ob gepufferte Daten immer noch in <xref:System.IO.StreamWriter> vorhanden sind. Wenn die gepufferten Daten vorhanden sind, wird der MDA aktiviert. Ein Aufruf der <xref:System.GC.Collect%2A>- und <xref:System.GC.WaitForPendingFinalizers%2A>-Methoden kann erzwingen, dass Finalizer ausgeführt werden. Finalizer werden andernfalls zu scheinbar willkürlichen Zeiten und beim Beenden des Prozesses möglicherweise gar nicht ausgeführt. Wenn Finalizer explizit mit diesem aktiven MDA ausgeführt werden, wird diese Art von Problemen zuverlässiger reproduziert werden können.  
  
## <a name="symptoms"></a>Symptome  
 Ein <xref:System.IO.StreamWriter> schreibt die letzten 1 bis 4 KB Daten nicht in eine Datei.  
  
## <a name="cause"></a>Ursache  
 Die <xref:System.IO.StreamWriter> puffert Daten intern. Dies erfordert, dass die <xref:System.IO.StreamWriter.Close%2A>- oder <xref:System.IO.StreamWriter.Flush%2A>-Methode aufgerufen wird, um die gepufferten Daten in den zugrunde liegenden Datenspeicher zu schreiben. Wenn <xref:System.IO.StreamWriter.Close%2A> oder <xref:System.IO.StreamWriter.Flush%2A> nicht richtig aufgerufen werden, können gepufferte Daten in der <xref:System.IO.StreamWriter>-Instanz nicht wie erwartet geschrieben werden.  
  
 Das folgende Beispiel zeigt schlecht geschriebenen Code, den dieser MDA abfangen sollte.  
  
```csharp  
// Poorly written code.  
void Write()
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 Der vorangehende Code wird diesen MDA zuverlässiger aktivieren, wenn eine Garbage Collection ausgelöst und dann angehalten wurde, bis die Finalizer beendet wurden. Um diese Art von Problemen aufzufinden, können Sie den folgenden Code am Ende der vorherigen Methode in einem Debugbuild hinzufügen. Dies hilft dabei, den MDA zuverlässig zu aktivieren, aber natürlich wird die Ursache des Problems somit nicht behoben.  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a>Lösung  
 Stellen Sie sicher, dass Sie <xref:System.IO.StreamWriter.Close%2A> oder <xref:System.IO.StreamWriter.Flush%2A> der <xref:System.IO.StreamWriter> oder eines beliebigen Codeblocks abrufen, der eine <xref:System.IO.StreamWriter>-Instanz enthält, bevor Sie eine Anwendung schließen. Eine der besten Mechanismen, um dies zu erreichen, ist das Erstellen der Instanz mithilfe des `using`-C#-Blocks (`Using` in Visual Basic), was sicherstellt, dass die <xref:System.IO.StreamWriter.Dispose%2A>-Methode für den Writer aufgerufen wurde, wodurch die Instanz ordnungsgemäß geschlossen wird.  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))
{  
    sw.WriteLine("Data");  
}  
```  
  
 Der folgende Code zeigt dieselbe Projektmappe mithilfe von `try/finally` anstelle von `using` an.  
  
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
  
 Wenn keine dieser Lösungen verwendet werden kann (z.B. wenn sich ein <xref:System.IO.StreamWriter> in einer statischen Variablen befindet und Sie den Code am Ende der Lebenszeit nicht problemlos ausführen können), sollte der Aufruf von <xref:System.IO.StreamWriter.Flush%2A> auf <xref:System.IO.StreamWriter> nach der letzten Verwendung oder die Einstellung der <xref:System.IO.StreamWriter.AutoFlush%2A>-Eigenschaft auf `true` vor der ersten Verwendung dieses Problem vermeiden.  
  
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
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die Laufzeit.  
  
## <a name="output"></a>Output  
 Eine Meldung, die angibt, dass diese Überschreitung aufgetreten ist.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.StreamWriter>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](diagnosing-errors-with-managed-debugging-assistants.md)
