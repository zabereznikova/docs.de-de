---
title: Endpunktleistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 1b0f7462fea8843bcb0a0938a8034f405f30a6fb
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320513"
---
# <a name="endpoint-performance-counters"></a>Endpunktleistungsindikatoren
Endpunktleistungsindikatoren zeichnen Daten auf, die zeigen, wie ein Endpunkt Nachrichten annimmt. Sie sind beim Anzeigen mit dem Systemmonitor unter dem `ServiceModelEndpoint 4.0.0.0`-Leistungsobjekt zu finden. Die Instanzen werden mithilfe des folgenden Musters benannt:  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 Die Daten ähneln denen, die für einzelne Vorgänge erfasst werden, sie werden jedoch nur über den Endpunkt aggregiert.  
  
> [!CAUTION]
> Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz. Wenn der Name einer Windows Communication Foundation (WCF)-Leistungs Zählers die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.  
  
## <a name="see-also"></a>Siehe auch

- [Leistungsindikatoren](index.md)
