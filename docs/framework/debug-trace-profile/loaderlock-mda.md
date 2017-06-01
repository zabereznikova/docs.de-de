---
title: "loaderLock MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "deadlocks [.NET Framework]"
  - "LoaderLock MDA"
  - "MDAs (managed debugging assistants), loader locks"
  - "managed debugging assistants (MDAs), loader locks"
  - "operating system loader locks"
  - "loader locks"
  - "locks, threads"
ms.assetid: 8c10fa02-1b9c-4be5-ab03-451d943ac1ee
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# loaderLock MDA
Der `loaderLock`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) erkennt Versuche, verwalteten Code für einen Thread auszuführen, der die Sperre für das Microsoft Windows\-Betriebssystemladeprogramm enthält.  Eine solche Ausführung ist ungültig, weil sie zu Deadlocks und der Verwendung von DLLs führen kann, bevor diese vom Betriebssystemladeprogramm initialisiert wurden.  
  
## Symptome  
 Der häufigste Fehler beim Ausführen von Code innerhalb der Sperre des Betriebssystemladeprogramms ist ein Deadlock bei Threads, die versuchen, andere Win32\-Funktionen aufzurufen, für die ebenfalls der Sperre des Ladeprogramms erforderlich ist.  Beispiele für diese Funktionen sind `LoadLibrary`, `GetProcAddress`, `FreeLibrary` und `GetModuleHandle`.  Möglicherweise werden diese Funktionen nicht direkt von der Anwendung aufgerufen, sondern von der CLR \(Common Language Runtime\) als Ergebnis eines Aufrufs auf einer höheren Ebene wie <xref:System.Reflection.Assembly.Load%2A> oder des ersten Aufrufs einer Plattformaufrufmethode.  
  
 Deadlocks können auch auftreten, wenn ein Thread auf den Start oder das Ende eines anderen Threads wartet.  Wenn ein Thread mit der Ausführung beginnt oder die Ausführung beendet, muss dieser die Sperre des Betriebssystemladeprogramms erhalten, um Ereignisse an betroffene DLLs zu übermitteln.  
  
 Außerdem gibt es Situationen, in denen Aufrufe in DLLs erfolgen, bevor diese DLLs ordnungsgemäß durch das Betriebssystemladeprogramm initialisiert wurden.  Im Gegensatz zu Fehler aufgrund von Deadlocks, die durch Untersuchen der Stapel aller am Deadlock beteiligten Threads diagnostiziert werden können, kann die Verwendung von nicht initialisierten DLLs ohne diesen MDA nur schwer festgestellt werden.  
  
## Ursache  
 Bei C\+\+\-Assemblys mit einer Mischung aus verwaltetem und nicht verwaltetem Code, die für .NET Framework 1.0 oder 1.1 erstellt wurden, wird im Allgemeinen versucht, verwalteten Code innerhalb der Sperre des Ladeprogramms auszuführen, sofern keine besonderen Vorkehrungen wie eine Verknüpfung mit **\/NOENTRY** getroffen wurden.  Eine ausführliche Beschreibung dieser Probleme finden Sie in "Gemischtem DLL\-Ladenproblem" in der MSDN Library.  
  
 Bei C\+\+\-Assemblys mit einer Mischung aus verwaltetem und nicht verwaltetem Code, die für .NET Framework 2.0 erstellt wurden, ist das Risiko kleiner, auf diese Probleme zu treffen. Es entspricht dem von Anwendungen, die nicht verwaltete DLLs verwenden und die Regeln des Betriebssystems verletzen.  Wenn beispielsweise im Einstiegspunkt `DllMain` einer nicht verwalteten DLL `CoCreateInstance` aufgerufen wird, um ein verwaltetes Objekt abzurufen, das für COM verfügbar gemacht wurde, führt das zu einem Versuch, verwalteten Code innerhalb der Sperre des Ladeprogramms auszuführen.  Weitere Informationen zu Problemen mit Ladeprogrammsperren in .NET Framework, Version 2.0 und höher, finden Sie unter [Initialisierung gemischter Assemblys](../Topic/Initialization%20of%20Mixed%20Assemblies.md).  
  
## Lösung  
 In Visual C\+\+ .NET 2002 und Visual C\+\+ .NET 2003 mit der Compileroption `/clr` kompilierte DLLs konnten beim Laden nicht deterministische Deadlocks verursachen. Dieses Problem kann als Ladeprogrammsperre\-Fehler oder Ladefehler einer gemischten DLL bezeichnet werden.  In Visual C\+\+ 2005 und höher wurde nahezu jeglicher Nicht\-Determinismus aus dem Ladeprozess bei gemischten DLLs entfernt.  Es gibt jedoch weiterhin Szenarien, bei denen die Ladeprogrammsperre \(deterministisch\) auftreten kann.  Eine detaillierte Schilderung der Ursachen und Lösungen für die verbleibenden Probleme mit der Ladeprogrammsperre finden Sie unter [Initialisierung gemischter Assemblys](../Topic/Initialization%20of%20Mixed%20Assemblies.md).  Wenn Sie in diesem Thema keine Lösung für Ihr Problem mit einer Ladeprogrammsperre finden, müssen Sie den Stapel des Threads untersuchen, um herauszufinden, warum die Ladeprogrammsperre auftritt und wie dies verhindert werden kann.  Untersuchen Sie die Stapelüberwachung für den Thread, der diesen MDA aktiviert hat.  Der Thread versucht ungültigerweise, einen Aufruf in den verwalteten Code durchzuführen, während er die Sperre des Betriebssystemladeprogramms hält.  Wahrscheinlich wird auf dem Stapel `DllMain` oder ein entsprechender Einstiegspunkt einer DLL angezeigt.  Die Regeln des Betriebssystems schränken die gültigen Vorgänge nach Erreichen des Einstiegspunkt relativ stark ein.  Diese Regeln schließen jede Ausführung von verwaltetem Code aus.  
  
## Auswirkungen auf die Laufzeit  
 I. d. R. sind mehrere Threads im Prozess am Deadlock beteiligt.  Einer dieser Threads ist wahrscheinlich ein Thread zum Ausführen einer Garbage Collection. Dieser Deadlock kann also umfangreiche Auswirkungen auf den gesamten Prozess haben.  Außerdem werden dadurch jegliche weiteren Vorgänge verhindert, für die die Sperre des Betriebssystemladeprogramms erforderlich sind, z. B. das Laden und Entladen von Assemblys oder DLLs sowie das Starten oder Beenden von Threads.  
  
 In einigen ungewöhnlichen Situationen ist es darüber hinaus möglich, dass Zugriffsverletzungen oder ähnliche Probleme in DLLs auftreten, die aufgerufen werden, bevor sie initialisiert wurden.  
  
## Ausgabe  
 Dieser MDA meldet, dass eine ungültige Ausführung von verwaltetem Code versucht wird.  Sie müssen den Stapel des Threads untersuchen, um zu ermitteln, warum das Ladeprogramm gesperrt ist und wie das Problem behoben werden kann.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <loaderLock/>  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)