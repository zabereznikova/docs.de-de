---
title: 'Endpunkt: Übergegangene Transaktionen pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405010"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="c2424-102">Endpunkt: Übergegangene Transaktionen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="c2424-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="c2424-103">Indikatorname: Transaktionen Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="c2424-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c2424-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2424-104">Description</span></span>  
 <span data-ttu-id="c2424-105">Die Anzahl der Transaktionen, die an diesem Endpunkt pro Sekunde in Vorgänge übergegangen sind.</span><span class="sxs-lookup"><span data-stu-id="c2424-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="c2424-106">Dieser Indikator wird jedes Mal gesteigert, wenn eine Transaktions-ID in einer Nachricht vorhanden ist, die an den Endpunkt gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2424-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="c2424-107">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="c2424-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c2424-108">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="c2424-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
