---
title: invalidVariant-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d29d3f3638b3dae4381524fcaf55e1afeddc9f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730801"
---
# <a name="invalidvariant-mda"></a>invalidVariant-MDA
Der Assistent für verwaltetes Debugging (MDA) `invalidVariant` wird aktiviert, wenn während eines Aufrufs aus systemeigenem oder unverwaltetem Code an verwalteten Code eine ungültige `VARIANT`-Struktur erkannt wird.  
  
## <a name="symptoms"></a>Symptome  
 Unerwartetes Verhalten während eines Übergangs zwischen systemeigenem und verwaltetem Code, das das Marshalling eines `VARIANT` an ein Objekt einbezieht.  
  
## <a name="cause"></a>Ursache  
 Systemeigener Code übergibt eine fehlerhafte `VARIANT`-Struktur an verwalteten Code.  Zur Laufzeit wird versucht, diesen `VARIANT` an ein Objekt zu marshallen, und der MDA wird aktiviert, wenn der `VARIANT` ungültig ist. Beispiele für ungültige `VARIANT`S enthalten unter anderem ein `VARIANT` mit dem `VARTYPE` VT_EMPTY &#124; VT_BYREF oder ein `VARIANT` mit dem `VARTYPE` VT_VARIANT.  
  
## <a name="resolution"></a>Auflösung  
 Der systemeigene oder unverwaltete Code, der den `VARIANT` übergibt, muss sicherstellen, dass der `VARIANT` korrekt geformt und initialisiert ist.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die Laufzeit.  
  
## <a name="output"></a>Ausgabe  
 Eine MDA-Meldung, die angibt, dass zur Laufzeit ein ungültiger `VARIANT` erkannt wurde, der von einem unverwalteten Modul an verwalteten Code übergeben wurde.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
