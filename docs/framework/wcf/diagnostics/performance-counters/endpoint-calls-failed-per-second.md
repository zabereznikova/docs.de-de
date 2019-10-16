---
title: 'Endpunkt: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 9634f8a170bb2fae2f15c3f00dcabb95d512c74e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321457"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="03da6-102">Endpunkt: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="03da6-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="03da6-103">Indikatorname: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="03da6-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="03da6-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03da6-104">Description</span></span>  
 <span data-ttu-id="03da6-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Endpunkt in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="03da6-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="03da6-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="03da6-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="03da6-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="03da6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="03da6-108">Der Wert dieses Indikators erhöht sich, sobald an diesem Endpunkt eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="03da6-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03da6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03da6-109">See also</span></span>

- [<span data-ttu-id="03da6-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="03da6-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
