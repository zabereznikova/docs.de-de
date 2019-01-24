---
title: dangerousThreadingAPI-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3cfbc1439be457987c058ee6d0298e93aa37f5d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716012"
---
# <a name="dangerousthreadingapi-mda"></a>dangerousThreadingAPI-MDA
Der `dangerousThreadingAPI`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>-Methode für einen anderen Thread als den aktuellen Thread aufgerufen wird.  
  
## <a name="symptoms"></a>Symptome  
 Eine Anwendung reagiert nicht oder bleibt auf unbestimmte Zeit hängen. Die System- oder Anwendungsdaten befinden sich vorübergehend oder selbst nach Herunterfahren der Anwendung in einem unvorhersehbaren Zustand. Einige Vorgänge werden nicht wie erwartet abgeschlossen.  
  
 Aufgrund des willkürlichen Auftretens dieses Problems ist ein breites Spektrum unterschiedlicher Symptome möglich.  
  
## <a name="cause"></a>Ursache  
 Ein Thread wird von einem anderen Thread mit der <xref:System.Threading.Thread.Suspend%2A>-Methode asynchron angehalten. Es gibt keine Möglichkeit festzustellen, wann ein anderer Thread sicher angehalten werden kann, der sich möglicherweise gerade mitten in einem Vorgang befindet. Das Anhalten eines Threads kann zur Beschädigung von Daten oder Invarianten führen. Befindet sich ein Thread in angehaltenem Zustand und wird nicht mit der <xref:System.Threading.Thread.Resume%2A>-Methode fortgesetzt, kann die Anwendung auf unbestimmte Zeit hängen bleiben und Anwendungsdaten beschädigen. Diese Methoden wurden als veraltet markiert.  
  
 Für den Zielthread reservierte Synchronisierungsprimitiven bleiben während der Unterbrechung reserviert. Dies kann zu Deadlocks führen, sollte ein anderer Thread versuchen, die Primitive zu sperren (z.B. der Thread, der <xref:System.Threading.Thread.Suspend%2A> ausführt). In diesem Fall wird das Problem als Deadlock sichtbar.  
  
## <a name="resolution"></a>Auflösung  
 Vermeiden Sie Entwürfe, die die Verwendung von <xref:System.Threading.Thread.Suspend%2A> und <xref:System.Threading.Thread.Resume%2A> erfordern. Verwenden Sie für die Zusammenarbeit zwischen Threads Synchronisierungsprimitiven wie beispielsweise <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> oder die C#-Anweisung `lock`. Wenn Sie diese Methoden verwenden müssen, verringern Sie das Zeitfenster, und minimieren Sie die Codemenge, die ausgeführt wird, während sich der Thread in angehaltenem Zustand befindet.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR. Es werden nur Angaben über problematische Threadoperationen gemeldet.  
  
## <a name="output"></a>Output  
 Der MDA identifiziert die problematische Threadmethode, die zu seiner Aktivierung führte.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht einen Aufruf der <xref:System.Threading.Thread.Suspend%2A>-Methode, der zur Aktivierung des `dangerousThreadingAPI` führt.  
  
```csharp
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Threading.Thread>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [lock-Anweisung](~/docs/csharp/language-reference/keywords/lock-statement.md)
