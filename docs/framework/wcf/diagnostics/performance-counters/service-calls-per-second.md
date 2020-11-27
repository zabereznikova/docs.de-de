---
title: 'Dienst: Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 7e702d402909c4a85a2cb42c837e0813c4d9f841
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252880"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="9aea7-102">Dienst: Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="9aea7-102">Service: Calls Per Second</span></span>

<span data-ttu-id="9aea7-103">Indikatorname: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="9aea7-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9aea7-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9aea7-104">Description</span></span>  

 <span data-ttu-id="9aea7-105">Die Anzahl der Aufrufe an diesen Dienst pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="9aea7-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="9aea7-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="9aea7-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9aea7-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Dabei gibt der Zähler (N) die Anzahl der im letzten Messintervall durchgeführten Operationen und der Nenner (D) die Anzahl der Ticks im letzten Messintervall an. F ist die Tickfrequenz.</span><span class="sxs-lookup"><span data-stu-id="9aea7-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
