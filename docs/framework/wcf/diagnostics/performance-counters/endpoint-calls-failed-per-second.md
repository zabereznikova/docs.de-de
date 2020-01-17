---
title: 'Endpunkt: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 25e504221097505e622a3ba60f0c7e85ec455f36
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163617"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="63fcf-102">Endpunkt: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="63fcf-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="63fcf-103">Indikatorname: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="63fcf-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="63fcf-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="63fcf-104">Description</span></span>  
 <span data-ttu-id="63fcf-105">Die Anzahl von Aufrufen, die nicht behandelte Ausnahmen aufweisen und von diesem Endpunkt in einer Sekunde empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="63fcf-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="63fcf-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="63fcf-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="63fcf-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="63fcf-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="63fcf-108">Der Wert dieses Indikators erhöht sich, sobald an diesem Endpunkt eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="63fcf-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fcf-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63fcf-109">See also</span></span>

- [<span data-ttu-id="63fcf-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="63fcf-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
