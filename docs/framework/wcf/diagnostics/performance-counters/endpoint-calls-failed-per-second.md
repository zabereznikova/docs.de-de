---
title: 'Endpunkt: Fehlerhafte Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 52419f45adde768d19d6b46642d52ad0a1844197
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100020"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="a6b32-102">Endpunkt: Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="a6b32-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="a6b32-103">Indikatorname: Fehlerhafte Aufrufe pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="a6b32-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a6b32-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6b32-104">Description</span></span>  
 <span data-ttu-id="a6b32-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Endpunkt in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="a6b32-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="a6b32-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="a6b32-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a6b32-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="a6b32-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="a6b32-108">Der Wert dieses Indikators erhöht sich, sobald an diesem Endpunkt eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="a6b32-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b32-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6b32-109">See also</span></span>

- [<span data-ttu-id="a6b32-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="a6b32-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
