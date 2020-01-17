---
title: 'Dienst: Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: be5d77169a71d6f44205a1150da5239eceff7d9c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163903"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="4241d-102">Dienst: Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="4241d-102">Service: Calls Per Second</span></span>
<span data-ttu-id="4241d-103">Indikatorname: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="4241d-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4241d-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4241d-104">Description</span></span>  
 <span data-ttu-id="4241d-105">Die Anzahl der Aufrufe an diesen Dienst pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4241d-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="4241d-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="4241d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="4241d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Dabei gibt der Zähler (N) die Anzahl der im letzten Messintervall durchgeführten Operationen und der Nenner (D) die Anzahl der Ticks im letzten Messintervall an. F ist die Tickfrequenz.</span><span class="sxs-lookup"><span data-stu-id="4241d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
