---
title: raceOnRCWCleanup-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07b6c674e2608ac46bf9870ae26afc2fc1ec99ba
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052346"
---
# <a name="raceonrcwcleanup-mda"></a>raceOnRCWCleanup-MDA
Der `raceOnRCWCleanup`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR (Common Language Runtime) ermittelt, dass ein [RWC (Runtime Callable Wrapper)](../../standard/native-interop/runtime-callable-wrapper.md) verwendet wird, wenn ein Freigabeaufruf mithilfe eines Befehls wie etwa der <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>-Methode erfolgt.  
  
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

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
