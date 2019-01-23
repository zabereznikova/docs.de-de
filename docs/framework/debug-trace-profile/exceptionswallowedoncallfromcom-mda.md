---
title: exceptionSwallowedOnCallFromCom-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebcd2d2f2387f478c36e84dad82d90d4d70d68e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554672"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a>exceptionSwallowedOnCallFromCom-MDA
Der `exceptionSwallowedOnCallFromCOM`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Ausnahme durch Common-Language-Runtime-Code (CLR-Code) ausgelöst wird, der aus COM über eine Methode aufgerufen wurde, die nicht über einen unverwalteten HRESULT-Rückgabetyp verfügt.  
  
## <a name="symptoms"></a>Symptome  
 Der Aufruf einer verwalteten Komponente aus COM gibt den Wert FALSE oder 0 zurück. Wenn die Methode stattdessen einen leeren Rückgabewert hat, gibt es möglicherweise keinen Hinweis darauf, dass während der Ausführung der Methode eine Ausnahme ausgelöst wurde. In diesem Fall wird die Ausnahme automatisch abgefangen und die Ausführung wird zum COM-Aufrufer zurückgegeben.  
  
## <a name="cause"></a>Ursache  
 Es wurde eine Ausnahme ausgelöst, aber es gibt keine gültige Möglichkeit, diese zu melden.  
  
## <a name="resolution"></a>Lösung  
 Dient nur Informationszwecken; weist nicht notwendigerweise auf einen Fehler hin.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR. Es werden nur Daten über automatisch abgefangene Ausnahmen gemeldet.  
  
## <a name="output"></a>Ausgabe  
 Informationsmeldung, die den Methodennamen, Typnamen und die Ausnahmemeldung enthält.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
