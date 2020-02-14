---
title: CallbackOnCollectedDelegate-MDA
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- managed debugging assistants (MDAs), callback on collected delegates
- MDAs (managed debugging assistants), callback on collected delegates
- callback on delegate after garbage collection
- callbackOnCollectedDelegate MDA
- managed debugging assistants (MDAs), garbage collection
- call back collected delegates
- garbage collection, run-time errors
- delegates [.NET Framework], garbage collection
ms.assetid: 398b0ce0-5cc9-4518-978d-b8263aa21e5b
ms.openlocfilehash: eb14e0df5396d92eb223dde2e562684c4c318295
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217565"
---
# <a name="callbackoncollecteddelegate-mda"></a>CallbackOnCollectedDelegate-MDA
Der `callbackOnCollectedDelegate`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn das Marshalling eines Delegaten von verwaltetem zu nicht verwaltetem Code als Funktionszeiger durchgeführt wird und nach der Garbage Collection des Delegaten ein Rückruf mit diesem Funktionszeiger erfolgt.  
  
## <a name="symptoms"></a>Symptome  
 Beim Versuch, mithilfe von aus verwalteten Delegaten stammenden Funktionszeigern verwalteten Code aufzurufen, treten Zugriffsverletzungen auf. Ursache der Zugriffsverletzungen sind keine Programmfehler der CLR (Common Language Runtime), auch wenn dieser Eindruck entsteht, da sie im CLR-Code auftreten.  
  
 Der Fehler ist nicht konsistent. Manchmal ist der Aufruf mit dem Funktionszeiger erfolgreich und manchmal nicht. Der Fehler tritt möglicherweise nur bei hoher Auslastung oder bei einer zufälligen Anzahl von Versuchen auf.  
  
## <a name="cause"></a>Ursache  
 Für den Delegaten, von dem der Funktionszeiger erstellt und dem nicht verwaltetem Code verfügbar gemacht wurde, erfolgte die Garbage Collection. Wenn die nicht verwaltete Komponente versucht, einen Aufruf mit dem Funktionszeiger durchzuführen, wird eine Zugriffsverletzung generiert.  
  
 Das Auftreten des Fehlers ist nicht vorhersagbar, da er vom Zeitpunkt der Garbage Collection abhängt. Wenn ein Delegat für die Garbage Collection freigegeben ist und diese nach dem Rückruf erfolgt, ist der Aufruf erfolgreich. Wenn zu einem anderen Zeitpunkt die Garbage Collection vor dem Rückruf erfolgt, tritt eine Zugriffsverletzung auf, und das Programm wird beendet.  
  
 Die Fehlerwahrscheinlichkeit hängt vom Zeitraum zwischen dem Marshalling des Delegaten und dem Rückruf mithilfe des Funktionszeigers sowie von der Häufigkeit der Garbage Collection ab. Der Fehler tritt sporadisch auf, wenn der Zeitraum zwischen dem Marshalling des Delegaten und dem folgenden Rückruf kurz ist. Dies ist gewöhnlich der Fall, wenn die nicht verwaltete Methode, der der Funktionszeiger übergeben wird, diesen nicht zur späteren Verwendung speichert, sondern mit ihm sofort einen Rückruf ausführt, um den entsprechenden Vorgang vor dem Verlassen der Methode abzuschließen. Die Häufigkeit der Garbage Collection erhöht sich auch, wenn ein System stark ausgelastet ist. Dabei steigt die Wahrscheinlichkeit, dass vor dem Rückruf eine Garbage Collection erfolgt.  
  
## <a name="resolution"></a>Lösung  
 Nach dem Marshalling eines Delegaten in einen nicht verwalteten Funktionszeiger ist es für den Garbage Collector unmöglich, dessen Lebensdauer zu überwachen. Stattdessen muss der Programmcode für die Lebensdauer des nicht verwalteten Funktionszeigers einen Verweis auf den Delegaten aufbewahren. Bevor dies jedoch möglich ist, müssen Sie zuerst ermitteln, welcher Delegat durch die Garbage Collection bereinigt wurde. Wenn der MDA aktiviert wird, stellt er den Typnamen des Delegaten bereit. Durchsuchen Sie mithilfe dieses Namens den Programmcode nach Plattformaufruf- oder COM-Signaturen, die einen Delegaten an nicht verwalteten Code übergeben. Der problematische Delegat wird über einen dieser Aufrufsites übergeben. Sie können auch den `gcUnmanagedToManaged`-MDA aktivieren, um vor jedem Rückruf in die CLR eine Garbage Collection zu erzwingen. Auf diese Weise wird die durch die Garbage Collection bedingte Ungewissheit beseitigt, indem sichergestellt wird, dass vor dem Rückruf stets eine Garbage Collection erfolgt. Nachdem Sie ermittelt haben, welcher Delegat durch die Garbage Collection erfasst wurde, ändern Sie den Programmcode so, dass für die Lebensdauer des gemarshallten nicht verwalteten Funktionszeigers ein Verweis auf diesen Delegaten auf der verwalteten Seite verbleibt.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Beim Marshalling von Delegaten als Funktionszeiger wird von der CLR ein Thunk zugeordnet, der für den Übergang vom nicht verwalteten zum verwalteten Code sorgt. Der nicht verwaltete Code ruft dann diesen Thunk auf, bevor schließlich der verwaltete Delegat aufgerufen wird. Ohne aktivierten `callbackOnCollectedDelegate`-MDA wird der nicht verwaltete Marshallingcode gelöscht, wenn für den Delegaten die Garbage Collection erfolgt. Mit aktiviertem `callbackOnCollectedDelegate`-MDA wird der nicht verwaltete Marshallingcode nicht sofort gelöscht, wenn für den Delegaten die Garbage Collection erfolgt. Vielmehr werden standardmäßig die letzten 1.000 Instanzen aufbewahrt und geändert, um bei einem Aufruf den MDA zu aktivieren. Der Thunk wird schließlich gelöscht, nachdem für weitere 1.001 gemarshallte Delegaten die Garbage Collection erfolgte.  
  
## <a name="output"></a>Output  
 Der MDA meldet den Typnamen des Delegaten, für den vor einem Rückruf mithilfe des entsprechenden nicht verwalteten Funktionszeigers eine Garbage Collection erfolgte.  
  
## <a name="configuration"></a>Konfiguration  
 Im folgenden Beispiel sind die Konfigurationsoptionen der Anwendung dargestellt. Dabei wird als Anzahl der vom MDA aktiv gehaltenen Thunks 1.500 festgelegt. Der Standardwert für `listSize` beträgt 1.000, der Mindestwert 50 und der Höchstwert 2.000.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann:  
  
```cpp
// Library.cpp : Defines the unmanaged entry point for the DLL application.  
#include "windows.h"  
#include "stdio.h"  
  
void (__stdcall *g_pfTarget)();  
  
void __stdcall Initialize(void __stdcall pfTarget())  
{  
    g_pfTarget = pfTarget;  
}  
  
void __stdcall Callback()  
{  
    g_pfTarget();  
}
```

```csharp
// C# Client  
using System;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public delegate void DCallback();  
  
    public static void Main()  
    {  
        new Entry();  
        Initialize(Target);  
        GC.Collect();  
        GC.WaitForPendingFinalizers();  
        Callback();  
    }  
  
    public static void Target()  
    {          
    }  
  
    [DllImport("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Initialize(DCallback pfDelegate);  
  
    [DllImport ("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Callback();  
  
    ~Entry() { Console.Error.WriteLine("Entry Collected"); }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
- [gcUnmanagedToManaged](gcunmanagedtomanaged-mda.md)
