---
title: Transacted Operations In Doubt Per Second
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: bc978f5b45352fa9fcce5aee5a616c9f86f56aeb
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163838"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="143dd-102">Transacted Operations In Doubt Per Second</span><span class="sxs-lookup"><span data-stu-id="143dd-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="143dd-103">Indikatorname: Transacted Operations In Doubt Per Second.</span><span class="sxs-lookup"><span data-stu-id="143dd-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="143dd-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="143dd-104">Description</span></span>  
 <span data-ttu-id="143dd-105">Anzahl von Transaktionsvorgängen mit einem zweifelhaften Ergebnis in diesem Dienst in einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="143dd-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="143dd-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="143dd-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="143dd-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="143dd-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
