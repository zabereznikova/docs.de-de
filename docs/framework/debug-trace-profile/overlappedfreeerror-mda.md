---
title: overlappedFreeError-MDA
description: Überprüfen Sie den overlappedfreerror Managed Debug Assistant (MDA) in .net, der bei Zugriffs Verletzungen oder Beschädigungen des Garbage Collection-Heaps aktiviert werden kann.
ms.date: 03/30/2017
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
ms.openlocfilehash: 9be33c59723ecb2743f2bc610d7fb69d24ff388c
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803913"
---
# <a name="overlappedfreeerror-mda"></a>overlappedFreeError-MDA
Der `overlappedFreeError`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType>-Methode aufgerufen wird, bevor der überlappende Vorgang abgeschlossen ist.  
  
## <a name="symptoms"></a>Symptome  
 Zugriffsverletzungen oder Beschädigungen des Heaps der Garbage Collection.  
  
## <a name="cause"></a>Ursache  
 Eine überlappende Struktur wurde freigegeben, bevor der Vorgang abgeschlossen wurde. Die Funktion, die den überlappenden Zeiger verwendet, wird möglicherweise später auf die Struktur schreiben, nachdem dieser freigegeben wurde. Dies kann den Heap beschädigen, da ein anderes Objekt jetzt diesen Bereich einnehmen kann.  
  
 Dieser MDA stellt möglicherweise keine Fehler dar, wenn der überlappende Vorgang nicht erfolgreich gestartet wurde.  
  
## <a name="resolution"></a>Lösung  
 Stellen Sie sicher, dass der E/A-Vorgang die überlappende Struktur verwendet, bevor Sie die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>-Methode aufrufen.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Output  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
