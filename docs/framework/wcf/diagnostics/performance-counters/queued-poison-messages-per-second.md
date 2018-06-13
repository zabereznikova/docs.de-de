---
title: Beschädigte Nachrichten in der Warteschlange pro Sekunde
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 6407cce120f5d534f88a12591ea2ad09bb5130d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473258"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="b5e63-102">Beschädigte Nachrichten in der Warteschlange pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="b5e63-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="b5e63-103">Indikatorname: Queued Poison Messages Per Second.</span><span class="sxs-lookup"><span data-stu-id="b5e63-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b5e63-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5e63-104">Description</span></span>  
 <span data-ttu-id="b5e63-105">Die Anzahl der Nachrichten, die pro Sekunde durch den Warteschlangentransport für diesen Dienst als beschädigt gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="b5e63-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="b5e63-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="b5e63-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b5e63-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="b5e63-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
