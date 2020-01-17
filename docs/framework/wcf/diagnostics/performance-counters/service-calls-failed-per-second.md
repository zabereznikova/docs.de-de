---
title: 'Dienst: Fehlerhafte Anrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: e165348a71101b21fa66bd4907c43335b1e476e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163981"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="872b3-102">Dienst: Fehlerhafte Anrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="872b3-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="872b3-103">Indikatorname: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="872b3-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="872b3-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="872b3-104">Description</span></span>  
 <span data-ttu-id="872b3-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Dienst in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="872b3-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="872b3-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="872b3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="872b3-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="872b3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="872b3-108">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="872b3-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="872b3-109">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="872b3-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="872b3-110">Der Wert dieses Indikators erhöht sich jedes Mal, wenn in diesem Dienst eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="872b3-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872b3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="872b3-111">See also</span></span>

- [<span data-ttu-id="872b3-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="872b3-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
