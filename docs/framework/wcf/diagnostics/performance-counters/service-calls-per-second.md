---
title: 'Dienst: Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5066108d8183502eeaec7c25186c00d9978261b7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546932"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="8c8f9-102">Dienst: Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="8c8f9-102">Service: Calls Per Second</span></span>
<span data-ttu-id="8c8f9-103">Indikatorname: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="8c8f9-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8c8f9-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c8f9-104">Description</span></span>  
 <span data-ttu-id="8c8f9-105">Die Anzahl der Aufrufe an diesen Dienst pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="8c8f9-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="8c8f9-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="8c8f9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8c8f9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Dabei gibt der Zähler (N) die Anzahl der im letzten Messintervall durchgeführten Operationen und der Nenner (D) die Anzahl der Ticks im letzten Messintervall an. F ist die Tickfrequenz.</span><span class="sxs-lookup"><span data-stu-id="8c8f9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
