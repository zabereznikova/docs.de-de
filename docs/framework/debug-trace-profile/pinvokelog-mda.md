---
title: pInvokeLog-MDA
description: Verstehen Sie den PInvokeLog Managed Debug Assistant (MDA), der für jede eindeutige Platt Form Aufruf-Signatur aktiviert wird, die während der Ausführung in .NET verwendet wird.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: b8cb4805663a2b28a133f98503730199af695c4f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271459"
---
# <a name="pinvokelog-mda"></a>pInvokeLog-MDA

Der `pInvokeLog`-MDA (Assistent für verwaltetes Debuggen) wird für jede eindeutige Plattformaufrufsignatur aktiviert, die während der Ausführung verwendet wird.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  

 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Ausgabe  

 Die Meldung, die die Plattformaufrufsignatur während der Ausführung angibt.  
  
## <a name="configuration"></a>Konfiguration  

 Jedes Übereinstimmungselement filtert die DLL-Dateien, für die Plattformaufrufe erfolgen.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Verwenden nicht verwalteter DLL-Funktionen](../interop/consuming-unmanaged-dll-functions.md)
