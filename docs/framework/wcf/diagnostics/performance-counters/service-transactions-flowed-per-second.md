---
title: 'Dienst: Transaktionen Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: cb41abe74568c3e9641443b81fce3fb6eb6e41bf
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874936"
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="50c4c-102">Dienst: Transaktionen Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="50c4c-102">Service: Transactions Flowed Per Second</span></span>
<span data-ttu-id="50c4c-103">Indikatorname: Transaktionen Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="50c4c-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="50c4c-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50c4c-104">Description</span></span>  
 <span data-ttu-id="50c4c-105">Anzahl der Transaktionen, die innerhalb einer Sekunde in Vorgänge in diesem Dienst übergegangen sind.</span><span class="sxs-lookup"><span data-stu-id="50c4c-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="50c4c-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="50c4c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="50c4c-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="50c4c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
