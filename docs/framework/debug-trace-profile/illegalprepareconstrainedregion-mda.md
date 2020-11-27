---
title: illegalPrepareConstrainedRegion-MDA
description: Überprüfen Sie den Assistenten für verwaltetes Debuggen von IllegalPrepareConstrainedRegion, der aufgerufen wird, wenn auf einen PrepareConstrainedRegions-Aufruf nicht eine try-Anweisung folgt.
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: 7cbf04e8605ccf18e89882dd09b96cc7c59330c9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272786"
---
# <a name="illegalprepareconstrainedregion-mda"></a>illegalPrepareConstrainedRegion-MDA

Der `illegalPrepareConstrainedRegion`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType>-Methodenaufruf der `try`-Anweisung des Ausnahmehandlers nicht direkt vorausgeht. Diese Einschränkung befindet sich auf MSIL-Ebene, daher ist es zulässig, über nicht codeerzeugende Datenquellen zwischen dem Aufruf und `try`, beispielsweise Kommentare, zu verfügen.  
  
## <a name="symptoms"></a>Symptome  

 Ein eingeschränkter Ausführungsbereich (CER), der nie als solcher behandelt wird, sondern als ein einfacher Block zur Ausnahmebehandlung (`finally` oder `catch`). Daher wird der Bereich nicht im Fall einer Out-of-Memory-Bedingung oder eines Threadabbruchs ausgeführt.  
  
## <a name="cause"></a>Ursache  

 Das Muster zur Vorbereitung für einen CER wird nicht richtig befolgt.  Dies ist ein Fehlerereignis. Der <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> Methoden Befehl, der zum Markieren von Ausnahme Handlern verwendet wird, um einen CER in ihren Blöcken einzuführen, `catch` / `finally` / `fault` / `filter` muss unmittelbar vor der-Anweisung verwendet werden `try` .  
  
## <a name="resolution"></a>Lösung  

 Stellen Sie sicher, dass der Aufruf von <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> unmittelbar vor der `try`-Anweisung geschieht.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  

 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Ausgabe  

 Der MDA zeigt den Namen der Methode an, die die <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>-Methode, den MSIL-Offset und eine Meldung aufruft, die angibt, dass der Aufruf dem Beginn des Try-Blocks nicht direkt vorausgeht.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Beispiel  

 Das folgende Codebeispiel veranschaulicht das Muster, das bewirkt, dass dieser MDA aktiviert wird.  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
