---
title: COM-Wrapper
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d86743f59c12cf59376ad542c2cd58f6e8c4ad65
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187243"
---
# <a name="com-wrappers"></a>COM-Wrapper
COM unterscheidet sich vom .NET Framework-Objektmodell in mehreren wichtigen Punkten:  
  
-   Clients von COM-Objekten müssen die Lebensdauer dieser Objekte verwalten. Die Common Language Runtime verwaltet die Lebensdauer der Objekte in ihrer Umgebung.  
  
-   Clients von COM-Objekten ermitteln, ob ein Dienst verfügbar ist, indem sie eine Schnittstelle anfordern, die diesen Dienst bereitstellt und einen Schnittstellenzeiger erhalten oder nicht. Clients von .NET-Objekten erhalten durch Reflektion eine Beschreibung der Objektfunktionen.  
  
-   NET-Objekte befinden sich im Arbeitsspeicher, der von der .NET Framework-Ausführungsumgebung verwaltet wird. Die Ausführungsumgebung kann Objekte im Arbeitsspeicher aus Leistungsgründen verschieben und alle Verweise auf die verschobenen Objekte aktualisieren. Nicht verwaltete Clients, die einen Zeiger auf ein Objekt erhalten haben, verlassen sich darauf, dass das Objekt am selben Speicherort verbleibt. Diese Clients haben keinen Mechanismen für den Umgang mit einem Objekt, dessen Position nicht fest ist.  
  
 Um diese Unterschiede zu überwinden, stellt die Common Language Runtime Wrapperklassen bereit, um sowohl verwalteten als auch nicht verwalteten Clients den Eindruck zu geben, dass sie Objekte in ihrer jeweiligen Umgebung aufrufen. Wenn Ihr verwalteter Client eine Methode für ein COM-Objekt aufruft, erstellt die Laufzeit einen [Runtime Callable Wrapper](runtime-callable-wrapper.md) (RCW). RCWs abstrahieren unter anderem die Unterschiede zwischen verwalteten und nicht verwalteten Verweismechanismen. Die Common Language Runtime erstellt außerdem einen [COM Callable Wrapper](com-callable-wrapper.md) (CCW) zur Umkehrung dieses Prozesses. Der COM-Client kann eine Methode für ein .NET-Objekt nahtlos aufrufen. Wie in der folgenden Abbildung gezeigt, bestimmt die Perspektive des aufrufenden Codes die Wrapperklasse, die die Common Language Runtime erstellt.  
  
 ![Übersicht über COM-Wrapper](media/bidirectional.gif "bidirektional")  
Übersicht über COM-Wrapper  
  
 In den meisten Fällen stellen die von der Common Language Runtime standardmäßig generierten RCW oder CCW ausreichend Marshalling für Aufrufe bereit, die die Anwendungsgrenze zwischen COM und dem .NET Framework überschreiten. Mithilfe von benutzerdefinierten Attributen können Sie optional anpassen, wie die Common Language Runtime verwalteten und nicht verwalteten Code darstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte COM-Interoperabilität](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))  
 [Runtime Callable Wrapper (RCW)](runtime-callable-wrapper.md)  
 [COM Callable Wrapper](com-callable-wrapper.md)  
 [Anpassen von Standardwrappern](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100))  
 [Vorgehensweise: Anpassen von durch die Laufzeit aufrufbaren Wrappern](https://msdn.microsoft.com/library/4a4bb3da-4d60-4517-99f2-78d46a681732(v=vs.100))
