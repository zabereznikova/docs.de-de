---
title: Dienst-Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: bf0b12e6d4954c0a1392554d7269a7d539a77dc1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545594"
---
# <a name="service-performance-counters"></a><span data-ttu-id="9a671-102">Dienst-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="9a671-102">Service Performance Counters</span></span>
<span data-ttu-id="9a671-103">Mit Dienst-Leistungsindikatoren wird das Dienstverhalten insgesamt gemessen und die Leistung des gesamten Diensts geprüft.</span><span class="sxs-lookup"><span data-stu-id="9a671-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="9a671-104">Die Dienst-Leistungsindikatoren sind unter dem `ServiceModelService 4.0.0.0`-Leistungsobjekt zu finden, wenn sie im Leistungsmonitor (Perfmon.exe) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9a671-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="9a671-105">Die Instanzen werden nach dem folgenden Schema benannt:</span><span class="sxs-lookup"><span data-stu-id="9a671-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="9a671-106">Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz.</span><span class="sxs-lookup"><span data-stu-id="9a671-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="9a671-107">Wenn Namen einer Leistungsindikatorinstanz Windows Communication Foundation (WCF) die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="9a671-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a671-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a671-108">See also</span></span>
- [<span data-ttu-id="9a671-109">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="9a671-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
