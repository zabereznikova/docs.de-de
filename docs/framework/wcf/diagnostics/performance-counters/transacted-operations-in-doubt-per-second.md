---
title: Transacted Operations In Doubt Per Second
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: f7365c4e5f03711129916c8c6964f7e25e9b553e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44076429"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="ed4f2-102">Transacted Operations In Doubt Per Second</span><span class="sxs-lookup"><span data-stu-id="ed4f2-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="ed4f2-103">Indikatorname: Transacted Operations In Doubt Per Second.</span><span class="sxs-lookup"><span data-stu-id="ed4f2-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ed4f2-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed4f2-104">Description</span></span>  
 <span data-ttu-id="ed4f2-105">Anzahl von Transaktionsvorgängen mit einem zweifelhaften Ergebnis in diesem Dienst in einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="ed4f2-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="ed4f2-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="ed4f2-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ed4f2-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="ed4f2-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
