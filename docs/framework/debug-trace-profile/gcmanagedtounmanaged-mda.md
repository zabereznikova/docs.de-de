---
title: gcManagedToUnmanaged-MDA
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
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d461ff702f756df6d599d7082edc6c5c4719c537
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="gcmanagedtounmanaged-mda"></a>gcManagedToUnmanaged-MDA
Der `gcManagedToUnmanaged`-Assistent für verwaltetes Debuggen (MDA) bewirkt eine Garbage Collection bei jedem Übergang eines Threads von verwaltetem zu nicht verwaltetem Code.  
  
## <a name="symptoms"></a>Symptome  
 Eine nicht verwaltete Benutzerkomponente löst bei dem Versuch, ein für COM verfügbar gemachtes verwaltetes Objekt zu verwenden, eine Zugriffsverletzung aus. Das COM-Objekt wurde scheinbar freigegeben. Die Zugriffsverletzung ist nicht deterministisch.  
  
## <a name="cause"></a>Ursache  
 Wenn eine nicht verwaltete Komponente keine korrekte Verweiszählung für ein verwaltetes COM-Objekt durchführt, wird das für COM verfügbar gemachte verwaltete Objekt unter Umständen schon einer Garbage Collection unterzogen, während die nicht verwaltete Komponente noch über einen Verweis auf dieses Objekt verfügt. Bei der Garbage Collection wird von der CLR <xref:System.Runtime.InteropServices.Marshal.Release%2A> aufgerufen. Wenn die Benutzerkomponente das Objekt also vor dem Ausführen der Garbage Collection verwendet, wurde es noch nicht der Garbage Collection unterzogen. Dies ist die Ursache der Nichtdeterminiertheit.  
  
## <a name="resolution"></a>Auflösung  
 Durch das Aktivieren dieses Assistenten verringert sich die Zeit zwischen der Freigabe des Objekts zur Garbage Collection und dem Aufruf von <xref:System.Runtime.InteropServices.Marshal.Release%2A>. So kann besser ermittelt werden, welche nicht verwaltete Komponente zuerst versucht, auf das der Garbage Collection unterzogene Objekt zuzugreifen.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Löst immer eine Garbage Collection aus, wenn der Übergang eines Threads von verwaltetem zu nicht verwaltetem Code erfolgt.  
  
## <a name="output"></a>Ausgabe  
 Dieser MDA erzeugt keine Ausgabe.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)  
 [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
