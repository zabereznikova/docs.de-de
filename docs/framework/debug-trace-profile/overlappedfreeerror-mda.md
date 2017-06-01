---
title: "overlappedFreeError MDA | Microsoft Docs"
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
  - "OverlappedFreeError MDA"
  - "overlapped free method call error"
  - "managed debugging assistants (MDAs), overlapped structures"
  - "overlapped structures"
  - "MDAs (managed debugging assistants), overlapped structures"
  - "freeing overlapped structures"
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# overlappedFreeError MDA
Der `overlappedFreeError`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) ist aktiviert, wenn die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=fullName>\-Methode aufgerufen wird, bevor die überlappende Operation abgeschlossen ist.  
  
## Symptome  
 Zugriffsverletzungen oder Beschädigungen des Heaps der Garbage Collection  
  
## Ursache  
 Eine überlappende Struktur wurde vor Ende der Operation freigegeben.  Die Funktion, die den überlappenden Zeiger verwendet, schreibt möglicherweise später in die Struktur, nachdem diese freigegeben wurde.  Dies kann Heapschäden verursachen, da ein anderes Objekt jetzt diesen Bereich einnehmen könnte.  
  
 Dieser MDA stellt möglicherweise keinen Fehler dar, wenn die überlappende Operation nicht erfolgreich gestartet wurde.  
  
## Lösung  
 Stellen Sie sicher, dass der E\/A\-Vorgang mit der überlappenden Struktur vor dem Aufrufen der <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>\-Methode abgeschlossen wurde.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
 Im Folgenden finden Sie eine Beispielausgabe dieses MDAs.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'.  If the AppDomain is shut down, this can cause heap corruption when the async I/O completes.  The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack().  If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)