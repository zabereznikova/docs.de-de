---
title: Transacted Operations In Doubt Per Second
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: 59186b1fc113bb87264a8b946cfee2719ff50b62
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550598"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="497cc-102">Transacted Operations In Doubt Per Second</span><span class="sxs-lookup"><span data-stu-id="497cc-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="497cc-103">Indikatorname: Transacted Operations In Doubt Per Second.</span><span class="sxs-lookup"><span data-stu-id="497cc-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="497cc-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="497cc-104">Description</span></span>  
 <span data-ttu-id="497cc-105">Anzahl von Transaktionsvorgängen mit einem zweifelhaften Ergebnis in diesem Dienst in einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="497cc-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="497cc-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="497cc-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="497cc-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="497cc-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
