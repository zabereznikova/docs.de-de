---
title: 'Endpunkt: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 0aeafa3d273ae22d9bbfe5e3edbac80c6e4851bd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271252"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="5c694-102">Endpunkt: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="5c694-102">Endpoint: Calls Failed Per Second</span></span>

<span data-ttu-id="5c694-103">Indikatorname: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="5c694-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5c694-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c694-104">Description</span></span>  

 <span data-ttu-id="5c694-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Endpunkt in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="5c694-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="5c694-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="5c694-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5c694-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="5c694-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="5c694-108">Der Wert dieses Indikators erhöht sich, sobald an diesem Endpunkt eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="5c694-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c694-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c694-109">See also</span></span>

- [<span data-ttu-id="5c694-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="5c694-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
