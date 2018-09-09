---
title: 'Endpunkt: Übergegangene Transaktionen pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227141"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="cda51-102">Endpunkt: Übergegangene Transaktionen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="cda51-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="cda51-103">Indikatorname: Transaktionen Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="cda51-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cda51-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cda51-104">Description</span></span>  
 <span data-ttu-id="cda51-105">Die Anzahl der Transaktionen, die an diesem Endpunkt pro Sekunde in Vorgänge übergegangen sind.</span><span class="sxs-lookup"><span data-stu-id="cda51-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="cda51-106">Dieser Indikator wird jedes Mal gesteigert, wenn eine Transaktions-ID in einer Nachricht vorhanden ist, die an den Endpunkt gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="cda51-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="cda51-107">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="cda51-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="cda51-108">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="cda51-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
