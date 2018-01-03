---
title: failedQI-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc717f1500d202ae2590adb61b0376e93eba0944
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="failedqi-mda"></a>failedQI-MDA
Der `failedQI`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR stellvertretend für einen RCW (Runtime Callable Wrapper) `QueryInterface` für einen COM-Schnittstellenzeiger aufruft und der Aufruf von `QueryInterface` fehlschlägt.  
  
## <a name="symptoms"></a>Symptome  
 Eine Umwandlung für einen RCW schlägt fehl, oder ein Aufruf von COM von einem RCW aus schlägt unerwartet fehl.  
  
## <a name="cause"></a>Ursache  
  
-   Der Aufruf erfolgt im falschen Kontext.  
  
-   Der registrierte Proxy kann den Aufruf von `QueryInterface` nicht ausführen, weil der Aufruf im falschen Kontext erfolgte.  
  
-   Ein OLE zugehöriger Proxy hat einen falschen Wert für HRESULT zurückgegeben.  
  
## <a name="resolution"></a>Auflösung  
 Informationen hierzu finden Sie in der MSDN-Dokumentation zu COM-Regeln.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Wenn ein Aufruf von `QueryInterface` fehlschlägt, erfolgt ein Kontextwechsel, und der Aufruf von `QueryInterface` wird erneut ausgeführt, um zu ermitteln, ob ein falscher Kontext für das Fehlschlagen verantwortlich war.  
  
## <a name="output"></a>Ausgabe  
 Der verwaltete Name der Schnittstelle, die GUID der Schnittstelle und das HRESULT des Fehlers.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
