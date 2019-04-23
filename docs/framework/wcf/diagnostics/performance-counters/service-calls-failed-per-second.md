---
title: 'Dienst: Fehlerhafte Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: d87d5f06d0c9a3849ec80a3d1c7badefde7cf372
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167491"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="57a77-102">Dienst: Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="57a77-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="57a77-103">Indikatorname: Fehlerhafte Aufrufe pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="57a77-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="57a77-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57a77-104">Description</span></span>  
 <span data-ttu-id="57a77-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Dienst in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="57a77-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="57a77-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="57a77-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="57a77-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="57a77-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="57a77-108">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="57a77-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="57a77-109">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="57a77-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="57a77-110">Der Wert dieses Indikators erhöht sich jedes Mal, wenn in diesem Dienst eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="57a77-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a77-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57a77-111">See also</span></span>

- [<span data-ttu-id="57a77-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="57a77-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
