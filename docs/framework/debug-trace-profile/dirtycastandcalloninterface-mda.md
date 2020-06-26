---
title: dirtyCastAndCallOnInterface-MDA
description: Überprüfen Sie den dirtyCastAndCallOnInterface-Assistenten für verwaltetes Debuggen, der aufgerufen wird, wenn frühe gebundene Vtable-Aufrufe an nur spät gebundene Klassen Schnittstellen durchgeführt werden.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
ms.openlocfilehash: 2ed5589909915a261a22c48490e469ae52659c8c
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416069"
---
# <a name="dirtycastandcalloninterface-mda"></a>dirtyCastAndCallOnInterface-MDA
Der `dirtyCastAndCallOnInterface`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn für eine Klassenschnittstelle, die für ausschließlich späte Bindung gekennzeichnet ist, ein früh gebundener Aufruf über eine Vtable erfolgt.  
  
## <a name="symptoms"></a>Symptome  
 Eine Anwendung löst eine Zugriffsverletzung aus oder zeigt unerwartetes Verhalten, wenn ein früh gebundener Aufruf über COM in die CLR erfolgt  
  
## <a name="cause"></a>Ursache  
 Code versucht einen früh gebundenen Aufruf durch eine Vtable über eine Klassenschnittstelle, die nur spät gebunden wird. Beachten Sie, dass Klassenschnittstellen standardmäßig als ausschließlich spät gebunden gekennzeichnet werden. Sie können aber auch mit dem <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut mit einem <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>-Wert (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`) als spät gebunden gekennzeichnet werden.  
  
## <a name="resolution"></a>Lösung  
 Die empfohlene Lösung besteht darin, eine explizite Schnittstelle für die Verwendung durch COM zu definieren und Aufrufe von COM-Clients über diese Schnittstelle erfolgen zu lassen, nicht über die automatisch generierte Klassenschnittstelle. Alternativ kann der Aufruf aus COM über `IDispatch` in einen spät gebundenen Aufruf transformiert werden.  
  
 Schließlich kann die Klasse auch als <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) gekennzeichnet werden, um früh gebundene Aufrufe aus COM zuzulassen. Wegen der unter <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> beschriebenen Versionseinschränkungen wird jedoch dringend davon abgeraten, <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> zu verwenden.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR. Er meldet nur Daten über früh gebundene Aufrufe für spät gebundene Schnittstellen.  
  
## <a name="output"></a>Output  
 Der Name der Methode oder des Felds, auf die oder das über frühe Bindung zugegriffen wird.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
