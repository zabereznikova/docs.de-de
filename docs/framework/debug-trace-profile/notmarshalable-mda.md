---
title: NotMarshalable-MDA
description: Überprüfen Sie den notmarshalling-Assistenten für verwaltetes Debuggen, der aktiviert werden kann, wenn Aufrufe nicht gewartet werden oder im falschen Kontext für COM-Schnittstellen Zeiger auftreten.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
ms.openlocfilehash: b464d914a8d83504daaf4cb276914da7798262dc
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803793"
---
# <a name="notmarshalable-mda"></a>NotMarshalable-MDA
Der `notMarshalable`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Versuch, eine Schnittstelle über Kontexte hinweg zu marshallen, einen COM-Schnittstellenzeiger ohne gültigen registrierten Proxy/Stub oder eine nicht ordnungsgemäß implementierte `IMarshal`-Schnittstelle erkennt.  
  
## <a name="symptoms"></a>Symptome  
 Aufrufe werden nicht abgewickelt, oder Aufrufe treten im falschen Kontext für COM-Schnittstellenzeiger auf.  
  
## <a name="cause"></a>Ursache  
 Beim Versuch, die Schnittstelle über Kontexte hinweg zu marshallen, wurde kein gültiger registrierter Proxy/Stub oder eine fehlerhafte `IMarshal`-Schnittstelle erkannt.  
  
## <a name="resolution"></a>Lösung  
 Stellen Sie sicher, dass ein Proxy/Stub registriert ist und die `IMarshal`-Implementierung gültig ist.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die Laufzeit.  
  
## <a name="output"></a>Output  
 Eine Meldung mit einer Beschreibung des Problems.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
