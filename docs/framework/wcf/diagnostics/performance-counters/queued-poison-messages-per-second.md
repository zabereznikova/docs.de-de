---
title: Beschädigte Nachrichten in der Warteschlange pro Sekunde
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d4c921b105dfd1c1a364d2c86f54ab920078dd4a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916148"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="04b53-102">Beschädigte Nachrichten in der Warteschlange pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="04b53-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="04b53-103">Indikatorname: In der Warteschlange für nicht verarbeitbare Nachrichten pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="04b53-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="04b53-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04b53-104">Description</span></span>  
 <span data-ttu-id="04b53-105">Die Anzahl der Nachrichten, die pro Sekunde durch den Warteschlangentransport für diesen Dienst als beschädigt gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="04b53-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="04b53-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="04b53-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="04b53-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="04b53-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
