---
title: Beschädigte Nachrichten in der Warteschlange pro Sekunde
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d755b9c9e4c8e7ef9e57a0d93c05f87830d63c5c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163994"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="9c0f0-102">Beschädigte Nachrichten in der Warteschlange pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="9c0f0-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="9c0f0-103">Indikatorname: Queued Poison Messages Per Second.</span><span class="sxs-lookup"><span data-stu-id="9c0f0-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9c0f0-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c0f0-104">Description</span></span>  
 <span data-ttu-id="9c0f0-105">Die Anzahl der Nachrichten, die pro Sekunde durch den Warteschlangentransport für diesen Dienst als beschädigt gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="9c0f0-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="9c0f0-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="9c0f0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9c0f0-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="9c0f0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
