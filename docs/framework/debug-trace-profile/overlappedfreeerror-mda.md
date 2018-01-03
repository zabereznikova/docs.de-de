---
title: overlappedFreeError-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e17e9d6a93b69d358e89109cf965b7b9856c325
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="overlappedfreeerror-mda"></a>overlappedFreeError-MDA
Der `overlappedFreeError`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType>-Methode aufgerufen wird, bevor der überlappende Vorgang abgeschlossen ist.  
  
## <a name="symptoms"></a>Symptome  
 Zugriffsverletzungen oder Beschädigungen des Heaps der Garbage Collection.  
  
## <a name="cause"></a>Ursache  
 Eine überlappende Struktur wurde freigegeben, bevor der Vorgang abgeschlossen wurde. Die Funktion, die den überlappenden Zeiger verwendet, wird möglicherweise später auf die Struktur schreiben, nachdem dieser freigegeben wurde. Dies kann den Heap beschädigen, da ein anderes Objekt jetzt diesen Bereich einnehmen kann.  
  
 Dieser MDA stellt möglicherweise keine Fehler dar, wenn der überlappende Vorgang nicht erfolgreich gestartet wurde.  
  
## <a name="resolution"></a>Auflösung  
 Stellen Sie sicher, dass der E/A-Vorgang die überlappende Struktur verwendet, bevor Sie die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>-Methode aufrufen.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Ausgabe  
 Nachfolgend wird eine Beispielausgabe für diesen MDA angezeigt.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
