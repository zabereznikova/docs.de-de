---
title: Dienst-Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 929ddcb2f271b7488270ea39e7a3a0037158c855
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320025"
---
# <a name="service-performance-counters"></a>Dienst-Leistungsindikatoren
Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft. Die Dienst-Leistungsindikatoren sind unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden, wenn sie im Leistungsmonitor (Perfmon.exe) angezeigt werden. Die Instanzen werden nach dem folgenden Schema benannt:  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz. Wenn der Name einer Windows Communication Foundation (WCF)-Leistungs Zählers die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.  
  
## <a name="see-also"></a>Siehe auch

- [Leistungsindikatoren](index.md)
