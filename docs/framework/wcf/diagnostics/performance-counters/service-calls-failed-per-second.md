---
title: 'Dienst: Fehlerhafte Anrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 9cd649788e1304c68caa1bbf4b5fd27e6fc9d508
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861815"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="d7e59-102">Dienst: Fehlerhafte Anrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="d7e59-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="d7e59-103">Indikatorname: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="d7e59-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d7e59-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7e59-104">Description</span></span>  
 <span data-ttu-id="d7e59-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Dienst in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="d7e59-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="d7e59-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="d7e59-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d7e59-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="d7e59-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="d7e59-108">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d7e59-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="d7e59-109">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d7e59-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="d7e59-110">Der Wert dieses Indikators erhöht sich jedes Mal, wenn in diesem Dienst eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="d7e59-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e59-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7e59-111">See Also</span></span>  
 [<span data-ttu-id="d7e59-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="d7e59-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
