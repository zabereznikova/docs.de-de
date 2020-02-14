---
title: asynchronousThreadAbort-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- asynchronous thread aborts
- AsynchronousThreadAbort MDA
- managed debugging assistants (MDAs), asynchronous thread aborts
- threading [.NET Framework], managed debugging assistants
- MDAs (managed debugging assistants), asynchronous thread aborts
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
ms.openlocfilehash: d0c78e6d52ae4a5b3a24e0bb4278b2e8a1b98751
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217579"
---
# <a name="asynchronousthreadabort-mda"></a>asynchronousThreadAbort-MDA
Der `asynchronousThreadAbort`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein Thread versucht, einen asynchronen Abbruch in einem anderen Thread hervorzurufen. Der `asynchronousThreadAbort`-MDA wird nicht durch synchrone Threadabbrüche aktiviert.

## <a name="symptoms"></a>Symptome
 Eine Anwendung stürzt mit einer nicht behandelten <xref:System.Threading.ThreadAbortException> ab, wenn der Thread der Hauptanwendung abgebrochen wird. Die Folgen der fortgesetzten Ausführung dieser Anwendung sind möglicherweise schwerwiegender als ein Absturz und können zur weiteren Beschädigung von Daten führen.

 Als unteilbar konzipierte Vorgänge wurden wahrscheinlich nach der partiellen Fertigstellung unterbrochen. Dadurch befinden sich die Anwendungsdaten nun in einem nicht vorhersagbaren Zustand. Eine <xref:System.Threading.ThreadAbortException> kann während der Ausführung von Programmcode an scheinbar zufälligen Stellen generiert werden, häufig auch an Stellen, an denen das Auslösen einer Ausnahme nicht zu erwarten war. Der Code ist möglicherweise nicht in der Lage, so eine Ausnahme zu behandeln. Dies führt zu einem fehlerhaften Zustand.

 Aufgrund des willkürlichen Auftretens dieses Problems ist ein breites Spektrum unterschiedlicher Symptome möglich.

## <a name="cause"></a>Ursache
 Die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode wurde aus dem Code in einem Thread für einen Zielthread aufgerufen, um einen asynchronen Threadabbruch hervorzurufen. Der Threadabbruch ist asynchron, da der die <xref:System.Threading.Thread.Abort%2A>-Methode aufrufende Code in einem anderen Thread ausgeführt wird als das Ziel des Abbruchvorgangs. Synchrone Threadabbrüche stellen in der Regel kein Problem dar, da ein Thread die <xref:System.Threading.Thread.Abort%2A>-Methode dabei nur an einem sicheren Anhaltepunkt aufrufen sollte, an dem sich die Anwendung in einem konsistenten Zustand befindet.

 Asynchrone Threadabbrüche führen zu Problemen, da sie an nicht vorhersagbaren Stellen der Ausführung des Zielthreads verarbeitet werden. In einem Thread ausgeführter Code, der möglicherweise asynchron abgebrochen wird, müsste zum Vermeiden dieses Problems für jede einzelne Codezeile eine <xref:System.Threading.ThreadAbortException> abfangen können, um dafür zu sorgen, dass die Anwendungsdaten anschließend in einem konsistenten Zustand vorliegen. Es ist jedoch unrealistisch zu erwarten, dass Code unter Berücksichtigung dieses Problems erstellt wurde, oder selbst Code zu verfassen, der Schutz vor allen möglichen Umständen bietet.

 Aufrufe von nicht verwaltetem Code und von `finally`-Blöcken werden nicht asynchron abgebrochen, sondern sofort nach dem Verlassen einer dieser Kategorien.

 Aufgrund des willkürlichen Auftretens dieses Problems ist die Ursache möglicherweise schwer zu ermitteln.

## <a name="resolution"></a>Lösung
 Vermeiden Sie Codeentwürfe, die die Verwendung asynchroner Threadabbrüche erfordern. Es gibt mehrere besser geeignete Verfahren zum Unterbrechen eines Zielthreads, die keinen Aufruf von <xref:System.Threading.Thread.Abort%2A> erfordern. Am sichersten ist der Einsatz eines Mechanismus, z.B. eine gemeinsame Eigenschaft, mit der dem Zielprozess die Unterbrechungsanforderung signalisiert wird. Der Zielthread prüft an bestimmten sicheren Anhaltepunkten, ob das Signal übermittelt wurde. Wenn eine Unterbrechungsanforderung festgestellt wird, kann der Thread ordnungsgemäß beendet werden.

## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit
 Dieser MDA hat keine Auswirkungen auf die CLR. Es werden nur Angaben zu asynchronen Threadabbrüchen gemeldet.

## <a name="output"></a>Output
 Der MDA meldet die ID des Threads, der den Abbruch durchführt, und die ID des Zielthreads für den Abbruch. Diese sind niemals gleich, da dieses Problem auf asynchrone Abbrüche beschränkt ist.

## <a name="configuration"></a>Konfiguration

```xml
<mdaConfig>
  <assistants>
    <asynchronousThreadAbort />
  </assistants>
</mdaConfig>
```

## <a name="example"></a>Beispiel
 Zum Aktivieren des `asynchronousThreadAbort`-MDA genügt ein Aufruf von <xref:System.Threading.Thread.Abort%2A> für einen separaten laufenden Thread. Bedenken Sie die Folgen, wenn der Inhalt der Threadstartfunktion aus einer Reihe komplexerer Vorgänge bestehen würde, die an jedem beliebigen Punkt durch den Abbruch unterbrochen werden können.

```csharp
using System.Threading;
void FireMda()
{
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });
    t.Start();
    // The following line activates the MDA.
    t.Abort();
    t.Join();
}
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Thread>
- [Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)](diagnosing-errors-with-managed-debugging-assistants.md)
