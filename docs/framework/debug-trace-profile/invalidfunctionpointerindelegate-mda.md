---
title: InvalidFunctionPointerInDelegate-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5e9fd1faacc7be5b95e2bab0d8fdbee105e35498
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="invalidfunctionpointerindelegate-mda"></a>InvalidFunctionPointerInDelegate-MDA
Der `invalidFunctionPointerInDelegate` Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn ein ungültiger Funktionszeiger übergeben wird, um einen Delegaten über einen systemeigenen Funktionszeiger zu konstruieren.  
  
## <a name="symptoms"></a>Symptome  
 Zugriffsverletzungen oder unerwartete Speicherschäden beim Verwenden eines Delegaten über einen Funktionszeiger.  
  
## <a name="cause"></a>Ursache  
 Es wurde ein ungültiger Funktionszeiger angegeben.  
  
## <a name="resolution"></a>Lösung  
 Geben Sie einen gültigen Funktionszeiger an.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Ausgabe  
 Der ungültige Funktionszeiger.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
