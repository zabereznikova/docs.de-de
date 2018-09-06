---
title: 'Endpunkt: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: fa4fc1d8a875557f1da9e54e7a05eb012e7c221c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856347"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="d7da4-102">Endpunkt: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="d7da4-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="d7da4-103">Indikatorname: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="d7da4-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d7da4-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7da4-104">Description</span></span>  
 <span data-ttu-id="d7da4-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Endpunkt in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="d7da4-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="d7da4-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="d7da4-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d7da4-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="d7da4-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="d7da4-108">Der Wert dieses Indikators erhöht sich, sobald an diesem Endpunkt eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="d7da4-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7da4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7da4-109">See Also</span></span>  
 [<span data-ttu-id="d7da4-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="d7da4-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
