---
title: "illegalPrepareConstrainedRegion MDA | Microsoft Docs"
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
  - "PrepareConstrainedRegions method"
  - "managed debugging assistants (MDAs), illegal PrepareConstrainedRegions"
  - "try/catch exception handling, managed debugging assistants"
  - "IllegalPrepareConstrainedRegions MDA"
  - "MDAs (managed debugging assistants), illegal PrepareConstrainedRegions"
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# illegalPrepareConstrainedRegion MDA
Der `illegalPrepareConstrainedRegion`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn der `try`\-Anweisung des Ausnahmehandlers nicht unmittelbar ein Aufruf der <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=fullName>\-Methode vorangestellt ist.  Diese Einschränkung gilt auf MSIL\-Ebene. Es ist deshalb zulässig, dass sich zwischen dem Aufruf und der `try`\-Anweisung Quellcode befindet, der keinen Code generiert \(z. B. Kommentare\).  
  
## Symptome  
 Ein eingeschränkter Ausführungsbereich \(Constrained Execution Region, CER\), der nicht als solcher behandelt wird, sondern als einfacher Ausnahmehandlerblock \(`finally` oder `catch`\).  Als Folge davon wird dieser Bereich bei nicht ausreichendem Speicherplatz oder im Fall eines Threadabbruchs nicht ausgeführt.  
  
## Ursache  
 Die Regeln zum Vorbereiten eines CER wurden nicht ordnungsgemäß befolgt.  Es handelt sich hierbei um ein Fehlerereignis.  Der Aufruf der <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>\-Methode, der zum Kennzeichnen des Beginns eines CER in den `catch`\/`finally`\/`fault`\/`filter`\-Blöcken von Ausnahmehandlern verwendet wird, muss direkt vor der `try`\-Anweisung erfolgen.  
  
## Lösung  
 Stellen Sie sicher, dass der Aufruf von <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> direkt vor der `try` `` \-Anweisung erfolgt.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
 Der MDA zeigt den Namen der Methode an, die die <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>\-Methode aufgerufen hat, den MSIL\-Offset und eine Meldung, die darauf hinweist, dass der Aufruf dem try\-Block nicht unmittelbar vorangestellt ist.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
 Im folgenden Codebeispiel ist der Ablauf dargestellt, der zum Aktivieren dieses MDA führt.  
  
```  
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)