---
title: invalidMemberDeclaration-MDA
description: Überprüfen Sie den Assistenten für das Debuggen von ungültetem Debugging, der aufgerufen wird, wenn ein Fehler-HRESULT an com zurückgegeben wird, ohne die verwaltete Methode aufzurufen.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 5dbfba2baec3263d91746c06379438e97a81f005
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051713"
---
# <a name="invalidmemberdeclaration-mda"></a>invalidMemberDeclaration-MDA
Der `invalidMemberDeclaration`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, um einen Fehler zu melden, der aufgetreten ist, als ermittelt werden sollte, wie das Marshalling für die Parameter eines Members zu erfolgen hat, das aus COM aufgerufen werden soll.  
  
## <a name="symptoms"></a>Symptome  
 Es wird ein Fehler-HRESULT an COM zurückgegeben, ohne dass die verwaltete Methode aufgerufen wurde.  
  
## <a name="cause"></a>Ursache  
 Dies wird höchstwahrscheinlich durch ein inkompatibles <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut für einen der Parameter verursacht.  
  
## <a name="resolution"></a>Lösung  
 Geben Sie gültige <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribute für die Parameter an.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Ausgabe  
 Eine Informationsmeldung, die den Membernamen, den Typnamen und die Fehlermeldung enthält.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
