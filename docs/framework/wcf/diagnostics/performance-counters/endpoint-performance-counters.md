---
title: Endpunktleistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 9aa741c4482e40a28a2744765114c21973547298
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="endpoint-performance-counters"></a>Endpunktleistungsindikatoren
Endpunktleistungsindikatoren zeichnen Daten auf, die zeigen, wie ein Endpunkt Nachrichten annimmt. Sie sind beim Anzeigen mit dem Systemmonitor unter dem `ServiceModelEndpoint 4.0.0.0`-Leistungsobjekt zu finden. Die Instanzen werden mithilfe des folgenden Musters benannt:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Die Daten ähneln denen, die für einzelne Vorgänge erfasst werden, sie werden jedoch nur über den Endpunkt aggregiert.  
  
> [!CAUTION]
>  Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz. Wenn ein Windows Communication Foundation (WCF)--Instanzname die maximale Länge überschreitet [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ersetzt einen Teil des Instanznamens durch einen Hashwert.  
  
## <a name="see-also"></a>Siehe auch  
 [Leistungsindikatoren](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
