---
title: Abgelehnte Nachrichten in der Warteschlange pro Sekunde
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 805b4f5d1e7882f38cfcc76ad63451d735389d5f
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163968"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="01c6c-102">Abgelehnte Nachrichten in der Warteschlange pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="01c6c-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="01c6c-103">Indikatorname: Queued Messages Rejected Per Second.</span><span class="sxs-lookup"><span data-stu-id="01c6c-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="01c6c-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01c6c-104">Description</span></span>  
 <span data-ttu-id="01c6c-105">Die Anzahl der Meldungen, die vom Warteschlangentransport für diesen Dienst pro Sekunde abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="01c6c-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="01c6c-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="01c6c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="01c6c-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="01c6c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
