---
title: Übergegangene Transaktionen pro Sekunde
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392935"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="9e9bf-102">Übergegangene Transaktionen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="9e9bf-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="9e9bf-103">Indikatorname: Transaktionen Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="9e9bf-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="9e9bf-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e9bf-104">Description</span></span>  
 <span data-ttu-id="9e9bf-105">Die Anzahl der in einer Sekunde an diesen Vorgang übergegangenen Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="9e9bf-106">Dieser Indikator wird jeweils inkrementiert, wenn eine TransaktionsID in einer Nachricht enthalten ist, die an den Vorgang gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="9e9bf-107">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="9e9bf-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9e9bf-108">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="9e9bf-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
