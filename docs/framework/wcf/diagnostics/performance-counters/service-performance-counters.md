---
title: Dienst-Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: f3e3a798bf04f24aaea03b5d70762d52b67a82f0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252828"
---
# <a name="service-performance-counters"></a>Dienst-Leistungsindikatoren

Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft. Die Dienst-Leistungsindikatoren sind unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden, wenn sie im Leistungsmonitor (Perfmon.exe) angezeigt werden. Die Instanzen werden nach dem folgenden Schema benannt:  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz. Wenn der Name einer Windows Communication Foundation (WCF)-Leistungs Zählers die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Leistungsindikatoren](index.md)
