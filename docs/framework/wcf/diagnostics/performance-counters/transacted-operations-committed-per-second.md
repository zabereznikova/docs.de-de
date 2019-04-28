---
title: Transacted Operations Committed Per Second
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 124eae3b36a731ac50a147782b19c87e3adfa7be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766375"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="fe050-102">Transacted Operations Committed Per Second</span><span class="sxs-lookup"><span data-stu-id="fe050-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="fe050-103">Indikatorname: Übermittelte abgewickelte Vorgänge pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="fe050-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fe050-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe050-104">Description</span></span>  
 <span data-ttu-id="fe050-105">Anzahl der von in diesem Dienst abgewickelten Transaktionsvorgänge pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="fe050-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="fe050-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="fe050-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="fe050-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="fe050-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
