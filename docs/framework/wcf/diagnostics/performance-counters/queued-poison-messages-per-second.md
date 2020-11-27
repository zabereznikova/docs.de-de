---
title: Beschädigte Nachrichten in der Warteschlange pro Sekunde
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 1e515a81580bd9773841bee4230288d8c7d12216
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276229"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="fccc2-102">Beschädigte Nachrichten in der Warteschlange pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="fccc2-102">Queued Poison Messages Per Second</span></span>

<span data-ttu-id="fccc2-103">Indikatorname: Queued Poison Messages Per Second.</span><span class="sxs-lookup"><span data-stu-id="fccc2-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fccc2-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fccc2-104">Description</span></span>  

 <span data-ttu-id="fccc2-105">Die Anzahl der Nachrichten, die pro Sekunde durch den Warteschlangentransport für diesen Dienst als beschädigt gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="fccc2-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="fccc2-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="fccc2-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="fccc2-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="fccc2-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
