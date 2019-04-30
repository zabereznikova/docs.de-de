---
title: Übergegangene Transaktionen pro Sekunde
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927191"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="7aed5-102">Übergegangene Transaktionen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="7aed5-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="7aed5-103">Indikatorname:  Übergegangene Transaktionen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="7aed5-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="7aed5-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aed5-104">Description</span></span>  
 <span data-ttu-id="7aed5-105">Die Anzahl der in einer Sekunde an diesen Vorgang übergegangenen Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="7aed5-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="7aed5-106">Dieser Indikator wird jeweils inkrementiert, wenn eine Transaktions-ID in einer Nachricht enthalten ist, die an den Vorgang gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="7aed5-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="7aed5-107">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="7aed5-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7aed5-108">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="7aed5-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
