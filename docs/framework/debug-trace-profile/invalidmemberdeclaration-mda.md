---
title: invalidMemberDeclaration-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e5b4cb4a04a79a748f4ea2292bac67a88a6e9f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754361"
---
# <a name="invalidmemberdeclaration-mda"></a>invalidMemberDeclaration-MDA
Der `invalidMemberDeclaration`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, um einen Fehler zu melden, der aufgetreten ist, als ermittelt werden sollte, wie das Marshalling für die Parameter eines Members zu erfolgen hat, das aus COM aufgerufen werden soll.  
  
## <a name="symptoms"></a>Symptome  
 Es wird ein Fehler-HRESULT an COM zurückgegeben, ohne dass die verwaltete Methode aufgerufen wurde.  
  
## <a name="cause"></a>Ursache  
 Dies wird höchstwahrscheinlich durch ein inkompatibles <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut für einen der Parameter verursacht.  
  
## <a name="resolution"></a>Auflösung  
 Geben Sie gültige <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribute für die Parameter an.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Output  
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
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
