---
title: Fehlerhafte Aufrufe pro Sekunde
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: bad37e0124698209955603c1b7d8a1aec4b87418
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521048"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="ce5d3-102">Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="ce5d3-102">Calls Failed Per Second</span></span>
<span data-ttu-id="ce5d3-103">Indikatorname: Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="ce5d3-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="ce5d3-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce5d3-104">Description</span></span>  
 <span data-ttu-id="ce5d3-105">Anzahl von Aufrufen mit nicht behandelten Ausnahmen in diesem Vorgang innerhalb einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="ce5d3-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="ce5d3-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="ce5d3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ce5d3-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="ce5d3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="ce5d3-108">Der Wert dieses Zählers erhöht sich, sobald in diesem Vorgang eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="ce5d3-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce5d3-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce5d3-109">See also</span></span>
- [<span data-ttu-id="ce5d3-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="ce5d3-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
