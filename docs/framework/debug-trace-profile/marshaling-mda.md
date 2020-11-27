---
title: marshaling-MDA
description: Überprüfen Sie den Marshalling-Assistenten für verwaltetes Debuggen (MDA), der aufgerufen wird, wenn die CLR Marshallinginformationen für einen Methoden Parameter oder ein Strukturfeld festlegt.
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: afe54a2104e05f8fad57c7cbba4988b013aff761
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271173"
---
# <a name="marshaling-mda"></a>marshaling-MDA

Der `marshaling`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR Marshallinginformationen für einen Methodenparameter oder das Feld einer Struktur einrichtet. Dieser MDA funktioniert nicht mit JIT-kompilierten Assemblys.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  

 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Ausgabe  

 Der MDA zeigt den Typ des Parameters bzw. Felds in den verwalteten und nicht verwalteten Kontexten sowie die Struktur bzw. Methode an, die diesen Typ enthält.  Das Folgende ist ein Beispiel für die Ausgabe für ein Feld:  
  
```output
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a>Konfiguration  

 Durch Konfigurieren des MDA können Sie die gemeldeten Marshallinginformationen anhand der betroffenen Feld- oder Methodennamen filtern.  Im folgenden Beispiel wird gezeigt, wie die Elemente `methodFilter`, `fieldFilter` und `match` verwendet werden, um Filter anzugeben.  Wenn das- `name` Attribut auf ein Sternchen () festgelegt \* wird, entspricht es allen.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
