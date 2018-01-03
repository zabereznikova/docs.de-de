---
title: gcUnmanagedToManaged-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bc02f12a49ef65614114a056f9263f9ef7f5322
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="gcunmanagedtomanaged-mda"></a>gcUnmanagedToManaged-MDA
Der `gcUnmanagedToManaged`-Assistent für verwaltetes Debuggen (MDA) bewirkt eine Garbage Collection bei jedem Übergang eines Threads von nicht verwaltetem zu verwaltetem Code.  
  
## <a name="symptoms"></a>Symptome  
 Eine Anwendung, die mithilfe von COM und Plattformaufrufen nicht verwaltete Benutzerkomponenten ausführt, verursacht eine nicht deterministische Zugriffsverletzung in der CLR.  
  
## <a name="cause"></a>Ursache  
 Wenn eine Anwendung nicht verwaltete Benutzerkomponenten ausführt, haben diese Komponenten möglicherweise den Heap der Garbage Collection beschädigt. Dies verursacht eine Zugriffsverletzung in der CLR, wenn der Garbage Collector versucht, das Objektdiagramm zu durchlaufen.  
  
## <a name="resolution"></a>Auflösung  
 Das Aktivieren dieses Assistenten verringert die Zeit zwischen dem Zeitpunkt der Beschädigung des Heaps der Garbage Collection durch die nicht verwaltete Komponente und dem Zeitpunkt, wenn die Zugriffsverletzung durch Erzwingen einer Garbage Collection vor jedem verwalteten Übergang auftritt.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Löst immer eine Garbage Collection aus, wenn der Übergang eines Threads von nicht verwaltetem zu verwaltetem Code erfolgt.  
  
## <a name="output"></a>Ausgabe  
 Dieser MDA erzeugt keine Ausgabe.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
 [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
