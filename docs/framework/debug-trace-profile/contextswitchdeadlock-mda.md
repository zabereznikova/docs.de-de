---
title: contextSwitchDeadlock-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
caps.latest.revision: 22
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cdb847c53f7aa4a38d67f55cae2f1df1eb638079
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="contextswitchdeadlock-mda"></a>contextSwitchDeadlock-MDA
Der `contextSwitchDeadlock`-MDA (Managed Debugging Assistant, Assistent für das verwaltete Debuggen) wird aktiviert, wenn während eines versuchten COM-Kontextübergangs ein Deadlock erkannt wird.  
  
## <a name="symptoms"></a>Symptome  
 Das häufigste Symptom ist, dass ein Aufruf einer nicht verwalteten COM-Komponente aus verwaltetem Code nicht zurückgegeben wird.  Ein weiteres Symptom ist die im Zeitverlauf zunehmende Speicherauslastung.  
  
## <a name="cause"></a>Ursache  
 Die wahrscheinlichste Ursache ist, dass ein Thread in einem Singlethread-Apartment (STA) keine Meldungen weiterleitet. Entweder wartet der STA-Thread, ohne Meldungen weiterzuleiten, oder er führt langwierige Operationen aus und lässt keine Weiterleitungen durch die Meldungswarteschlange zu.  
  
 Die im Zeitverlauf zunehmende Speicherauslastung wird durch den Finalizerthread verursacht, der versucht, `Release` für eine nicht verwaltete COM-Komponente aufzurufen, von der keine Rückgabe erfolgt.  Dadurch wird verhindert, dass der Finalizer andere Objekte freigibt.  
  
 Standardmäßig wird STA als Threadingmodell für den Hauptthread von Visual Basic-Konsolenanwendungen verwendet. Dieser MDA wird aktiviert, wenn ein STA-Thread COM-Interoperabilität entweder direkt oder indirekt über die Common Language Runtime oder ein Drittanbieter-Steuerelement verwendet.  Um zu vermeiden, das dieser MDA in einer Visual Basic-Konsolenanwendung aktiviert wird, wenden Sie das <xref:System.MTAThreadAttribute>-Attribut auf die Hauptmethode an, oder ändern Sie die Anwendung so, dass sie Meldungen weiterleitet.  
  
 Unter Umständen wird dieser MDA fälschlicherweise aktiviert, wenn alle folgenden Bedingungen erfüllt sind:  
  
-   Eine Anwendung erstellt entweder direkt oder indirekt über Bibliotheken COM-Komponenten von STA-Threads.  
  
-   Die Anwendung wurde im Debugger angehalten, und der Benutzer hat entweder die Ausführung der Anwendung fortgesetzt oder einen Ausführungsschritt durchgeführt.  
  
-   Nicht verwaltetes Debuggen ist nicht aktiviert.  
  
 Um festzustellen, ob der MDA fälschlicherweise aktiviert wurde, deaktivieren Sie alle Haltepunkte, starten Sie die Anwendung neu, und führen Sie sie ohne Unterbrechung aus. Wenn der MDA nicht aktiviert wird, war die erste Aktivierung wahrscheinlich falsch. Deaktivieren Sie in diesem Fall den MDA, um eine Störung der Debugsitzung zu vermeiden.  
  
> [!NOTE]
>  Dieser MDA befindet sich im Standardsatz für [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] und höhere Versionen. Wenn in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] der Hostprozess aktiviert ist, können Sie MDAs, die sind im Standardsatz befinden, nicht deaktivieren. Der Hostprozess wird standardmäßig aktiviert, sodass er explizit deaktiviert werden muss. Informationen zum Deaktivieren von MDAs finden Sie unter "Bereitstellen und Aufheben der Bereitstellung von MDAs" in [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="resolution"></a>Auflösung  
 Befolgen Sie die COM-Regeln hinsichtlich der STA-Meldungsweiterleitung.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR. Es werden nur Angaben über COM-Kontexte gemeldet.  
  
## <a name="output"></a>Ausgabe  
 Eine Meldung, die den aktuellen Kontext und den Zielkontext beschreibt.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <contextSwitchDeadlock />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop-Marshalling](../../../docs/framework/interop/interop-marshaling.md)

