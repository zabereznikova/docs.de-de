---
title: Reentranz-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, debugging
- transitioning threads unmanaged to managed code
- reentrancy MDA
- reentrancy without an orderly transition
- managed debugging assistants (MDAs), reentrancy
- illegal reentrancy
- MDAs (managed debugging assistants), reentrancy
- threading [.NET Framework], managed debugging assistants
- managed code, debugging
- native debugging, MDAs
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
ms.openlocfilehash: 5cbe8e843ad72785010240f3db30b1d344c80650
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181764"
---
# <a name="reentrancy-mda"></a>Reentranz-MDA
Der `reentrancy`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn versucht wird, von nativem zu verwaltetem Code überzugehen, und wenn ein vorheriger Wechsel von verwaltetem zu nativem Code nicht über einen ordnungsgemäßen Übergang ausgeführt wurde.  
  
## <a name="symptoms"></a>Symptome  
 Der Objektheap ist beschädigt oder es treten andere schwerwiegende Fehler beim Übergang von nativem zu verwaltetem Code auf.  
  
 Threads, die zwischen nativem und verwaltetem Code in beide Richtungen wechseln, müssen einen ordnungsgemäßen Übergang durchführen. Allerdings erlauben bestimmte Erweiterbarkeitspunkte auf niedriger Ebene, wie beispielsweise Ausnahmehandler von Vektoren, dass Schalter ohne ordnungsgemäßen Übergang aus verwaltetem zu nativem Code wechseln.  Diese Schalter werden vom Betriebssystem gesteuert und nicht von der Common Language Runtime (CLR).  Jede native Code, der in diesen Erweiterungspunkten ausgeführt wird, muss Rückrufe in verwaltetem Code vermeiden.  
  
## <a name="cause"></a>Ursache  
 Ein Erweiterungspunkt auf niedriger Ebene, wie z.B. der Ausnahmehandler für Vektoren, wurde während der Ausführung von verwaltetem Code aktiviert.  Der Anwendungscode, der über diesen Erweiterungspunkt aufgerufen wird, versucht einen Rückruf in verwaltetem Code.  
  
 Dieses Problem wird immer durch den Anwendungscode verursacht.  
  
## <a name="resolution"></a>Lösung  
 Überprüfen Sie die Stapelüberwachung für den Thread, der diesen MDA aktiviert hat.  Der Thread versucht illegal verwalteten Code aufzurufen.  Die Stapelüberwachung sollte den Anwendungscode, der diesen Erweiterungspunkt nutzt, den Code des Betriebssystems, der diesen Erweiterungspunkt bereitstellt, und den verwalteten Code, der durch den Erweiterungspunkt unterbrochen wurde, anzeigen.  
  
 Sie sehen beispielsweise, dass der MDA bei einem Versuch aktiviert wird, bei dem verwalteter Code innerhalb eines Ausnahmehandlers für Vektoren aufgerufen wird.  Auf dem Stapel sehen Sie den Code für die Ausnahmebehandlung des Betriebssystems und verwalteten Code wie z.B. <xref:System.DivideByZeroException> oder <xref:System.AccessViolationException>, der eine Ausnahme auslöst.  
  
 In diesem Beispiel ist die richtige Lösung die vollständige Implementierung des Ausnahmehandlers für Vektoren in nicht verwaltetem Code.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Output  
 Der MDA meldet, dass ungültiges Wiedereintreten versucht wird.  Überprüfen Sie die Threadstapel, um zu bestimmen, warum dies geschieht und wie Sie das Problem beheben können. Nachfolgend ist die Ausgabe des Beispiels aufgeführt.  
  
```output
Additional Information: Attempting to call into managed code without
transitioning out first.  Do not attempt to run managed code inside
low-level native extensibility points. Managed Debugging Assistant
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine <xref:System.AccessViolationException> ausgelöst wird.  Bei Windows-Versionen, die Ausnahmebehandlung für Vektoren unterstützen, wird der verwaltete Ausnahmehandler für Vektoren aufgerufen.  Wenn der `reentrancy`-MDA aktiviert ist, wird der MDA beim versuchten Aufruf von `MyHandler` aus dem Unterstützungscode des Ausnahmebehandlers für Vektoren aufgerufen.  
  
```csharp
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try
        {  
            // Dispatch on null should AV.  
            Reenter r = null;
            r.Run();  
        }
        catch { }  
    }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](diagnosing-errors-with-managed-debugging-assistants.md)
