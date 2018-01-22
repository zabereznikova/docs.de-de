---
title: COM-Wrapper
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b899ed162fa626f8c378923907f275cebf9a7db4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="com-wrappers"></a>COM-Wrapper
COM unterscheidet sich vom .NET Framework-Objektmodell in mehreren wichtigen Punkten:  
  
-   Clients von COM-Objekten müssen die Lebensdauer dieser Objekte verwalten. Die Common Language Runtime verwaltet die Lebensdauer der Objekte in ihrer Umgebung.  
  
-   Clients von COM-Objekten ermitteln, ob ein Dienst verfügbar ist, indem sie eine Schnittstelle anfordern, die diesen Dienst bereitstellt und einen Schnittstellenzeiger erhalten oder nicht. Clients von .NET-Objekten erhalten durch Reflektion eine Beschreibung der Objektfunktionen.  
  
-   NET-Objekte befinden sich im Arbeitsspeicher, der von der .NET Framework-Ausführungsumgebung verwaltet wird. Die Ausführungsumgebung kann Objekte im Arbeitsspeicher aus Leistungsgründen verschieben und alle Verweise auf die verschobenen Objekte aktualisieren. Nicht verwaltete Clients, die einen Zeiger auf ein Objekt erhalten haben, verlassen sich darauf, dass das Objekt am selben Speicherort verbleibt. Diese Clients haben keinen Mechanismen für den Umgang mit einem Objekt, dessen Position nicht fest ist.  
  
 Um diese Unterschiede zu überwinden, stellt die Common Language Runtime Wrapperklassen bereit, um sowohl verwalteten als auch nicht verwalteten Clients den Eindruck zu geben, dass sie Objekte in ihrer jeweiligen Umgebung aufrufen. Wenn Ihr verwalteter Client eine Methode für ein COM-Objekt aufruft, erstellt die Laufzeit einen [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW). RCWs abstrahieren unter anderem die Unterschiede zwischen verwalteten und nicht verwalteten Verweismechanismen. Die Common Language Runtime erstellt außerdem einen [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) (CCW) zur Umkehrung dieses Prozesses. Der COM-Client kann eine Methode für ein .NET-Objekt nahtlos aufrufen. Wie in der folgenden Abbildung gezeigt, bestimmt die Perspektive des aufrufenden Codes die Wrapperklasse, die die Common Language Runtime erstellt.  
  
 ![Übersicht über COM-Wrapper](../../../docs/framework/interop/media/bidirectional.gif "bidirektional")  
Übersicht über COM-Wrapper  
  
 In den meisten Fällen stellen die von der Common Language Runtime standardmäßig generierten RCW oder CCW ausreichend Marshalling für Aufrufe bereit, die die Anwendungsgrenze zwischen COM und dem .NET Framework überschreiten. Mithilfe von benutzerdefinierten Attributen können Sie optional anpassen, wie die Common Language Runtime verwalteten und nicht verwalteten Code darstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte COM-Interoperabilität](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [Runtime Callable Wrapper (RCW)](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)  
 [Anpassen von Standardwrappern](http://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d)  
 [Vorgehensweise: Anpassen von durch die Laufzeit aufrufbaren Wrappern](http://msdn.microsoft.com/library/4a4bb3da-4d60-4517-99f2-78d46a681732)
