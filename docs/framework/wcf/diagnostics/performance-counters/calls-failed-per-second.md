---
title: Fehlerhafte Aufrufe pro Sekunde
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 19f09b2a2132cab56da5dec49bdc8d5f5e4c8b8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474453"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="f53c6-102">Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="f53c6-102">Calls Failed Per Second</span></span>
<span data-ttu-id="f53c6-103">Zählername: Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="f53c6-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="f53c6-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f53c6-104">Description</span></span>  
 <span data-ttu-id="f53c6-105">Anzahl von Aufrufen mit nicht behandelten Ausnahmen in diesem Vorgang innerhalb einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="f53c6-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="f53c6-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="f53c6-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f53c6-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="f53c6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="f53c6-108">Der Wert dieses Zählers erhöht sich, sobald in diesem Vorgang eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="f53c6-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53c6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f53c6-109">See Also</span></span>  
 [<span data-ttu-id="f53c6-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="f53c6-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
