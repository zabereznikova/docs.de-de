---
title: invalidVariant-MDA
description: Überprüfen Sie den invalidVariant-Assistenten für verwaltetes Debuggen, der aufgerufen wird, wenn eine ungültige Variante bei einem Aufruf von System eigenem/nicht verwaltetem zu verwaltetem Code auftritt
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: f0667a54e950ead27000eb6b93ebd547dea1cfb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281299"
---
# <a name="invalidvariant-mda"></a>invalidVariant-MDA

Der Assistent für verwaltetes Debugging (MDA) `invalidVariant` wird aktiviert, wenn während eines Aufrufs aus systemeigenem oder unverwaltetem Code an verwalteten Code eine ungültige `VARIANT`-Struktur erkannt wird.  
  
## <a name="symptoms"></a>Symptome  

 Unerwartetes Verhalten während eines Übergangs zwischen nativem und verwaltetem Code, das das Marshalling eines `VARIANT` an ein Objekt einbezieht.  
  
## <a name="cause"></a>Ursache  

 Systemeigener Code übergibt eine fehlerhafte `VARIANT`-Struktur an verwalteten Code.  Zur Laufzeit wird versucht, diesen `VARIANT` an ein Objekt zu marshallen, und der MDA wird aktiviert, wenn der `VARIANT` ungültig ist. Beispiele für ungültige `VARIANT`S enthalten unter anderem ein `VARIANT` mit dem `VARTYPE` VT_EMPTY &#124; VT_BYREF oder ein `VARIANT` mit dem `VARTYPE` VT_VARIANT.  
  
## <a name="resolution"></a>Lösung  

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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
