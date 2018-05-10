---
title: Dienst-Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: bdc68fd2b629c538c097dab4e1cf3f89b7f3a091
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="service-performance-counters"></a>Dienst-Leistungsindikatoren
Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft. Die Dienst-Leistungsindikatoren sind unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden, wenn sie im Leistungsmonitor (Perfmon.exe) angezeigt werden. Die Instanzen werden nach dem folgenden Schema benannt:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz. Ein Windows Communication Foundation (WCF)--Instanzname die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.  
  
## <a name="see-also"></a>Siehe auch  
 [Leistungsindikatoren](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
