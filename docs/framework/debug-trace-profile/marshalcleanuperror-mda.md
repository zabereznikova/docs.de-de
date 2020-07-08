---
title: marshalCleanupError-MDA
description: Überprüfen Sie den "marshalCleanupError Managed Debug Assistant" (MDA), der aufgerufen wird, weil ein unerwarteter Fehler beim Bereinigen von temporären Strukturen aufgetreten ist.
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
ms.openlocfilehash: 3c7498d6f51484de3a2e84d611a2634f53724ab6
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051609"
---
# <a name="marshalcleanuperror-mda"></a>marshalCleanupError-MDA
Der `marshalCleanupError`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Bereinigen von temporären Strukturen und Arbeitsspeicher, die zum Marshalling von Datentypen über die Grenze zwischen nativem und verwaltetem Code verwendet wurden, auf einen Fehler stößt.  
  
## <a name="symptoms"></a>Symptome  
 Beim Übergang von systemeigenem zu verwaltetem Code tritt Speicherverlust auf, der Laufzeitzustand (wie z. B. die Threadkultur) wird nicht wiederhergestellt oder es treten Fehler beim Bereinigen von <xref:System.Runtime.InteropServices.SafeHandle> auf.  
  
## <a name="cause"></a>Ursache  
 Beim Bereinigen temporärer Strukturen ist ein unerwarteter Fehler aufgetreten.  
  
## <a name="resolution"></a>Lösung  
 Überprüfen Sie alle Destruktoren-, Finalizer- und benutzerdefinierten Marshallerimplementierungen für <xref:System.Runtime.InteropServices.SafeHandle> auf Fehler.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Ausgabe  
 Eine Meldung über den während der Bereinigung fehlgeschlagenen Vorgang.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
