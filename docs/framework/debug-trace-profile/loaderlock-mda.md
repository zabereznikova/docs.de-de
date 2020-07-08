---
title: loaderLock-MDA
description: Überprüfen Sie den loaderLock-MDA (Managed Debugging Assistant) in .net, der versucht, verwalteten Code in einem Thread auszuführen, der die Windows-Betriebssystem Lade Sperre enthält.
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- LoaderLock MDA
- MDAs (managed debugging assistants), loader locks
- managed debugging assistants (MDAs), loader locks
- operating system loader locks
- loader locks
- locks, threads
ms.assetid: 8c10fa02-1b9c-4be5-ab03-451d943ac1ee
ms.openlocfilehash: 055b07a805c5f0b613519d6019950a9b249a4b38
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051621"
---
# <a name="loaderlock-mda"></a>loaderLock-MDA
Der `loaderLock`-MDA (Assistent für verwaltetes Debuggen) erkennt Versuche zur Ausführung von verwaltetem Code in einem Thread, der die Loadersperre für das Microsoft Windows-Betriebssystem enthält.  Eine solche Ausführung ist ungültig, da sie zu Deadlocks führen und DLLs verwenden kann, bevor sie vom Ladeprogramm des Betriebssystems initialisiert wird.  
  
## <a name="symptoms"></a>Symptome  
 Der häufigste Fehler beim Ausführen von Code innerhalb der Loadersperre des Betriebssystems ist, dass Threads beim Versuch, andere Win32-Funktionen aufzurufen, die ebenfalls die Loadersperre erfordern, einen Deadlock auslösen.  Beispiele für solche Funktionen sind `LoadLibrary`, `GetProcAddress`, `FreeLibrary` und `GetModuleHandle`.  Die Anwendung ruft diese Funktionen möglicherweise nicht direkt auf. Die Common Language Runtime (CLR) ruft diese Funktionen möglicherweise als Ergebnis eines Aufrufs der höheren Ebene wie <xref:System.Reflection.Assembly.Load%2A> oder als ersten Aufruf an eine Plattformaufrufmethode auf.  
  
 Deadlocks können auch auftreten, wenn ein Thread wartet, dass ein anderer Thread startet oder endet.  Wenn ein Thread gestartet oder abgeschlossen wurde, muss die Loadersperre des Betriebssystems Ereignisse an betroffene DLLs übertragen.  
  
 Schließlich gibt es Fälle, in denen Aufrufe in DLLs auftreten können, bevor diese DLLs ordnungsgemäß vom Ladeprogramm des Betriebssystems initialisiert wurden.  Im Gegensatz zu den Deadlock-Fehlern, die durch Untersuchen der Stapel aller am Deadlock beteiligten Threads diagnostiziert werden können, ist es sehr schwierig, die Verwendung von nicht initialisierten DLLs ohne diesen MDA zu diagnostizieren.  
  
## <a name="cause"></a>Ursache  
 Eine Mischung aus verwalteten und nicht verwalteten C++-Assemblys für die .NET Framework-Versionen 1.0 oder 1.1 versucht in der Regel, verwalteten Code innerhalb der Loadersperre auszuführen, es sei denn, es wurde besondere Sorgfalt angewendet und z.B. eine Verknüpfung mit **/NOENTRY** erstellt.
  
 Eine Mischung aus verwalteten und nicht verwalteten C++-Assemblys für die .NET Framework-Versionen 2.0 ist weniger anfällig für diese Probleme und hat dasselbe verringerte Risiko wie Anwendungen, die nicht verwaltete DLLs verwenden, die gegen die Regeln des Betriebssystems verstoßen.  Wenn beispielsweise der `DllMain`-Einstiegspunkt einer nicht verwalteten DLL `CoCreateInstance` aufruft, um ein verwaltetes Objekt zu erhalten, das für COM verfügbar gemacht wurde, erhält man einen Versuch, verwalteten Code innerhalb der Loadersperre auszuführen. Weitere Informationen zu Problemen mit Loadersperren in .NET Framework Version 2.0 oder höher finden Sie unter [Initialization of Mixed Assemblies (Initialisierung gemischter Assemblys)](/cpp/dotnet/initialization-of-mixed-assemblies).  
  
## <a name="resolution"></a>Lösung  
 In Visual C++ .NET 2002 und Visual C++ .NET 2003 konnten mit der Compileroption `/clr` kompilierte DLLs beim Laden nicht deterministische Deadlocks laden. Dies wurde als Problem beim Laden gemischter DLLs bzw. Loadersperrenproblem bezeichnet. In Visual C++ 2005 und höher wurde fast der gesamte Nichtdeterminismus aus dem Prozess des Ladens gemischter DLLs entfernt. Es verbleiben jedoch weiterhin ein paar Szenarien, bei denen die Loadersperre (deterministisch) auftreten kann. Eine ausführliche Beschreibung der Ursachen und Lösungen für die verbleibenden Loadersperrenprobleme finden Sie unter [Initialization of Mixed Assemblies (Initialisierung gemischter Assemblys)](/cpp/dotnet/initialization-of-mixed-assemblies). Wenn dieses Thema Ihr Loadersperrenproblem nicht abdeckt, dann überprüfen Sie die Threadstapel, um zu bestimmen, warum die Loadersperre geschieht und wie Sie das Problem beheben können. Überprüfen Sie die Stapelüberwachung für den Thread, der diesen MDA aktiviert hat.  Der Thread versucht, verwalteten Code auf illegale Weise aufzurufen, während die Loadersperre des Betriebssystems gehalten wird.  Sie werden wahrscheinlich ein `DllMain` einer DLL oder den entsprechenden Einstiegspunkt auf dem Stapel sehen.  Die Regeln des Betriebssystems für innerhalb dieses Einstiegspunkts legale Verwendungsmöglichkeiten sind recht eingeschränkt.  Diese Regeln schließen eine nicht verwaltete Ausführung aus.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 In der Regel wird für mehrere Threads innerhalb des Prozesses ein Deadlock auftreten.  Einer dieser Threads ist wahrscheinlich der Thread, der für die Ausführung einer Garbage Collection verantwortlich ist, sodass dieser Deadlock erhebliche Auswirkungen auf den gesamten Prozess haben kann.  Darüber hinaus werden weitere Vorgänge verhindert, die die Loadersperre des Betriebssystems erfordern, wie das Laden und Entladen von Assemblys oder DLLs und das Starten oder Beenden von Threads.  
  
 In einigen seltenen Fällen ist es auch möglich, dass Zugriffsverletzungen oder ähnlichen Probleme in DLLs ausgelöst werden, die vor ihrer Initialisierung aufgerufen wurden.  
  
## <a name="output"></a>Ausgabe  
 Dieser MDA meldet, dass eine ungültige verwaltete Ausführung versucht wird.  Überprüfen Sie die Threadstapel, um zu bestimmen, warum die Loadersperre geschieht und wie Sie das Problem beheben können.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loaderLock/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
