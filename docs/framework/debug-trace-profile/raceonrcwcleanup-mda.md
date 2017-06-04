---
title: "raceOnRCWCleanup MDA | Microsoft Docs"
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
  - "RCW"
  - "managed debugging assistants (MDAs), RCWs"
  - "race on RCW cleanup"
  - "MDAs (managed debugging assistants), RCWs"
  - "RaceOnRCWCleanup MDA"
  - "runtime callable wrappers"
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# raceOnRCWCleanup MDA
Der `raceOnRCWCleanup`\-Assistent für verwaltetes Debuggen \(Managed Debugging Assistant, MDA\) wird aktiviert, wenn die CLR \(Common Language Runtime\) ermittelt, dass ein [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) \(verwendet wird, wenn ein Aufruf zum Freigeben mithilfe eines Befehls wie etwa der Methode <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName> erfolgt.  
  
## Symptome  
 Zugriffsverletzungen oder Speicherschäden während oder nach dem Freigeben eines RCW mithilfe von <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> oder einer ähnlichen Methode.  
  
## Ursache  
 Der RCW wird in einem anderen Thread oder für den freigebenden Threadstapel verwendet.  Ein RCW, der verwendet wird, kann nicht freigegeben werden.  
  
## Auflösung  
 Geben Sie einen RCW, der im aktuellen Thread oder in anderen Threads verwendet wird, nicht frei.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
 Eine Meldung mit einer Beschreibung des Fehlers.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)