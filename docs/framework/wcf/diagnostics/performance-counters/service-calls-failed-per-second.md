---
title: 'Dienst: Fehlerhafte Anrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: c97e4b0c6c2c71756a9bed7b1a2359ad0c118a98
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252971"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="58359-102">Dienst: Fehlerhafte Anrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="58359-102">Service: Calls Failed Per Second</span></span>

<span data-ttu-id="58359-103">Indikatorname: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="58359-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="58359-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="58359-104">Description</span></span>  

 <span data-ttu-id="58359-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Dienst in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="58359-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="58359-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="58359-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="58359-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="58359-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="58359-108">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="58359-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="58359-109">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="58359-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="58359-110">Der Wert dieses Indikators erhöht sich jedes Mal, wenn in diesem Dienst eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="58359-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58359-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58359-111">See also</span></span>

- [<span data-ttu-id="58359-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="58359-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
