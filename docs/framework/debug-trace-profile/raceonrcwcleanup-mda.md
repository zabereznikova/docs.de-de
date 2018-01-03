---
title: raceOnRCWCleanup-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33d1c7d91c33c194353af43deed9329b9b4ec841
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="raceonrcwcleanup-mda"></a>raceOnRCWCleanup-MDA
Der `raceOnRCWCleanup`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR (Common Language Runtime) ermittelt, dass ein [RWC (Runtime Callable Wrapper)](../../../docs/framework/interop/runtime-callable-wrapper.md) verwendet wird, wenn ein Freigabeaufruf mithilfe eines Befehls wie etwa der <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>-Methode erfolgt.  
  
## <a name="symptoms"></a>Symptome  
 Zugriffsverletzungen oder Speicherschäden während oder nach dem Freigeben eines RCW mithilfe von <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> oder einer ähnlichen Methode.  
  
## <a name="cause"></a>Ursache  
 Der RCW wird in einem anderen Thread oder für den freigebenden Threadstapel verwendet.  Ein RCW, der verwendet wird, kann nicht freigegeben werden.  
  
## <a name="resolution"></a>Auflösung  
 Geben Sie einen RCW, der im aktuellen Thread oder in anderen Threads verwendet wird, nicht frei.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Ausgabe  
 Eine Meldung mit einer Beschreibung des Fehlers.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
